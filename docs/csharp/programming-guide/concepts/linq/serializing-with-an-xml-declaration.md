---
title: Serialisieren mit einer XML-Deklaration (C#)
ms.date: 07/20/2015
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
ms.openlocfilehash: 4f5dd9a7e392acff30814db4a483b297494b68b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702404"
---
# <a name="serializing-with-an-xml-declaration-c"></a>Serialisieren mit einer XML-Deklaration (C#)
In diesem Thema wird beschrieben, wie Sie steuern können, ob die Serialisierung eine XML-Deklaration generiert.  
  
## <a name="xml-declaration-generation"></a>Generierung einer XML-Deklaration  
 Beim Serialisieren in ein <xref:System.IO.File>- oder <xref:System.IO.TextWriter>-Objekt führt die Verwendung der <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>- oder <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>-Methode zur Generierung einer XML-Deklaration. Beim Serialisieren in einen <xref:System.Xml.XmlWriter> bestimmen die (in einem <xref:System.Xml.XmlWriterSettings>-Objekt angegebenen) Writer-Einstellungen, ob eine XML-Deklaration generiert wird.  
  
 Bei der Serialisierung in eine Zeichenfolge mit der `ToString`-Methode enthält der resultierende XML-Code keine XML-Deklaration.  
  
### <a name="serializing-with-an-xml-declaration"></a>Serialisieren mit einer XML-Deklaration  
 Das folgende Beispiel erstellt ein <xref:System.Xml.Linq.XElement>, speichert das Dokument in einer Datei und gibt die Datei dann auf der Konsole aus:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a>Serialisieren ohne eine XML-Deklaration  
 Das folgende Beispiel zeigt die Vorgehensweise beim Speichern eines <xref:System.Xml.Linq.XElement> in einem <xref:System.Xml.XmlWriter>.  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Serialisieren von XML-Strukturen (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
