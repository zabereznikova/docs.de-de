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
# <a name="unordered-node-retrieval-by-name-or-index"></a><span data-ttu-id="29d4e-102">Abrufen von ungeordneten Knoten anhand des Namens oder Indexes</span><span class="sxs-lookup"><span data-stu-id="29d4e-102">Unordered Node Retrieval by Name or Index</span></span>
<span data-ttu-id="29d4e-103">Die **XmlNamedNodeMap** wird beschrieben, in der Spezifikation World Wide Web Consortium (W3C) als "NamedNodeMap" durch und ist erforderlich, um eine ungeordnete Gruppe von Knoten mit der Fähigkeit zum Verweisknoten nach Name oder Index zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="29d4e-103">The **XmlNamedNodeMap** is described in the World Wide Web Consortium (W3C) specification as the NamedNodeMap and is required to handle an unordered set of nodes with the ability to reference nodes by their name or index.</span></span> <span data-ttu-id="29d4e-104">Die einzige Möglichkeit haben Sie Zugriff auf eine **XmlNamedNodeMap** ist, wenn ein **XmlNamedNodeMap** über eine Methode oder Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="29d4e-104">The only way you have access to an **XmlNamedNodeMap** is when an **XmlNamedNodeMap** is returned through a method or property.</span></span> <span data-ttu-id="29d4e-105">Es gibt drei Methoden oder Eigenschaften, die Zurückgeben einer **XmlNamedNodeMap**:</span><span class="sxs-lookup"><span data-stu-id="29d4e-105">There are three methods or properties that return an **XmlNamedNodeMap**:</span></span>  
  
-   <span data-ttu-id="29d4e-106">XmlElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="29d4e-106">XmlElement.Attributes</span></span>  
  
-   <span data-ttu-id="29d4e-107">XmlDocumentType.Entities</span><span class="sxs-lookup"><span data-stu-id="29d4e-107">XmlDocumentType.Entities</span></span>  
  
-   <span data-ttu-id="29d4e-108">XmlDocumentType.Notations</span><span class="sxs-lookup"><span data-stu-id="29d4e-108">XmlDocumentType.Notations</span></span>  
  
 <span data-ttu-id="29d4e-109">Z. B. die **XmlDocumentType.Entities** Eigenschaft ruft die Auflistung der **XmlEntity** Knoten in der Dokumenttypdeklaration deklarierte.</span><span class="sxs-lookup"><span data-stu-id="29d4e-109">For example, the **XmlDocumentType.Entities** property gets the collection of **XmlEntity** nodes declared in the document type declaration.</span></span> <span data-ttu-id="29d4e-110">Diese Auflistung wird zurückgegeben, als ein **XmlNamedNodeMap**, und Sie können die Auflistung mit dem Durchlaufen der **Anzahl** Eigenschaft und der Anzeige Entitätsinformationen.</span><span class="sxs-lookup"><span data-stu-id="29d4e-110">This collection is returned as an **XmlNamedNodeMap**, and you can iterate through the collection with the use of the **Count** property and display entity information.</span></span> <span data-ttu-id="29d4e-111">Ein Beispiel für die Iteration durch eine **XmlNamedNodeMap**, finden Sie unter <xref:System.Xml.XmlDocumentType.Entities%2A>.</span><span class="sxs-lookup"><span data-stu-id="29d4e-111">For an example of iterating through an **XmlNamedNodeMap**, see <xref:System.Xml.XmlDocumentType.Entities%2A>.</span></span>  
  
 <span data-ttu-id="29d4e-112">Die **XmlAttributeCollection** stammt aus **XmlNamedNodeMap** und nur Attribute geändert werden kann, während Notationen und Entitäten schreibgeschützt sind.</span><span class="sxs-lookup"><span data-stu-id="29d4e-112">The **XmlAttributeCollection** is derived from **XmlNamedNodeMap** and only attributes are modifiable, while notations and entities are read-only.</span></span> <span data-ttu-id="29d4e-113">Mithilfe der **XmlNamedNodeMap** für die Attribute, können Sie den Knoten für diese Attribute ausgehend von deren XML-Namen abrufen.</span><span class="sxs-lookup"><span data-stu-id="29d4e-113">Using the **XmlNamedNodeMap** for the attributes, you can get nodes for those attributes based on their XML names.</span></span> <span data-ttu-id="29d4e-114">Dies ist eine einfache Methode zum Bearbeiten der Attributauflistung eines Elementknotens.</span><span class="sxs-lookup"><span data-stu-id="29d4e-114">This provides an easy method for manipulating the collection of attributes on an element node.</span></span> <span data-ttu-id="29d4e-115">Dieser Vergleich dazu wird direkt mit **XmlNodeList**, dem implementiert außerdem die **IEnumerable** -Schnittstelle, jedoch mit einem Indexaccessor und keine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="29d4e-115">This can be contrasted directly with **XmlNodeList**, which also implements the **IEnumerable** interface, but with an index accessor rather than a string.</span></span> <span data-ttu-id="29d4e-116">Die **RemoveNamedItem** und **SetNamedItem** Methoden dienen nur anhand einer **XmlAttributeCollection**.</span><span class="sxs-lookup"><span data-stu-id="29d4e-116">The **RemoveNamedItem** and **SetNamedItem** methods are only used against an **XmlAttributeCollection**.</span></span> <span data-ttu-id="29d4e-117">Hinzufügen oder Entfernen aus einer attributauflistung, unabhängig davon, ob die **AttributeCollection** oder **XmlNamedNodeMap** Implementierung, ändert die attributauflistung für das Element.</span><span class="sxs-lookup"><span data-stu-id="29d4e-117">Adding or removing from an attribute collection, whether using the **AttributeCollection** or the **XmlNamedNodeMap** implementation, modifies the attribute collection on the element.</span></span> <span data-ttu-id="29d4e-118">Im folgenden Codebeispiel wird gezeigt, wie ein Attribut entfernt und wie ein neues Attribut erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="29d4e-118">The following code example shows how to move an attribute and create a new attribute.</span></span>  
  
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
  
 <span data-ttu-id="29d4e-119">Um ein weiteres Codebeispiel finden Sie unter dem zeigt ein Attribut aus entfernt wird ein **AttributeCollection**, finden Sie unter [XmlNamedNodeMap.RemoveNamedItem-Methode](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem).</span><span class="sxs-lookup"><span data-stu-id="29d4e-119">To see an additional code example which shows an attribute being removed from an **AttributeCollection**, see [XmlNamedNodeMap.RemoveNamedItem Method](Overload:System.Xml.XmlNamedNodeMap.RemoveNamedItem).</span></span> <span data-ttu-id="29d4e-120">Weitere Informationen über die Methoden und Eigenschaften finden Sie unter [XmlNamedNodeMap-Member](AllMembers.T:System.Xml.XmlNamedNodeMap).</span><span class="sxs-lookup"><span data-stu-id="29d4e-120">For more information on the methods and properties, see [XmlNamedNodeMap Members](AllMembers.T:System.Xml.XmlNamedNodeMap).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d4e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29d4e-121">See Also</span></span>  
 [<span data-ttu-id="29d4e-122">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="29d4e-122">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
