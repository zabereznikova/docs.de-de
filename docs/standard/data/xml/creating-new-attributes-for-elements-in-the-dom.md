---
title: Erstellen von neuen Attributen für Elemente im Dokumentobjektmodell
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: dd6dc920-b011-418a-b3db-f1580a7d9251
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9445f16b6470b1d2066fcae749b1623ec5e11ac
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138940"
---
# <a name="creating-new-attributes-for-elements-in-the-dom"></a><span data-ttu-id="4e8dd-102">Erstellen von neuen Attributen für Elemente im Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="4e8dd-102">Creating New Attributes for Elements in the DOM</span></span>

<span data-ttu-id="4e8dd-103">Das Erstellen von neuen Attributen unterscheidet sich vom Erstellen anderer Knotentypen, da Attribute keine Knoten sind, sondern Eigenschaften eines Elementknotens, und in einer mit dem Element verknüpften **XmlAttributeCollection** enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-103">Creating new attributes is different than creating other node types, because attributes are not nodes, but are properties of an element node and are contained in an **XmlAttributeCollection** associated with the element.</span></span> <span data-ttu-id="4e8dd-104">Es gibt verschiedene Möglichkeiten, ein Attribut zu erstellen und an ein Element anzuhängen:</span><span class="sxs-lookup"><span data-stu-id="4e8dd-104">There are multiple ways to create an attribute and attach it to an element:</span></span>

- <span data-ttu-id="4e8dd-105">Den Elementknoten abrufen und dann mit **SetAttribute** der Attributauflistung dieses Elements ein Attribut hinzufügen</span><span class="sxs-lookup"><span data-stu-id="4e8dd-105">Get the element node and use **SetAttribute** to add an attribute to the attribute collection of that element.</span></span>

- <span data-ttu-id="4e8dd-106">Mit der **CreateAttribute**-Methode einen **XmlAttribute**-Knoten erstellen, den Elementknoten abrufen und dann mit **SetAttributeNode** den Knoten der Attributauflistung dieses Elements hinzufügen</span><span class="sxs-lookup"><span data-stu-id="4e8dd-106">Create an **XmlAttribute** node using the **CreateAttribute** method, get the element node, then use **SetAttributeNode** to add the node to the attribute collection of that element.</span></span>

<span data-ttu-id="4e8dd-107">Im folgenden Beispiel wird gezeigt, wie einem Element mithilfe der Methode " **tstribute** " ein Attribut hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="4e8dd-107">The following example shows how to add an attribute to an element using the **SetAttribute** method:</span></span>

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As New XmlDocument()
        doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" & _
                    "<title>Pride And Prejudice</title>" & _
                    "</book>")
        Dim root As XmlElement = doc.DocumentElement

        ' Add a new attribute.
        root.SetAttribute("genre", "urn:samples", "novel")

        Console.WriteLine("Display the modified XML...")
        Console.WriteLine(doc.InnerXml)
    End Sub
