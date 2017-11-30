---
title: "Ändern der Eigenschaften von Namespacepräfixen"
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
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7ce6e4b705188b9c1d0949703991633e3f450689
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-prefix-properties"></a><span data-ttu-id="60be4-102">Ändern der Eigenschaften von Namespacepräfixen</span><span class="sxs-lookup"><span data-stu-id="60be4-102">Changing Namespace Prefix Properties</span></span>
<span data-ttu-id="60be4-103">Die **XmlNode** -Klasse ermöglicht es Ihnen, die einem bestimmten Knoten zugeordnete Namespacepräfix ändern.</span><span class="sxs-lookup"><span data-stu-id="60be4-103">The **XmlNode** class allows you to change the namespace prefix associated with a given node.</span></span> <span data-ttu-id="60be4-104">Im folgenden Code wird beispielsweise die Änderung des Präfixes eines Elements dargestellt.</span><span class="sxs-lookup"><span data-stu-id="60be4-104">For example, the following code shows the prefix of an element being changed.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="60be4-105">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="60be4-105">**Output**</span></span>  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 <span data-ttu-id="60be4-106">Wenn Sie das Präfix eines Knotens ändern, ändert sich dessen Namespace dadurch nicht.</span><span class="sxs-lookup"><span data-stu-id="60be4-106">Changing the prefix of a node does not change its namespace.</span></span> <span data-ttu-id="60be4-107">Der Namespace kann nur bei der Erstellung des Knotens festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="60be4-107">The namespace can only be set when the node is created.</span></span> <span data-ttu-id="60be4-108">Wenn die Struktur erhalten bleiben soll, können neue Namespaceattribute nicht mit übernommen werden, damit die Anforderungen für das festgelegte Präfix erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="60be4-108">When you persist the tree, new namespace attributes may be persisted out to satisfy the prefix you set.</span></span> <span data-ttu-id="60be4-109">	Wenn der neue Namespace nicht erstellt werden kann, wird das Präfix geändert, sodass der Knoten seinen lokalen Namen und Namespace beibehält.</span><span class="sxs-lookup"><span data-stu-id="60be4-109">If the new namespace cannot be created, then the prefix is changed so the node preserves its local name and namespace.</span></span> <span data-ttu-id="60be4-110">Im folgenden Beispiel wird dargestellt, wie ein Namespaceattribut hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="60be4-110">The following example shows a namespace attribute being added.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="60be4-111">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="60be4-111">**Output**</span></span>  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 <span data-ttu-id="60be4-112">Wenn die Struktur in eine Zeichenfolge als Folge des Aufrufs zum beibehalten wurde **Doc. InnerXml**, `xmlns:a='123'` Attribut wurde hinzugefügt, um den Namespace des erhalten die `test` Element.</span><span class="sxs-lookup"><span data-stu-id="60be4-112">When the tree was persisted to a string as a result of the call to **doc.InnerXml**, the `xmlns:a='123'` attribute was added to preserve the namespace of the `test` element.</span></span> <span data-ttu-id="60be4-113">Er war `'123'` und bleibt `'123'`.</span><span class="sxs-lookup"><span data-stu-id="60be4-113">It was `'123'`, and it remained `'123'`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60be4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60be4-114">See Also</span></span>  
 [<span data-ttu-id="60be4-115">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="60be4-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
