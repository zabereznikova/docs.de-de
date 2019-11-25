---
title: 'Vorgehensweise: Erstellen eines Dokuments mit Namespaces (C#) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 429b0b0b41f2201b983f931e469b25ff406b91ac
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141334"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a>Vorgehensweise: Erstellen eines Dokuments mit Namespaces (C#) (LINQ to XML)
In diesem Thema wird das Erstellen von Dokumenten mit Namespaces beschrieben.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie ein Element oder Attribut erstellen möchten, das sich in einem Namespace befindet, deklarieren und initialisieren Sie zuerst ein <xref:System.Xml.Linq.XNamespace>-Objekt. Anschließend verwenden Sie die Additionsoperatorüberladung, um den Namespace mit dem lokalen Namen in Form einer Zeichenfolge zu kombinieren.  
  
 Das folgende Beispiel erstellt ein Dokument mit nur einem Namespace. Standardmäßig serialisiert [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] dieses Dokument mit einem Standardnamespace.  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein Dokument mit nur einem Namespace. Es erstellt auch ein Attribut, das den Namespace mit einem Namespacepräfix deklariert. Gehen Sie zum Erstellen eines Attributs, das einen Namespace mit einem Präfix deklariert, wie folgt vor. Erstellen Sie ein Attribut, bei dem der Name des Attributs das Namespacepräfix darstellt. Dieser Name befindet sich im <xref:System.Xml.Linq.XNamespace.Xmlns%2A>-Namespace. Der Wert dieses Attributs ist der URI des Namespace.  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Erstellen eines Dokuments, das zwei Namespaces enthält. Einer der Namespaces ist der Standardnamespace. Der andere Namespace besitzt ein Präfix.  
  
 Durch das Aufnehmen von Namespaceattributen in das Stammelement werden die Namespaces so serialisiert, dass `http://www.adventure-works.com` zum Standardnamespace wird und `www.fourthcoffee.com` mit dem Präfix „fc“ serialisiert wird. Zum Erstellen eines Attributs, das einen Standardnamespace deklariert, erstellen Sie ein Attribut mit dem Namen  <legacyBold>xmlns</legacyBold> ohne einen Namespace. Der Wert des Attributs ist der Standardnamespace-URI.  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt ein Dokument, das zwei Namespaces enthält, die beide ein Namespacepräfix besitzen.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a>Beispiel  
 Dasselbe Ergebnis lässt sich erzielen, indem statt des Deklarierens und Erstellens eines <xref:System.Xml.Linq.XNamespace>-Objekts erweiterte Namen verwendet werden.  
  
 Dieser Ansatz wirkt sich aber negativ auf die Leistung aus. Jedes Mal, wenn Sie eine Zeichenfolge, die einen erweiterten Namen enthält, an [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] übergeben, muss [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] den Namen analysieren und nach dem atomisierten Namespace und dem atomisierten Namen suchen. Dieser Prozess nimmt CPU-Zeit in Anspruch. Wenn es auf eine hohe Leistung ankommt, sollten Sie daher explizit ein <xref:System.Xml.Linq.XNamespace>-Objekt deklarieren und verwenden.  
  
 Wenn die Leistung ein wichtiger Aspekt ist, finden Sie weitere Informationen unter [Pre-Atomization of XName Objects (LINQ to XML) (C#) (Voratomisierung von XName-Objekten (LINQ to XML) (C#))](./pre-atomization-of-xname-objects-linq-to-xml.md).  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)
