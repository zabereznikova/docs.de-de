---
title: "Ändern von Namespacedeklarationen in einem XML-Dokument"
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
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="7f76f-102">Ändern von Namespacedeklarationen in einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="7f76f-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="7f76f-103">Die **XmlDocument** macht Namespacedeklarationen und **Xmlns** Attribute als Teil des Dokumentobjektmodells.</span><span class="sxs-lookup"><span data-stu-id="7f76f-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="7f76f-104">Diese werden gespeichert, der **XmlDocument**, sodass, wenn Sie das Dokument zu speichern, können sie den Speicherort dieser Attribute beibehalten.</span><span class="sxs-lookup"><span data-stu-id="7f76f-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="7f76f-105">Änderung dieser Attribute hat keine Auswirkung auf die **Namen**, **NamespaceURI**, und **Präfix** Eigenschaften anderer Knoten bereits in der Struktur.</span><span class="sxs-lookup"><span data-stu-id="7f76f-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="7f76f-106">Angenommen, wenn Sie das folgende Dokument laden und dann die `test` Element verfügt über **NamespaceURI**`123.`</span><span class="sxs-lookup"><span data-stu-id="7f76f-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="7f76f-107">Wenn Sie entfernen die `xmlns` -Attribut wie folgt die `test` Element immer noch die **NamespaceURI** von `123`.</span><span class="sxs-lookup"><span data-stu-id="7f76f-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="7f76f-108">Ebenso, wenn Sie ein anderes hinzufügen `xmlns` -Attribut auf die `doc` -Element wie folgt, und dann die `test` Element immer noch **NamespaceURI** `123`.</span><span class="sxs-lookup"><span data-stu-id="7f76f-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="7f76f-109">Aus diesem Grund ändern `xmlns` Attribute haben keinen Einfluss, bis Sie speichern und laden die **XmlDocument** Objekt.</span><span class="sxs-lookup"><span data-stu-id="7f76f-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f76f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f76f-110">See Also</span></span>  
 [<span data-ttu-id="7f76f-111">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="7f76f-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
