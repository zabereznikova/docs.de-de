---
title: Ändern von Namespacedeklarationen in einem XML-Dokument
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: b8aa670764deb8e77cfb67fd16dbcf8b1cc9b4c0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711128"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="0976c-102">Ändern von Namespacedeklarationen in einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="0976c-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="0976c-103">Das **XmlDocument** macht Namespacedeklarationen und **xmlns**-Attribute als Teil des Dokumentobjektmodells verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0976c-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="0976c-104">Diese werden im **XmlDocument** gespeichert, sodass der Speicherort dieser Attribute beim Speichern des Dokuments beibehalten werden kann.</span><span class="sxs-lookup"><span data-stu-id="0976c-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="0976c-105">Eine Änderung dieser Attribute hat keine Auswirkungen auf die Eigenschaften **Name**, **NamespaceURI** und **Prefix** anderer Knoten, die bereits in der Struktur vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="0976c-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="0976c-106">Wenn Sie z. b. das folgende Dokument laden, hat das `test`-Element **namespaceURI** `123.`</span><span class="sxs-lookup"><span data-stu-id="0976c-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="0976c-107">Wenn Sie das `xmlns`-Attribut wie folgt entfernen, weist das `test`-Element weiterhin den **NamespaceURI**`123` auf.</span><span class="sxs-lookup"><span data-stu-id="0976c-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="0976c-108">Wenn Sie dem `doc`-Element wie folgt ein anderes `xmlns` Attribut hinzufügen, verfügt das `test`-Element auch weiterhin über die **namespaceURI** -`123`.</span><span class="sxs-lookup"><span data-stu-id="0976c-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="0976c-109">Änderungen an `xmlns`-Attributen haben daher keine Auswirkungen, solange Sie das **XmlDocument**-Objekt nicht speichern und erneut laden.</span><span class="sxs-lookup"><span data-stu-id="0976c-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0976c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0976c-110">See also</span></span>

- [<span data-ttu-id="0976c-111">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="0976c-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
