---
title: 'Gewusst wie: Steuern von Namespacepräfixen (C#) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: 9f43c0804d8c830fa75f1e1390cb578c5f5d5106
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141382"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a>Gewusst wie: Steuern von Namespacepräfixen (C#) (LINQ to XML)
In diesem Thema wird beschrieben, wie Sie beim Serialisieren einer XML-Struktur Namespacepräfixe steuern können.  
  
 In vielen Situationen ist es nicht notwendig, die Namespacepräfixe zu steuern.  
  
 Bestimmte XML-Programmiertools erfordern jedoch eine spezifische Steuerung der Namespacepräfixe. Angenommen, Sie möchten z. B. ein XSLT-Stylesheet oder ein XAML-Dokument bearbeiten, das eingebettete XPath-Ausdrücke enthält, die auf bestimmte Namespacepräfixe verweisen. In diesem Fall ist es wichtig, dass das Dokument mit diesen konkreten Präfixen serialisiert wird.  
  
 Dies ist der häufigste Grund für die Steuerung von Namespacepräfixen.  
  
 Ein weiterer Grund für die Notwendigkeit, Namespacepräfixe zu steuern, liegt darin, dass die Benutzer das XML-Dokument manuell bearbeiten können sollen und dass Sie Namespacepräfixe erstellen möchten, die für den Benutzer einfach einzugeben sind. Nehmen wir z. B. an, Sie möchten ein XSD-Dokument generieren. Den Konventionen für Schemas zufolge verwenden Sie  als Präfix für den Schemanamespace entweder `xs` oder `xsd`.  
  
 Zum Steuern von Namespacepräfixen fügen Sie Attribute ein, die Namespaces deklarieren. Wenn Sie die Namespaces mit bestimmten Präfixen deklarieren, versucht [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], die Namespacepräfixe beim Serialisieren zu beachten.  
  
 Beim Erstellen eines Attributs, das einen Namespace mit einem Präfix deklariert, erstellen Sie ein Attribut, bei dem der Namespace des Namens des Attributs <xref:System.Xml.Linq.XNamespace.Xmlns%2A> lautet und der Name des Attributs das Namespacepräfix ist. Der Wert des Attributs ist der URI des Namespace.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel deklariert zwei Namespaces. Es gibt für den `http://www.adventure-works.com`-Namespace das Präfix `aw` und für den `www.fourthcoffee.com`-Namespace das Präfix `fc` an.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
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
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)
