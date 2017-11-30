---
title: Abrufen von ungeordneten Knoten anhand des Namens oder Indexes
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
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8bea8f373dced08fd7a2a828255a593533df9d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="unordered-node-retrieval-by-name-or-index"></a>Abrufen von ungeordneten Knoten anhand des Namens oder Indexes
Die **XmlNamedNodeMap** wird beschrieben, in der Spezifikation World Wide Web Consortium (W3C) als "NamedNodeMap" durch und ist erforderlich, um eine ungeordnete Gruppe von Knoten mit der Fähigkeit zum Verweisknoten nach Name oder Index zu behandeln. Die einzige Möglichkeit haben Sie Zugriff auf eine **XmlNamedNodeMap** ist, wenn ein **XmlNamedNodeMap** über eine Methode oder Eigenschaft zurückgegeben wird. Es gibt drei Methoden oder Eigenschaften, die Zurückgeben einer **XmlNamedNodeMap**:  
  
-   XmlElement.Attributes  
  
-   XmlDocumentType.Entities  
  
-   XmlDocumentType.Notations  
  
 Z. B. die **XmlDocumentType.Entities** Eigenschaft ruft die Auflistung der **XmlEntity** Knoten in der Dokumenttypdeklaration deklarierte. Diese Auflistung wird zurückgegeben, als ein **XmlNamedNodeMap**, und Sie können die Auflistung mit dem Durchlaufen der **Anzahl** Eigenschaft und der Anzeige Entitätsinformationen. Ein Beispiel für die Iteration durch eine **XmlNamedNodeMap**, finden Sie unter <xref:System.Xml.XmlDocumentType.Entities%2A>.  
  
 Die **XmlAttributeCollection** stammt aus **XmlNamedNodeMap** und nur Attribute geändert werden kann, während Notationen und Entitäten schreibgeschützt sind. Mithilfe der **XmlNamedNodeMap** für die Attribute, können Sie den Knoten für diese Attribute ausgehend von deren XML-Namen abrufen. Dies ist eine einfache Methode zum Bearbeiten der Attributauflistung eines Elementknotens. Dieser Vergleich dazu wird direkt mit **XmlNodeList**, dem implementiert außerdem die **IEnumerable** -Schnittstelle, jedoch mit einem Indexaccessor und keine Zeichenfolge. Die **RemoveNamedItem** und **SetNamedItem** Methoden dienen nur anhand einer **XmlAttributeCollection**. Hinzufügen oder Entfernen aus einer attributauflistung, unabhängig davon, ob die **AttributeCollection** oder **XmlNamedNodeMap** Implementierung, ändert die attributauflistung für das Element. Im folgenden Codebeispiel wird gezeigt, wie ein Attribut entfernt und wie ein neues Attribut erstellt wird.  
  
```vb  
Imports System  
Imports System.Xml  
  
Class test  
  
    Public Shared Sub Main()  
        Dim doc As New XmlDocument()  
        doc.LoadXml("<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> ")  
  
        ' Get the attributes of node "child2 "  
        Dim ac As XmlAttributeCollection = doc.DocumentElement.ChildNodes(1).Attributes  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
        Dim i As Integer  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Get the 'attr1' from child1.  
        Dim attr As XmlAttribute = doc.DocumentElement.ChildNodes(0).Attributes(0)  
  
        ' Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem(attr)  
  
        ''attr1' will be removed from 'child1' and added to 'child2'.  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
        ' Create a new attribute and add to the collection.  
        Dim attr2 As XmlAttribute = doc.CreateAttribute("attr4")  
        attr2.Value = "val4"  
        ac.SetNamedItem(attr2)  
  
        ' Print out the number of attributes and their names.  
        Console.WriteLine(("Number of Attributes: " + ac.Count))  
  
        For i = 0 To ac.Count - 1  
            Console.WriteLine((i + 1 + ".  Attribute Name: '" + ac(i).Name + "'  Attribute Value:  '" + ac(i).Value + "'"))  
        Next i  
    End Sub 'Main  
End Class 'test  
```  
  
```csharp  
using System;  
using System.Xml;  
class test {  
    public static void Main() {  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml( "<root> <child1 attr1='val1' attr2='val2'> text1 </child1> <child2 attr3='val3'> text2 </child2> </root> " );  
  
        // Get the attributes of node "child2"  
        XmlAttributeCollection ac = doc.DocumentElement.ChildNodes[1].Attributes;  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );  
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Get the 'attr1' from child1.  
        XmlAttribute attr = doc.DocumentElement.ChildNodes[0].Attributes[0];  
  
        // Add this attribute to the attributecollection "ac".  
        ac.SetNamedItem( attr );  
  
        // 'attr1' will be removed from 'child1' and added to 'child2'.  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );   
  
        // Create a new attribute and add to the collection.  
        XmlAttribute attr2 = doc.CreateAttribute( "attr4" );  
        attr2.Value = "val4";  
        ac.SetNamedItem( attr2 );  
  
        // Print out the number of attributes and their names.  
        Console.WriteLine( "Number of Attributes: "+ac.Count );          
        for( int i = 0; i < ac.Count; i++ )  
            Console.WriteLine( (i+1) + ".  Attribute Name: '" +ac[i].Name+ "'  Attribute Value:  '"+ ac[i].Value +"'" );           
  
    }  
}  
```  
  
 Um ein weiteres Codebeispiel finden Sie unter dem zeigt ein Attribut aus entfernt wird ein **AttributeCollection**, finden Sie unter [XmlNamedNodeMap.RemoveNamedItem-Methode](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem). Weitere Informationen über die Methoden und Eigenschaften finden Sie unter [XmlNamedNodeMap-Member](AllMembers.T:System.Xml.XmlNamedNodeMap).  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
