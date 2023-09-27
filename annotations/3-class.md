#  Terceira aula - 13/09/23

### Tópicos 

- analise da classe Time1
- importancia do metodo toString para imprimir o conteudo do objeto e não seu endereço de memória 
- não criar classes 
- uso do this (ou pq não usar kkkkk)
- static 
- garbage collector (um gari)


### this

não a necessidade de this se usarmos nomes diferentes no construtor

Exemplo com this

``` java

    private int hour;

    public constructor (String hour) {
        this.hour = hour;
    }
```

``` java

    private int hour;

    public constructor(String h){
        hour = h;
    }
```

no uso de metodos que estão na mesma classe também não se a necessidade



Boa usabilidade do This para segurança, protegendo todas as entradas de dados

```Java 

public class Time2 {
    // this é o guardinha
    
    private int hour;
    private int minute;
    private int second;

    public Time2 () {
        this(0, 0, 0);
    }

    public Time2 (int h) {
        this(h, 0, 0);
    }

    public Time2(int h, int m, int s) {
        setTime(h, m, s);
    }

    public void SetTime(int h, int m, int s) {
        setHour(h);
        setMinute(m);
        setSecond(s);
    }

    public void setHour(int h) {
        hour = ( ( h >= 0 &&  h < 24 ) ? h : 0 );
    }

    public void setMinute(int m) {
        minute = ( ( m >= 0 && h < 60 ) ? m : 0 );
    }

    public void setSecond(int s) {
        second = ( ( s >= 0 && s < 60 ) ? s : 0 );
    }
}
```

### static

o atributo count é acessado mesmo sem a instancia ou em todas as instancias do objeto

```java
public class Employer{
    public static count = 0;

    public Int getCount(){
        return count;
    }
}
```

### Garbage Collector 

Monitora objetos com endereço de memória com valor nulo 