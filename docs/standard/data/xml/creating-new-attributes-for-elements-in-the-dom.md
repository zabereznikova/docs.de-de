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
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="038bb-102">Erstellen von neuen Attributen für Elemente im Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="038bb-102">Creating New Attributes for Elements in the DOM</span></span>
<span data-ttu-id="038bb-103">Erstellen von neuen Attributen unterscheidet sich vom Erstellen anderer Knotentypen, da Attribute keine Knoten sind, jedoch sind Eigenschaften eines Elementknotens und sind in enthalten eine **XmlAttributeCollection** mit dem Element verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="038bb-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="038bb-104">Es gibt verschiedene Möglichkeiten, ein Attribut zu erstellen und an ein Element anzuhängen:</span><span class="sxs-lookup"><span data-stu-id="038bb-104">There are multiple ways to create an attribute and attach it to an element:</span></span>  
  
-   <span data-ttu-id="038bb-105">Den Elementknoten abrufen und verwenden Sie **SetAttribute** der attributauflistung dieses Elements ein Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="038bb-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>  
  
-   <span data-ttu-id="038bb-106">Erstellen einer **XmlAttribute** Knoten unter Verwendung der **CreateAttribute** -Methode, den Elementknoten abrufen, verwenden Sie **SetAttributeNode** auf den Knoten der attributauflistung, hinzufügen Element.</span><span class="sxs-lookup"><span data-stu-id="038bb-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>  
  
 <span data-ttu-id="038bb-107">Im folgende Beispiel wird gezeigt, wie ein Attribut hinzufügen, um ein Element mit dem **SetAttribute** Methode.</span><span class="sxs-lookup"><span data-stu-id="038bb-107">The following example shows how to add an attribute to an element using the **SetAttribute** method.</span></span>  
  
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
  
 <span data-ttu-id="038bb-108">Das folgende Beispiel zeigt ein neues Attribut erstellt wird, mithilfe der **CreateAttribute** Methode.</span><span class="sxs-lookup"><span data-stu-id="038bb-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="038bb-109">Anschließend wird das Attribut der attributauflistung hinzugefügt der **Buch** Element mit dem **SetAttributeNode** Methode.</span><span class="sxs-lookup"><span data-stu-id="038bb-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>  
  
 <span data-ttu-id="038bb-110">Mit dem folgenden XML-Code </span><span class="sxs-lookup"><span data-stu-id="038bb-110">Given the following XML:</span></span>  
  
```xml  
<book genre='novel' ISBN='1-861001-57-5'>  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="038bb-111">erstellen Sie ein neues Attribut. Geben Sie ihm einen Wert </span><span class="sxs-lookup"><span data-stu-id="038bb-111">create a new attribute and give it a value:</span></span>  
  
```vb  
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")  
   attr.Value = "WorldWide Publishing"  
