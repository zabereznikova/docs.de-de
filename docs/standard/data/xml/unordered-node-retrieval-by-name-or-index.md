---
title: Abrufen von ungeordneten Knoten anhand des Namens oder Indexes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
ms.openlocfilehash: c3358f6cca27fbe61ba2b59fe6f2eb5df81c91ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675645"
---
# <a name="unordered-node-retrieval-by-name-or-index"></a>Abrufen von ungeordneten Knoten anhand des Namens oder Indexes

**XmlNamedNodeMap** wird in der W3C-Spezifikation (World Wide Web Consortium) als „NamedNodeMap“ beschrieben und muss eine ungeordnete Gruppe von Knoten behandeln können und auf Knoten nach Name oder Index verweisen können. Zugriff auf eine **XmlNamedNodeMap** ist nur dann möglich, wenn eine **XmlNamedNodeMap** von einer Methode oder einer Eigenschaft zurückgegeben wurde. Es gibt drei Methoden bzw. Eigenschaften, die eine **XmlNamedNodeMap** zurückgeben:  
  
- XmlElement.Attributes  
  
- XmlDocumentType.Entities  
  
- XmlDocumentType.Notations  
  
 Die **XmlDocumentType.Entities**-Eigenschaft ruft z.B. die in der Dokumenttypdeklaration deklarierte Auflistung von **XmlEntity**-Knoten ab. Diese Auflistung wird als **XmlNamedNodeMap** zurückgegeben, und Sie können sie mithilfe der **Count**-Eigenschaft durchlaufen und Informationen über die Entitäten anzeigen lassen. Ein Beispiel für das Durchlaufen einer **XmlNamedNodeMap** finden Sie unter <xref:System.Xml.XmlDocumentType.Entities%2A>.  
  
 **XmlAttributeCollection** wird von **XmlNamedNodeMap** abgeleitet. Es können nur Attribute geändert werden. Notationen und Entitäten sind schreibgeschützt. Unter Verwendung von **XmlNamedNodeMap** für die Attribute können Sie Knoten für diese Attribute ausgehend von deren XML-Namen abrufen. Dies ist eine einfache Methode zum Bearbeiten der Attributauflistung eines Elementknotens. Im Vergleich dazu wird bei **XmlNodeList** ebenfalls die **IEnumerable**-Schnittstelle implementiert, jedoch mit einer Indexzugriffsmethode und nicht mit einer Zeichenfolge. Die **RemoveNamedItem**-Methode und die **SetNamedItem**-Methode werden nur bei einer **XmlAttributeCollection** verwendet. Durch Hinzufügen oder Entfernen von Elementen in einer Attributauflistung, sei es mit der **AttributeCollection**- oder der **XmlNamedNodeMap**-Implementierung, wird die Attributauflistung im betreffenden Element verändert. Im folgenden Codebeispiel wird gezeigt, wie ein Attribut entfernt und wie ein neues Attribut erstellt wird.  
  
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
  
 Ein weiteres Codebeispiel zum Entfernen eines Attributs aus einer **AttributeCollection** finden Sie unter [XmlNamedNodeMap.RemoveNamedItem-Methode](xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A). Weitere Informationen über die Methoden und Eigenschaften finden Sie unter [XmlNamedNodeMap-Member](xref:System.Xml.XmlNamedNodeMap).  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