End Class
```  
  
```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{
    public static void Main()
    {
        var doc = new XmlDocument();
        doc.LoadXml("<book xmlns:bk='urn:samples' bk:ISBN='1-861001-57-5'>" +
                    "<title>Pride And Prejudice</title>" +
                    "</book>");
        XmlElement root = doc.DocumentElement;

        // Add a new attribute.
        root.SetAttribute("genre", "urn:samples", "novel");

        Console.WriteLine("Display the modified XML...");
        Console.WriteLine(doc.InnerXml);
    }
}
```

<span data-ttu-id="4e8dd-108">Im folgenden Beispiel wird dargestellt, wie mit der **CreateAttribute**-Methode ein neues Attribut erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-108">The following example shows a new attribute being created using the **CreateAttribute** method.</span></span> <span data-ttu-id="4e8dd-109">Anschließend wird das Attribut mithilfe der **SetAttributeNode**-Methode der Attributauflistung des **book**-Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-109">It then shows the attribute added to the attribute collection of the **book** element using the **SetAttributeNode** method.</span></span>

<span data-ttu-id="4e8dd-110">Mit dem folgenden XML-Code</span><span class="sxs-lookup"><span data-stu-id="4e8dd-110">Given the following XML:</span></span>
  
```xml
<book genre='novel' ISBN='1-861001-57-5'>
<title>Pride And Prejudice</title>
</book>
```

<span data-ttu-id="4e8dd-111">erstellen Sie ein neues Attribut. Geben Sie ihm einen Wert</span><span class="sxs-lookup"><span data-stu-id="4e8dd-111">create a new attribute and give it a value:</span></span>

```vb
Dim attr As XmlAttribute = doc.CreateAttribute("publisher")
attr.Value = "WorldWide Publishing"
```

```csharp
XmlAttribute attr = doc.CreateAttribute("publisher");
attr.Value = "WorldWide Publishing";
```

<span data-ttu-id="4e8dd-112">, und fügen Sie es an das Element an</span><span class="sxs-lookup"><span data-stu-id="4e8dd-112">and attach it to the element:</span></span>

```vb
doc.DocumentElement.SetAttributeNode(attr)
```

```csharp
doc.DocumentElement.SetAttributeNode(attr);
```

<span data-ttu-id="4e8dd-113">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="4e8dd-113">**Output**</span></span>

```xml
<book genre="novel" ISBN="1-861001-57-5" publisher="WorldWide Publishing">
<title>Pride And Prejudice</title>
</book>
```

<span data-ttu-id="4e8dd-114">Das vollständige Codebeispiel finden Sie unter <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-114">The full code sample can be found at <xref:System.Xml.XmlDocument.CreateAttribute%2A>.</span></span>

<span data-ttu-id="4e8dd-115">Sie können auch einen **XmlAttribute**-Knoten erstellen und diesen mit der **InsertBefore**-Methode oder der **InsertAfter**-Methode an der entsprechenden Position in der Auflistung platzieren.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-115">You can also create an **XmlAttribute** node and use the **InsertBefore** or **InsertAfter** methods to place it in the appropriate position in the collection.</span></span> <span data-ttu-id="4e8dd-116">Wenn ein Attribut mit demselben Namen bereits in der Attributauflistung vorhanden ist, wird der bisherige **XmlAttribute**-Knoten aus der Auflistung entfernt, und der neue **XmlAttribute**-Knoten wird eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-116">If an attribute with the same name is already present in the attribute collection, the existing **XmlAttribute** node is removed from the collection and the new **XmlAttribute** node is inserted.</span></span> <span data-ttu-id="4e8dd-117">Dies erfolgt auf die gleiche Weise wie bei der **SetAttribute**-Methode.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-117">This performs the same way as the **SetAttribute** method.</span></span> <span data-ttu-id="4e8dd-118">Diese Methoden erfordern als Parameter einen vorhandenen Knoten, der als Referenzpunkt für die **InsertBefore**-Methode und die **InsertAfter**-Methode dient.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-118">These methods take, as a parameter, an existing node as a reference point to do the **InsertBefore** and **InsertAfter**.</span></span> <span data-ttu-id="4e8dd-119">Wenn Sie keinen Referenzknoten bereitstellen, der angibt, wo der neue Knoten eingefügt werden soll, wird mit der **InsertAfter**-Methode der neue Knoten standardmäßig am Anfang der Auflistung eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-119">If you do not provide a reference node indicating where to insert the new node, the default for the **InsertAfter** method is to insert the new node at the beginning of the collection.</span></span> <span data-ttu-id="4e8dd-120">Die Standardposition für die **InsertBefore**-Methode ist das Ende der Auflistung, wenn kein Referenzknoten angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-120">The default position for the **InsertBefore**, if no reference node is provided, is at the end of the collection.</span></span>

<span data-ttu-id="4e8dd-121">Wenn Sie eine **XmlNamedNodeMap** von Attributen erstellt haben, können Sie mithilfe der <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A>-Methode ein Attribut anhand des Namens hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-121">If you created an **XmlNamedNodeMap** of attributes, you can add an attribute by name using the <xref:System.Xml.XmlNamedNodeMap.SetNamedItem%2A> method.</span></span> <span data-ttu-id="4e8dd-122">Weitere Informationen hierzu finden Sie unter [Knotenauflistungen in „NamedNodeMaps“ und „NodeLists“](node-collections-in-namednodemaps-and-nodelists.md).</span><span class="sxs-lookup"><span data-stu-id="4e8dd-122">For more information, see [Node Collections in NamedNodeMaps and NodeLists](node-collections-in-namednodemaps-and-nodelists.md).</span></span>

## <a name="default-attributes"></a><span data-ttu-id="4e8dd-123">Standard Attribute</span><span class="sxs-lookup"><span data-stu-id="4e8dd-123">Default attributes</span></span>

<span data-ttu-id="4e8dd-124">Wenn Sie ein Element erstellen, das gemäß Deklaration ein Standardattribut aufweist, wird durch das Dokumentobjektmodell (DOM) ein neues Standardattribut mit seinem Standardwert erstellt und an das Element angehängt.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-124">If you create an element that is declared to have a default attribute, then a new default attribute with its default value is created by the XML Document Object Model (DOM) and attached to the element.</span></span> <span data-ttu-id="4e8dd-125">Gleichzeitig werden die untergeordneten Knoten des Standardattributs erstellt.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-125">The child nodes of the default attribute are also created at this time.</span></span>

## <a name="attribute-child-nodes"></a><span data-ttu-id="4e8dd-126">Untergeordnete Attribut Knoten</span><span class="sxs-lookup"><span data-stu-id="4e8dd-126">Attribute child nodes</span></span>

<span data-ttu-id="4e8dd-127">Die Werte eines Attributknotens werden zu dessen untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-127">The value of an attribute node becomes its child nodes.</span></span> <span data-ttu-id="4e8dd-128">Es gibt nur zwei Typen von gültigen untergeordneten Knoten: **XmlText** -Knoten und **XmlEntityReference** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-128">There are only two types of valid child nodes: **XmlText** nodes and **XmlEntityReference** nodes.</span></span> <span data-ttu-id="4e8dd-129">Diese sind dahingehend als untergeordnete Knoten zu betrachten, dass sie von Methoden wie **FirstChild** und **LastChild** als untergeordnete Knoten verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-129">These are child nodes in the sense that methods such as **FirstChild** and **LastChild** process them as child nodes.</span></span> <span data-ttu-id="4e8dd-130">Dieses Merkmal eines Attributs mit untergeordneten Knoten ist von Bedeutung, wenn Sie versuchen, Attribute oder untergeordnete Knoten von Attributen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4e8dd-130">This distinction of an attribute having child nodes is important when trying to remove attributes or attribute child nodes.</span></span> <span data-ttu-id="4e8dd-131">Weitere Informationen hierzu finden Sie unter [Entfernen von Attributen aus einem Elementknoten im DOM](removing-attributes-from-an-element-node-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="4e8dd-131">For more information, see [Removing Attributes from an Element Node in the DOM](removing-attributes-from-an-element-node-in-the-dom.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e8dd-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e8dd-132">See also</span></span>

- [<span data-ttu-id="4e8dd-133">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="4e8dd-133">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
