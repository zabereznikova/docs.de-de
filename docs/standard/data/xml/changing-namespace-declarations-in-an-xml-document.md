---
title: Ändern von Namespacedeklarationen in einem XML-Dokument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: 95f9c6301f656ad4da5edcfb66521589b9195114
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725364"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="cb65b-102">Ändern von Namespacedeklarationen in einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="cb65b-102">Changing Namespace Declarations in an XML Document</span></span>

<span data-ttu-id="cb65b-103">Das **XmlDocument** macht Namespacedeklarationen und **xmlns**-Attribute als Teil des Dokumentobjektmodells verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cb65b-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="cb65b-104">Diese werden im **XmlDocument** gespeichert, sodass der Speicherort dieser Attribute beim Speichern des Dokuments beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb65b-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="cb65b-105">Eine Änderung dieser Attribute hat keine Auswirkungen auf die Eigenschaften **Name**, **NamespaceURI** und **Prefix** anderer Knoten, die bereits in der Struktur vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cb65b-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="cb65b-106">Wenn Sie z. B. das folgende Dokument laden, weist das `test`-Element den **NamespaceURI** `123.` auf.</span><span class="sxs-lookup"><span data-stu-id="cb65b-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="cb65b-107">Wenn Sie das `xmlns`-Attribut wie folgt entfernen, weist das `test`-Element weiterhin den **NamespaceURI**`123` auf.</span><span class="sxs-lookup"><span data-stu-id="cb65b-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="cb65b-108">Gleichermaßen weist das `test`-Element weiterhin den **NamespaceURI** `123` auf, wenn Sie dem `doc`-Element wie folgt ein anderes `xmlns`-Attribut hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cb65b-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="cb65b-109">Änderungen an `xmlns`-Attributen haben daher keine Auswirkungen, solange Sie das **XmlDocument**-Objekt nicht speichern und erneut laden.</span><span class="sxs-lookup"><span data-stu-id="cb65b-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb65b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb65b-110">See also</span></span>

- [<span data-ttu-id="cb65b-111">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="cb65b-111">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
