---
title: Ändern der Eigenschaften von Namespacepräfixen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
ms.openlocfilehash: e6b811d58ef9d98c51e9a45a46a1965c4fa12b55
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711115"
---
# <a name="changing-namespace-prefix-properties"></a><span data-ttu-id="5626a-102">Ändern der Eigenschaften von Namespacepräfixen</span><span class="sxs-lookup"><span data-stu-id="5626a-102">Changing Namespace Prefix Properties</span></span>
<span data-ttu-id="5626a-103">Mit der **XmlNode**-Klasse können Sie das Namespacepräfix ändern, das mit einem bestimmten Knoten verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="5626a-103">The **XmlNode** class allows you to change the namespace prefix associated with a given node.</span></span> <span data-ttu-id="5626a-104">Im folgenden Code wird beispielsweise die Änderung des Präfixes eines Elements dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5626a-104">For example, the following code shows the prefix of an element being changed.</span></span>  
  
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
  
 <span data-ttu-id="5626a-105">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="5626a-105">**Output**</span></span>  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 <span data-ttu-id="5626a-106">Wenn Sie das Präfix eines Knotens ändern, ändert sich dessen Namespace dadurch nicht.</span><span class="sxs-lookup"><span data-stu-id="5626a-106">Changing the prefix of a node does not change its namespace.</span></span> <span data-ttu-id="5626a-107">Der Namespace kann nur bei der Erstellung des Knotens festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5626a-107">The namespace can only be set when the node is created.</span></span> <span data-ttu-id="5626a-108">Wenn die Struktur erhalten bleiben soll, können neue Namespaceattribute nicht mit übernommen werden, damit die Anforderungen für das festgelegte Präfix erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="5626a-108">When you persist the tree, new namespace attributes may be persisted out to satisfy the prefix you set.</span></span> <span data-ttu-id="5626a-109">Wenn der neue Namespace nicht erstellt werden kann, wird das Präfix geändert, sodass der Knoten seinen lokalen Namen und Namespace beibehält.</span><span class="sxs-lookup"><span data-stu-id="5626a-109">If the new namespace cannot be created, then the prefix is changed so the node preserves its local name and namespace.</span></span> <span data-ttu-id="5626a-110">Im folgenden Beispiel wird dargestellt, wie ein Namespaceattribut hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5626a-110">The following example shows a namespace attribute being added.</span></span>  
  
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
  
 <span data-ttu-id="5626a-111">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="5626a-111">**Output**</span></span>  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 <span data-ttu-id="5626a-112">Wenn die Struktur als Folge des Aufrufs von **doc.InnerXml** in Form einer Zeichenfolge erhalten blieb, wurde das `xmlns:a='123'`-Attribut hinzugefügt, damit der Namespace des `test`-Elements beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="5626a-112">When the tree was persisted to a string as a result of the call to **doc.InnerXml**, the `xmlns:a='123'` attribute was added to preserve the namespace of the `test` element.</span></span> <span data-ttu-id="5626a-113">Er war `'123'` und bleibt `'123'`.</span><span class="sxs-lookup"><span data-stu-id="5626a-113">It was `'123'`, and it remained `'123'`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5626a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5626a-114">See also</span></span>

- [<span data-ttu-id="5626a-115">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="5626a-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
