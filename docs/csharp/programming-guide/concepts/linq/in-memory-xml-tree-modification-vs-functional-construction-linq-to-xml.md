---
title: Änderung der XML-Struktur im Arbeitsspeicher und Funktionale Konstruktion (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b5afc31d-a325-4ec6-bf17-0ff90a20ffca
ms.openlocfilehash: 55eb95585bdd5d2c52175cacae2e6d049bd06f69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "66484553"
---
# <a name="in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml-c"></a>Änderung der XML-Struktur im Arbeitsspeicher und Funktionale Konstruktion (LINQ to XML) (C#)
Zur Änderung der Form eines XML-Dokuments wird üblicherweise die XML-Struktur an Ort und Stelle geändert. Eine typische Anwendung lädt ein Dokument in einen Datenspeicher, z. B. DOM oder [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], verwendet eine Programmierschnittstelle, um Knoten einzufügen, zu löschen oder zu ändern, und speichert den XML-Code dann in einer Datei bzw. überträgt ihn über ein Netzwerk.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ermöglicht eine andere Herangehensweise, die sich in vielen Szenarios als hilfreich erweist: *die funktionale Konstruktion*. Bei der funktionalen Konstruktion wird das Ändern von Daten als ein Transformationsproblem und nicht als detaillierte Manipulation eines Datenspeichers angesehen. Wenn Sie eine Datendarstellung effizient von einer Form in eine andere Form transformieren können, sieht das Ergebnis genauso aus, als hätten Sie einen Datenspeicher so manipuliert, dass er eine andere Form erhalten hat. Ein entscheidender Punkt bei der funktionalen Konstruktion ist die Übergabe der Ergebnisse von Abfragen an die Konstruktoren <xref:System.Xml.Linq.XDocument> und <xref:System.Xml.Linq.XElement>.  
  
 Das Schreiben des Transformationscodes kostet Sie häufig nur einen Bruchteil der Zeit, die Sie für die Manipulation des Datenspeichers hätten aufwenden müssen, und der Code ist robuster und leichter zu unterhalten. In diesen Fällen ist die Verwendung von Transformationscode die effektivere Möglichkeit, Daten zu ändern, auch wenn die Transformation mehr CPU-Leistung beansprucht. Wenn ein Entwickler mit dem funktionalen Ansatz vertraut ist, ist der entstehende Code häufig einfacher zu verstehen. Es ist dann auch leichter, den Code zu finden, der die einzelnen Teile der Struktur ändert.  
  
 Das Ändern einer XML-Struktur an Ort und Stelle ist vielen DOM-Programmierern vertrauter, während Code, der mit dem funktionalen Ansatz geschrieben wurde, für Entwickler, die diesen Ansatz nicht kennen, eher fremd aussieht. Wenn an einer großen XML-Struktur nur eine kleine Änderung vorgenommen werden muss, wird die CPU durch das Ändern der Struktur an Ort und Stelle weniger beansprucht.  
  
 Dieses Thema enthält ein Beispiel, das mit beiden Ansätzen implementiert wird.  
  
## <a name="transforming-attributes-into-elements"></a>Transformieren von Attributen in Elemente  
 Nehmen wir für dieses Beispiel an, Sie möchten das folgende einfache XML-Dokument so ändern, dass aus den Attributen Elemente werden. Zunächst wird in diesem Thema der herkömmliche Ansatz gezeigt: das Ändern einer Struktur an Ort und Stelle. Anschließend wird der Ansatz der funktionalen Konstruktion dargestellt.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root Data1="123" Data2="456">  
  <Child1>Content</Child1>  
</Root>  
```  
  
### <a name="modifying-the-xml-tree"></a>Ändern der XML-Struktur  
 Sie können prozeduralen Code zum Erstellen von Elementen aus Attributen schreiben und dann die Attribute löschen. Dies sieht wie folgt aus:  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
foreach (XAttribute att in root.Attributes()) {  
    root.Add(new XElement(att.Name, (string)att));  
}  
root.Attributes().Remove();  
Console.WriteLine(root);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Child1>Content</Child1>  
  <Data1>123</Data1>  
  <Data2>456</Data2>  
</Root>  
```  
  
### <a name="functional-construction-approach"></a>Funktionale Konstruktion  
 Bei der funktionalen Konstruktion wird zunächst eine neue Struktur erstellt. Dann werden Elemente und Attribute aus der Quellstruktur ausgewählt und der neuen Struktur hinzugefügt, wobei sie entsprechend transformiert werden. Der funktionale Ansatz sieht wie folgt aus:  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
XElement newTree = new XElement("Root",  
    root.Element("Child1"),  
    from att in root.Attributes()  
    select new XElement(att.Name, (string)att)  
);  
Console.WriteLine(newTree);  
```  
  
 Dieses Beispiel gibt denselben XML-Code wie das erste Beispiel aus. Beachten Sie dabei aber, dass Sie beim funktionalen Ansatz die entstehende Struktur des neuen XML-Codes auch tatsächlich sehen können. Sie können die Erstellung des `Root`-Elements, den Code, der das `Child1`-Element aus der ursprünglichen Struktur abruft, und den Code sehen, der die Attribute aus der Quellstruktur in Elemente in der neuen Struktur transformiert.  
  
 Der funktionale Ansatz ist in diesem Beispiel nicht kürzer und auch in keiner Weise einfacher als das erste Beispiel. Wenn an einer XML-Struktur aber viele Änderungen vorgenommen werden müssen, wird der nicht-funktionale Ansatz ziemlich komplex und in gewisser Weise stumpf. Im Unterschied dazu erstellen Sie beim funktionalen Ansatz lediglich den gewünschten XML-Code mit entsprechenden eingebetteten Abfragen und Ausdrücken, sodass Sie den gewünschten Inhalt erhalten. Der funktionale Ansatz erzeugt Code, der leichter zu unterhalten ist.  
  
 Beachten Sie, dass der funktionale Ansatz in diesem Fall wahrscheinlich nicht so gut funktioniert wie die direkte Bearbeitung der Struktur. Das Hauptproblem dabei ist, dass beim funktionalen Ansatz kurzlebigere Objekte entstehen. Der funktionale Ansatz zahlt sich aber aus, wenn der Programmierer dadurch produktiver wird.  
  
 Das hier verwendete Beispiel ist ein sehr einfaches Beispiel, das lediglich dazu dient, die grundlegenden Unterschiede zwischen den beiden Ansätzen zu verdeutlichen. Beim Transformieren großer XML-Dokumente sind beim funktionalen Ansatz eindeutig größere Produktivitätsgewinne zu erzielen.  
  