# Lektionen 1 und 2
>* In der ersten Woche haben wir uns mit den Begriffen Polymorphie und Vererbung beschäftigt.

## Polymorphie

* Polymorphie kommt aus dem griechischen und bedeutet "Vielgestaltigkeit"
* In Java können Methoden der sogenannnten Vielgestaltigkeit (Polymorphie) unterliegen.
* Von Polymorphie spricht man dann wenn zwei Klassen den gleichen Methodennamen verwenden, sich die Implementierung jedoch unterscheidet.

Oftmals wird die Polymorphie mit der Vererbung verwendet damit die Kindesklassen die Methoden ebenfalls nutzen können. Dies funktioniert aber nur
weil jede Kindsklasse alle Methoden und Attribute der superclass (Elternklasse) implementieren muss.

>* Quelle: https://java-tutorial.org/polymorphie.html

## Vererbung

* Bei der Vererbung wird zwischen Subklasse (Kindsklasse) und Superklasse (Eltern- oder Basisklasse) unterschieden.

Die Superklasse ist in der Regel eine Zusammenfassung von allgemeinen Attributen und Methoden unterschiedlicher aber ähnlicher Objekte.

> [!NOTE|style:flat]
> Eine Vererbung in Java findet über das Schlüsselwort extends statt. Folgend ein Beispiel wie die Klasse mit extends initialisiert wird.

```
public class Subklasse extends Superklasse {

}
```
> [!NOTE|style:flat]
> Der Modifikator kann public, abstract oder andere Zugriffsmodifikatoren annehmen.
> Die Subklasse bezeichnet beim vorherigen Code-Beispiel die Klasse die etwas vererbt bekommt.

>* Quelle: https://java-tutorial.org/vererbung.html

## BZT1 (Skript Auftrag)

>* Die Klasse BZT1 (mit Main)
```
public class BZT1
{

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args)
    {
       Lehrer mt = new Lehrer();
       mt.setNachname("Inauen");
       mt.setFachbereich("Informatik");
       
       Lernende mus = new Lernende();
       mus.setNachname("Muster");
       mus.setNummer(1001);
       
       System.out.println("Nachname des Lehrers: " + mt.getNachname());
       System.out.println("Fachbereich des Lehrers: " + mt.getFachbereich());
       
       System.out.println("Nachname des Lernenden: " + mus.getNachname());
       System.out.println("Nummer des Lernenden: " + mus.getNummer());
    }
}
```
>* Die Klasse Lehrer
```
 public class Lehrer
{
    private String fachbereich = new String(); // ein String ist eine Klasse, 
                                               // das geht deshalb mit new!
    private String nachname;
    
   public void setNachname(String nachname)
    {
        this.nachname = nachname;
    }
    
    public String getNachname()
    {
        return nachname;
    }
    
    public void setFachbereich(String fachbereich)
    {
        this.fachbereich = fachbereich;
    }
    
    public String  getFachbereich()
    {
        return fachbereich;
    }
}
```

>* Die Klasse Lernender
```
public class Lernende
{
    private String nachname = new String(); // new ist optional
    private int nummer;  // Schülernummer
    
    public void setNachname(String nachname)
    {
        this.nachname = nachname;
    }
    
    public String getNachname()
    {
        return nachname;
    }
    
    public void setNummer(int nummer)
    {
        this.nummer = nummer;
    }
    
    public int getNummer()
    {
        return nummer;
    }  
}
```
> [!NOTE|style:flat]
> Das Beispiel zeigt auf das redundante Code-Segmente mit der Vererbung entfernt werden können.
Dies löst man indem man eine Superklasse erstellt z.B. Person und den String nachname mit GETTER und SETTER in die Klasse aufnimmt.
Dannach kann mit der Vererbung von der Klasse Lehrer sowie Lernender auf die Superklasse und deren Methoden zugegriffen werden.