---
title: "Erstellen von neuen Attributen für Elemente im Dokumentobjektmodell"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6970ffc38e900c9b47c58c8ae4b81b9551f5589b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a>Erstellen von neuen Attributen für Elemente im Dokumentobjektmodell
Erstellen von neuen Attributen unterscheidet sich vom Erstellen anderer Knotentypen, da Attribute keine Knoten sind, jedoch sind Eigenschaften eines Elementknotens und sind in enthalten eine **XmlAttributeCollection** mit dem Element verknüpft sind. Es gibt verschiedene Möglichkeiten, ein Attribut zu erstellen und an ein Element anzuhängen:  
  
-   Den Elementknoten abrufen und verwenden Sie **SetAttribute** der attributauflistung dieses Elements ein Attribut hinzu.  
  
-   Erstellen einer **XmlAttribute** Knoten unter Verwendung der **CreateAttribute** -Methode, den Elementknoten abrufen, verwenden Sie **SetAttributeNode** auf den Knoten der attributauflistung, hinzufügen Element.  
  
 Im folgende Beispiel wird gezeigt, wie ein Attribut hinzufügen, um ein Element mit dem **SetAttribute** Methode.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
public class Sample  
  
  public shared sub Main()  
  
  Dim doc as XmlDocument = new XmlDocument()  
  doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _  
              "<title>Pride And Prejudice</title>" & _  
              "</book>")  
  Dim root as XmlElement = doc.DocumentElement  
  
  'Add a new attribute.  
  root.SetAttribute("genre", "urn:samples", "novel")  
  
  Console.WriteLine("Display the modified XML...")  
  Console.WriteLine(doc.InnerXml)  
  
  end sub  
end class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  public static void Main()  
  {  
    XmlDocument doc = new XmlDocument();  
    doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +  
                "<title>Pride And Prejudice</title>" +  
                "</book>");  
    XmlElement root = doc.DocumentElement;  
  
    // Add a new attribute.  
    root.SetAttribute("genre", "urn:samples", "novel");  
  
    Console.WriteLine("Display the modified XML...");  
    Console.WriteLine(doc.InnerXml);  
  }  
```  
  
 Das folgende Beispiel zeigt ein neues Attribut erstellt wird, mithilfe der **CreateAttribute** Methode. Anschließend wird das Attribut der attributauflistung hinzugefügt der **Buch** Element mit dem **SetAttributeNode** Methode.  
  
 Mit dem folgenden XML-Code   
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 erstellen Sie ein neues Attribut. Geben Sie ihm einen Wert   
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 , und fügen Sie es an das Element an  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 **Ausgabe**  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 Der vollständigen Beispielcode finden Sie unter <xref:System.Xml.XmlDocument.CreateAttribute%2A>.  
  
 Sie können auch erstellen eine **XmlAttribute** Knoten und Verwenden der **InsertBefore** oder **InsertAfter** Methoden, um sie in der entsprechenden Position in der Auflistung einzufügen. Wenn ein Attribut mit demselben Namen bereits vorhanden ist, in der attributauflistung der vorhandenen ist **XmlAttribute** Knoten aus der Auflistung und der neuen entfernt **XmlAttribute** Knoten eingefügt wird. Dies führt die gleiche Weise wie die **SetAttribute** Methode. Diese Methoden erfordern als Parameter einen vorhandenen Knoten als Bezugspunkt möchten die **InsertBefore** und **InsertAfter**. Wenn Sie keinen Referenzknoten, der angibt, wo den neuen Knoten, der Standardwert für eingefügt angeben der **InsertAfter** Methode besteht darin, den neuen Knoten am Anfang der Auflistung eingefügt. Die Standardposition für die **InsertBefore**, wenn kein Referenzknoten angegeben wird, wird am Ende der Auflistung.  
  
 Wenn Sie erstellt ein **XmlNamedNodeMap** von Attributen, können Sie ein Attribut mit Namen hinzufügen der <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>. Weitere Informationen finden Sie unter [Knotenauflistungen in "NamedNodeMaps" und "NodeLists"](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).  
  
## <a name="default-attributes"></a>Standardattribute  
 Wenn Sie ein Element erstellen, das gemäß Deklaration ein Standardattribut aufweist, wird durch das Dokumentobjektmodell (DOM) ein neues Standardattribut mit seinem Standardwert erstellt und an das Element angehängt. Gleichzeitig werden die untergeordneten Knoten des Standardattributs erstellt.  
  
## <a name="attribute-child-nodes"></a>Untergeordnete Knoten von Attributen  
 Die Werte eines Attributknotens werden zu dessen untergeordneten Knoten. Es gibt nur zwei Typen von zulässigen untergeordneten Knoten: **XmlText** Knoten, und **XmlEntityReference** Knoten. Dies sind die untergeordneten Knoten in dem Sinne, dass Methoden wie z. B. **FirstChild** und **LastChild** als untergeordnete Knoten zu verarbeiten. Dieses Merkmal eines Attributs mit untergeordneten Knoten ist von Bedeutung, wenn Sie versuchen, Attribute oder untergeordnete Knoten von Attributen zu entfernen. Weitere Informationen finden Sie unter [Entfernen von Attributen aus einem Elementknoten im DOKUMENTOBJEKTMODELL](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
