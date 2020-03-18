---
title: Erstellen von XML-Strukturen in C# (LINQ to XML)
ms.date: 08/31/2018
ms.assetid: cc74234a-0bac-4327-9c8c-5a2ead15b595
ms.openlocfilehash: 4794e4fe019b30d8f2acb3eb255bb77ba2f7f290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169544"
---
# <a name="creating-xml-trees-in-c-linq-to-xml"></a>Erstellen von XML-Bäumen in C# (LINQ to XML)
Dieser Abschnitt enthält Informationen zum Erstellen von XML-Strukturen in C#.  
  
 Informationen zur Verwendung der Ergebnisse von LINQ-Abfragen als Inhalt für eine <xref:System.Xml.Linq.XElement>-Klasse finden Sie unter [Funktionale Konstruktion (LINQ to XML) (C#)](./functional-construction-linq-to-xml.md).  
  
## <a name="constructing-elements"></a>Konstruieren von Elementen
 Die Signaturen der <xref:System.Xml.Linq.XElement>-Konstruktoren und der <xref:System.Xml.Linq.XAttribute>-Konstruktoren ermöglichen es Ihnen, den Inhalt des Elements oder Attributs als Argumente an den Konstruktor zu übergeben. Da einer der Konstruktoren eine variable Anzahl von Argumenten akzeptiert, können Sie jede beliebige Anzahl von untergeordneten Elementen übergeben. Natürlich kann jedes dieser untergeordneten Elemente wiederum untergeordnete Elemente enthalten. Für jedes Element können Sie eine beliebige Anzahl von Attributen hinzufügen.  
  
 Wenn beim Hinzufügen von <xref:System.Xml.Linq.XNode>-Objekten (einschließlich <xref:System.Xml.Linq.XElement>) oder von <xref:System.Xml.Linq.XAttribute>-Objekten der neue Inhalt kein übergeordnetes Element besitzt, werden die Objekte einfach an die XML-Struktur angefügt. Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird er geklont, und der neu geklonte Inhalt wird an die XML-Struktur angefügt. Dies wird im letzten Beispiel in diesem Thema gezeigt.  
  
 Zum Erstellen eines `contacts`-<xref:System.Xml.Linq.XElement>-Objekts können Sie den folgenden Code verwenden:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Bei ordnungsgemäßen Einzügen ähnelt der zum Konstruieren von <xref:System.Xml.Linq.XElement>-Objekten verwendete Code sehr stark der Struktur des zugrunde liegenden XML-Codes.  
  
## <a name="xelement-constructors"></a>„XElement“-Konstruktoren  
 Die <xref:System.Xml.Linq.XElement>-Klasse verwendet für die funktionale Konstruktion die folgenden Konstruktoren. Beachten Sie, dass es auch noch andere Konstruktoren für <xref:System.Xml.Linq.XElement> gibt. Diese werden nicht für die funktionale Konstruktion verwendet und sind daher hier auch nicht aufgeführt.  
  
|Konstruktor|Beschreibung|  
|-----------------|-----------------|  
|`XElement(XName name, object content)`|Erstellt ein <xref:System.Xml.Linq.XElement>. Der `name`-Parameter gibt den Namen des Elements an, und `content` gibt den Inhalt des Elements an.|  
|`XElement(XName name)`|Erstellt ein <xref:System.Xml.Linq.XElement> mit seinem <xref:System.Xml.Linq.XName>, initialisiert für den angegebenen Namen.|  
|`XElement(XName name, params object[] content)`|Erstellt ein <xref:System.Xml.Linq.XElement> mit seinem <xref:System.Xml.Linq.XName>, initialisiert für den angegebenen Namen. Die Attribute und/oder untergeordneten Elemente werden aus dem Inhalt der Parameterliste erstellt.|  
  
 Der `content`-Parameter ist äußerst flexibel. Er unterstützt jede Art von Objekt, das ein gültiges untergeordnetes Element eines <xref:System.Xml.Linq.XElement> ist. Die folgenden Regeln gelten für andere Arten von Objekten, die in diesem Parameter übergeben werden:  
  
- Eine Zeichenfolge wird als Textinhalt hinzugefügt.  
  
- Ein <xref:System.Xml.Linq.XElement> wird als untergeordnetes Element hinzugefügt.  
  
- Ein <xref:System.Xml.Linq.XAttribute> wird als Attribut hinzugefügt.  
  
- Eine <xref:System.Xml.Linq.XProcessingInstruction>, ein <xref:System.Xml.Linq.XComment> oder ein <xref:System.Xml.Linq.XText> wird als untergeordneter Inhalt hinzugefügt.  
  
- Eine <xref:System.Collections.IEnumerable> wird aufgelistet, und diese Regeln werden rekursiv auf die Ergebnisse angewendet.  
  
- Für alle anderen Arten wird deren `ToString`-Methode aufgerufen, und das Ergebnis wird als Textinhalt hinzugefügt.  
  
### <a name="creating-an-xelement-with-content"></a>Erstellen eines „XElement“ mit Inhalt  
 Sie können mit einem einzigen Methodenaufruf ein <xref:System.Xml.Linq.XElement> erstellen, das einfachen Inhalt enthält. Geben Sie dazu den Inhalt wie folgt als zweiten Parameter an:  
  
```csharp  
XElement n = new XElement("Customer", "Adventure Works");  
Console.WriteLine(n);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
 Sie können jede Art von Objekt als Inhalt übergeben. So erstellt z. B. der folgende Code ein Element, das eine Gleitkommazahl als Inhalt enthält:  
  
```csharp  
XElement n = new XElement("Cost", 324.50);  
Console.WriteLine(n);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Cost>324.5</Cost>  
```  
  
 Die Gleitkommazahl wird geschachtelt und an den Konstruktor übergeben. Die geschachtelte Zahl wird in eine Zeichenfolge konvertiert und als Inhalt des Elements verwendet.  
  
### <a name="creating-an-xelement-with-a-child-element"></a>Erstellen eines „XElement“ mit einem untergeordneten Element  
 Wenn Sie eine Instanz der <xref:System.Xml.Linq.XElement>-Klasse für das Inhaltsargument übergeben, erstellt der Konstruktor ein Element mit einem untergeordneten Element:  
  
```csharp  
XElement shippingUnit = new XElement("ShippingUnit",  
    new XElement("Cost", 324.50)  
);  
Console.WriteLine(shippingUnit);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<ShippingUnit>  
  <Cost>324.5</Cost>  
</ShippingUnit>  
```  
  
### <a name="creating-an-xelement-with-multiple-child-elements"></a>Erstellen eines „XElement“ mit mehreren untergeordneten Elementen  
 Sie können für den Inhalt mehrere <xref:System.Xml.Linq.XElement>-Objekte übergeben. Jedes dieser <xref:System.Xml.Linq.XElement>-Objekte wird zu einem untergeordneten Element.  
  
```csharp  
XElement address = new XElement("Address",  
    new XElement("Street1", "123 Main St"),  
    new XElement("City", "Mercer Island"),  
    new XElement("State", "WA"),  
    new XElement("Postal", "68042")  
);  
Console.WriteLine(address);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Address>  
  <Street1>123 Main St</Street1>  
  <City>Mercer Island</City>  
  <State>WA</State>  
  <Postal>68042</Postal>  
</Address>  
```  
  
 Sie können eine ganze XML-Struktur erstellen, indem Sie das oben erwähnte Beispiel wie folgt erweitern:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
Console.WriteLine(contacts);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Contacts>  
  <Contact>  
    <Name>Patrick Hines</Name>  
    <Phone>206-555-0144</Phone>  
    <Address>  
      <Street1>123 Main St</Street1>  
      <City>Mercer Island</City>  
      <State>WA</State>  
      <Postal>68042</Postal>  
    </Address>  
  </Contact>  
</Contacts>  
```  

### <a name="creating-an-xelement-with-an-xattribute"></a>Erstellen eines „XElement“ mit einem XAttribute
 Wenn Sie eine Instanz der <xref:System.Xml.Linq.XAttribute>-Klasse für das Inhaltsargument übergeben, erstellt der Konstruktor ein Element mit einem Attribut:

```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>
```

### <a name="creating-an-empty-element"></a>Erstellen eines leeren Elements  
 Wenn Sie ein leeres <xref:System.Xml.Linq.XElement> erstellen möchten, übergeben Sie einfach keinen Inhalt an den Konstruktor. Das folgende Beispiel erstellt ein leeres Element:  
  
```csharp  
XElement n = new XElement("Customer");  
Console.WriteLine(n);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Customer />  
```  
  
### <a name="attaching-vs-cloning"></a>Anfügen oder Klonen?  
 Wie bereits erwähnt, werden beim Hinzufügen von <xref:System.Xml.Linq.XNode>-Objekten (einschließlich <xref:System.Xml.Linq.XElement>) oder von <xref:System.Xml.Linq.XAttribute>-Objekten für den Fall, dass der neue Inhalt kein übergeordnetes Element besitzt, die Objekte einfach an die XML-Struktur angefügt. Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird er geklont, und der neu geklonte Inhalt wird an die XML-Struktur angefügt.  

Das folgende Beispiel zeigt das Verhalten, wenn Sie zu einer Struktur ein übergeordnetes Element und ein Element ohne übergeordnetes Element hinzufügen.

```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  

// The example displays the following output:  
//    Child1 was cloned  
//    Child2 was attached  
```

## <a name="see-also"></a>Weitere Informationen

- [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](./linq-to-xml-overview.md)