```  
  
```csharp  
XmlAttribute attr = doc.CreateAttribute("publisher");  
attr.Value = "WorldWide Publishing";  
```  
  
 <span data-ttu-id="038bb-112">, und fügen Sie es an das Element an</span><span class="sxs-lookup"><span data-stu-id="038bb-112">and attach it to the element:</span></span>  
  
```vb  
doc.DocumentElement.SetAttributeNode(attr)  
```  
  
```csharp  
doc.DocumentElement.SetAttributeNode(attr);  
```  
  
 <span data-ttu-id="038bb-113">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="038bb-113">**Output**</span></span>  
  
```xml  
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">  
<title>Pride And Prejudice</title>  
</book>  
```  
  
 <span data-ttu-id="038bb-114">Der vollständigen Beispielcode finden Sie unter <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="038bb-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>  
  
 <span data-ttu-id="038bb-115">Sie können auch erstellen eine **XmlAttribute** Knoten und Verwenden der **InsertBefore** oder **InsertAfter** Methoden, um sie in der entsprechenden Position in der Auflistung einzufügen.</span><span class="sxs-lookup"><span data-stu-id="038bb-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="038bb-116">Wenn ein Attribut mit demselben Namen bereits vorhanden ist, in der attributauflistung der vorhandenen ist **XmlAttribute** Knoten aus der Auflistung und der neuen entfernt **XmlAttribute** Knoten eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="038bb-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="038bb-117">Dies führt die gleiche Weise wie die **SetAttribute** Methode.</span><span class="sxs-lookup"><span data-stu-id="038bb-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="038bb-118">Diese Methoden erfordern als Parameter einen vorhandenen Knoten als Bezugspunkt möchten die **InsertBefore** und **InsertAfter**.</span><span class="sxs-lookup"><span data-stu-id="038bb-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="038bb-119">Wenn Sie keinen Referenzknoten, der angibt, wo den neuen Knoten, der Standardwert für eingefügt angeben der **InsertAfter** Methode besteht darin, den neuen Knoten am Anfang der Auflistung eingefügt.</span><span class="sxs-lookup"><span data-stu-id="038bb-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="038bb-120">Die Standardposition für die **InsertBefore**, wenn kein Referenzknoten angegeben wird, wird am Ende der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="038bb-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>  
  
 <span data-ttu-id="038bb-121">Wenn Sie erstellt ein **XmlNamedNodeMap** von Attributen, können Sie ein Attribut mit Namen hinzufügen der <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="038bb-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>.</span></span> <span data-ttu-id="038bb-122">Weitere Informationen finden Sie unter [Knotenauflistungen in "NamedNodeMaps" und "NodeLists"](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span><span class="sxs-lookup"><span data-stu-id="038bb-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md).</span></span>  
  
## <a name="default-attributes"></a><span data-ttu-id="038bb-123">Standardattribute</span><span class="sxs-lookup"><span data-stu-id="038bb-123">Default Attributes</span></span>  
 <span data-ttu-id="038bb-124">Wenn Sie ein Element erstellen, das gemäß Deklaration ein Standardattribut aufweist, wird durch das Dokumentobjektmodell (DOM) ein neues Standardattribut mit seinem Standardwert erstellt und an das Element angehängt.</span><span class="sxs-lookup"><span data-stu-id="038bb-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="038bb-125">Gleichzeitig werden die untergeordneten Knoten des Standardattributs erstellt.</span><span class="sxs-lookup"><span data-stu-id="038bb-125">The child nodes of the default attribute are also created at this time.</span></span>  
  
## <a name="attribute-child-nodes"></a><span data-ttu-id="038bb-126">Untergeordnete Knoten von Attributen</span><span class="sxs-lookup"><span data-stu-id="038bb-126">Attribute Child Nodes</span></span>  
 <span data-ttu-id="038bb-127">Die Werte eines Attributknotens werden zu dessen untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="038bb-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="038bb-128">Es gibt nur zwei Typen von zulässigen untergeordneten Knoten: **XmlText** Knoten, und **XmlEntityReference** Knoten.</span><span class="sxs-lookup"><span data-stu-id="038bb-128">There are only two types of valid child nodes: **XmlText** nodes, and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="038bb-129">Dies sind die untergeordneten Knoten in dem Sinne, dass Methoden wie z. B. **FirstChild** und **LastChild** als untergeordnete Knoten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="038bb-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="038bb-130">Dieses Merkmal eines Attributs mit untergeordneten Knoten ist von Bedeutung, wenn Sie versuchen, Attribute oder untergeordnete Knoten von Attributen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="038bb-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="038bb-131">Weitere Informationen finden Sie unter [Entfernen von Attributen aus einem Elementknoten im DOKUMENTOBJEKTMODELL](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="038bb-131">For more information, see [Removing Attributes from an Element Node in the DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="038bb-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="038bb-132">See Also</span></span>  
 [<span data-ttu-id="038bb-133">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="038bb-133">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
