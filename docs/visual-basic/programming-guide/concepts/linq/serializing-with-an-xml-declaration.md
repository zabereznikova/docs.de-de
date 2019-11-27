---
title: Serialisieren mit einer XML-Deklaration
ms.date: 07/20/2015
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
ms.openlocfilehash: 96c95b4c94290016684721a194ca31a836a49740
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350631"
---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a>Serialisieren mit einer XML-Deklaration (Visual Basic)
In diesem Thema wird beschrieben, wie Sie steuern können, ob die Serialisierung eine XML-Deklaration generiert.  
  
## <a name="xml-declaration-generation"></a>Generierung einer XML-Deklaration  
 Beim Serialisieren in ein <xref:System.IO.File>- oder <xref:System.IO.TextWriter>-Objekt führt die Verwendung der <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>- oder <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>-Methode zur Generierung einer XML-Deklaration. Beim Serialisieren in einen <xref:System.Xml.XmlWriter> bestimmen die (in einem <xref:System.Xml.XmlWriterSettings>-Objekt angegebenen) Writer-Einstellungen, ob eine XML-Deklaration generiert wird.  
  
 Bei der Serialisierung in eine Zeichenfolge mit der `ToString`-Methode enthält der resultierende XML-Code keine XML-Deklaration.  
  
### <a name="serializing-with-an-xml-declaration"></a>Serialisieren mit einer XML-Deklaration  
 Das folgende Beispiel erstellt ein <xref:System.Xml.Linq.XElement>, speichert das Dokument in einer Datei und gibt die Datei dann auf der Konsole aus:  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
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
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Serialisieren von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
