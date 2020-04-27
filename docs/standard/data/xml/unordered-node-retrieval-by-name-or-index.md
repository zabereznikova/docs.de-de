---
title: Abrufen von ungeordneten Knoten anhand des Namens oder Indexes
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2038a90b-92af-4a0a-baaa-08e688d95194
ms.openlocfilehash: 55ea0e31bb8a2863dc0e0eb30f6ca5700c3110b8
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155736"
---
# <a name="unordered-node-retrieval-by-name-or-index"></a><span data-ttu-id="feead-102">Abrufen von ungeordneten Knoten anhand des Namens oder Indexes</span><span class="sxs-lookup"><span data-stu-id="feead-102">Unordered Node Retrieval by Name or Index</span></span>
<span data-ttu-id="feead-103">**XmlNamedNodeMap** wird in der W3C-Spezifikation (World Wide Web Consortium) als „NamedNodeMap“ beschrieben und muss eine ungeordnete Gruppe von Knoten behandeln können und auf Knoten nach Name oder Index verweisen können.</span><span class="sxs-lookup"><span data-stu-id="feead-103">The **XmlNamedNodeMap** is described in the World Wide Web Consortium (W3C) specification as the NamedNodeMap and is required to handle an unordered set of nodes with the ability to reference nodes by their name or index.</span></span> <span data-ttu-id="feead-104">Zugriff auf eine **XmlNamedNodeMap** ist nur dann möglich, wenn eine **XmlNamedNodeMap** von einer Methode oder einer Eigenschaft zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="feead-104">The only way you have access to an **XmlNamedNodeMap** is when an **XmlNamedNodeMap** is returned through a method or property.</span></span> <span data-ttu-id="feead-105">Es gibt drei Methoden bzw. Eigenschaften, die eine **XmlNamedNodeMap** zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="feead-105">There are three methods or properties that return an **XmlNamedNodeMap**:</span></span>  
  
- <span data-ttu-id="feead-106">XmlElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="feead-106">XmlElement.Attributes</span></span>  
  
- <span data-ttu-id="feead-107">XmlDocumentType.Entities</span><span class="sxs-lookup"><span data-stu-id="feead-107">XmlDocumentType.Entities</span></span>  
  
- <span data-ttu-id="feead-108">XmlDocumentType.Notations</span><span class="sxs-lookup"><span data-stu-id="feead-108">XmlDocumentType.Notations</span></span>  
  
 <span data-ttu-id="feead-109">Die **XmlDocumentType.Entities**-Eigenschaft ruft z.B. die in der Dokumenttypdeklaration deklarierte Auflistung von **XmlEntity**-Knoten ab.</span><span class="sxs-lookup"><span data-stu-id="feead-109">For example, the **XmlDocumentType.Entities** property gets the collection of **XmlEntity** nodes declared in the document type declaration.</span></span> <span data-ttu-id="feead-110">Diese Auflistung wird als **XmlNamedNodeMap** zurückgegeben, und Sie können sie mithilfe der **Count**-Eigenschaft durchlaufen und Informationen über die Entitäten anzeigen lassen.</span><span class="sxs-lookup"><span data-stu-id="feead-110">This collection is returned as an **XmlNamedNodeMap**, and you can iterate through the collection with the use of the **Count** property and display entity information.</span></span> <span data-ttu-id="feead-111">Ein Beispiel für das Durchlaufen einer **XmlNamedNodeMap** finden Sie unter <xref:System.Xml.XmlDocumentType.Entities%2A>.</span><span class="sxs-lookup"><span data-stu-id="feead-111">For an example of iterating through an **XmlNamedNodeMap**, see <xref:System.Xml.XmlDocumentType.Entities%2A>.</span></span>  
  
 <span data-ttu-id="feead-112">**XmlAttributeCollection** wird von **XmlNamedNodeMap** abgeleitet. Es können nur Attribute geändert werden. Notationen und Entitäten sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="feead-112">The **XmlAttributeCollection** is derived from **XmlNamedNodeMap** and only attributes are modifiable, while notations and entities are read-only.</span></span> <span data-ttu-id="feead-113">Unter Verwendung von **XmlNamedNodeMap** für die Attribute können Sie Knoten für diese Attribute ausgehend von deren XML-Namen abrufen.</span><span class="sxs-lookup"><span data-stu-id="feead-113">Using the **XmlNamedNodeMap** for the attributes, you can get nodes for those attributes based on their XML names.</span></span> <span data-ttu-id="feead-114">Dies ist eine einfache Methode zum Bearbeiten der Attributauflistung eines Elementknotens.</span><span class="sxs-lookup"><span data-stu-id="feead-114">This provides an easy method for manipulating the collection of attributes on an element node.</span></span> <span data-ttu-id="feead-115">Im Vergleich dazu wird bei **XmlNodeList** ebenfalls die **IEnumerable**-Schnittstelle implementiert, jedoch mit einer Indexzugriffsmethode und nicht mit einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="feead-115">This can be contrasted directly with **XmlNodeList**, which also implements the **IEnumerable** interface, but with an index accessor rather than a string.</span></span> <span data-ttu-id="feead-116">Die **RemoveNamedItem**-Methode und die **SetNamedItem**-Methode werden nur bei einer **XmlAttributeCollection** verwendet.</span><span class="sxs-lookup"><span data-stu-id="feead-116">The **RemoveNamedItem** and **SetNamedItem** methods are only used against an **XmlAttributeCollection**.</span></span> <span data-ttu-id="feead-117">Durch Hinzufügen oder Entfernen von Elementen in einer Attributauflistung, sei es mit der **AttributeCollection**- oder der **XmlNamedNodeMap**-Implementierung, wird die Attributauflistung im betreffenden Element verändert.</span><span class="sxs-lookup"><span data-stu-id="feead-117">Adding or removing from an attribute collection, whether using the **AttributeCollection** or the **XmlNamedNodeMap** implementation, modifies the attribute collection on the element.</span></span> <span data-ttu-id="feead-118">Im folgenden Codebeispiel wird gezeigt, wie ein Attribut entfernt und wie ein neues Attribut erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="feead-118">The following code example shows how to move an attribute and create a new attribute.</span></span>  
  
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
  
 <span data-ttu-id="feead-119">Ein weiteres Codebeispiel zum Entfernen eines Attributs aus einer **AttributeCollection** finden Sie unter [XmlNamedNodeMap.RemoveNamedItem-Methode](xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A).</span><span class="sxs-lookup"><span data-stu-id="feead-119">To see an additional code example which shows an attribute being removed from an **AttributeCollection**, see [XmlNamedNodeMap.RemoveNamedItem Method](xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A).</span></span> <span data-ttu-id="feead-120">Weitere Informationen über die Methoden und Eigenschaften finden Sie unter [XmlNamedNodeMap-Member](xref:System.Xml.XmlNamedNodeMap).</span><span class="sxs-lookup"><span data-stu-id="feead-120">For more information on the methods and properties, see [XmlNamedNodeMap Members](xref:System.Xml.XmlNamedNodeMap).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feead-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="feead-121">See also</span></span>

- [<span data-ttu-id="feead-122">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="feead-122">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
