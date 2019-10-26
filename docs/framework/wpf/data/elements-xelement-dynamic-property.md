---
title: Elements (dynamische XElement-Eigenschaft)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.openlocfilehash: 812adabd3bfb01fd9313ce3f35e6cb0a5e23344e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921149"
---
# <a name="elements-xelement-dynamic-property"></a><span data-ttu-id="daec9-102">Elements (dynamische XElement-Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="daec9-102">Elements (XElement dynamic property)</span></span>

<span data-ttu-id="daec9-103">Sucht nach einem Indexer, der zum Abrufen der untergeordneten Elemente des aktuellen Elements verwendet wird, die dem angegebenen erweiterten Namen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="daec9-103">Gets an indexer used to retrieve the child elements of the current element that match the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="daec9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="daec9-104">Syntax</span></span>

```xaml
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="daec9-105">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="daec9-105">Property value/return value</span></span>

<span data-ttu-id="daec9-106">Indexer des Typs `IEnumerable<XElement> Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="daec9-106">An indexer of the type `IEnumerable<XElement> Item(String expandedName)`.</span></span> <span data-ttu-id="daec9-107">Dieser Indexer nimmt den erweiterten Namen des gewünschten untergeordneten Elements und gibt die passenden untergeordneten Elemente in einer <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>`-Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="daec9-107">This indexer takes the expanded name of the desired child elements and returns the matching child elements in an <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="daec9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="daec9-108">Remarks</span></span>

<span data-ttu-id="daec9-109">Diese Eigenschaft ist identisch mit der <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName>-Methode der <xref:System.Xml.Linq.XContainer>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="daec9-109">This property is equivalent to the <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> method of the <xref:System.Xml.Linq.XContainer> class.</span></span>

<span data-ttu-id="daec9-110">Die Elemente in der zurückgegebenen Auflistung sind in derselben Reihenfolge aufgeführt wie im XML-Quelldokument.</span><span class="sxs-lookup"><span data-stu-id="daec9-110">The elements in the returned collection are in XML source document order.</span></span>

<span data-ttu-id="daec9-111">Diese Eigenschaft verwendet die verzögerte Ausführung.</span><span class="sxs-lookup"><span data-stu-id="daec9-111">This property uses deferred execution.</span></span>

## <a name="see-also"></a><span data-ttu-id="daec9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daec9-112">See also</span></span>

- [<span data-ttu-id="daec9-113">Dynamische Eigenschaften der XElement-Klasse</span><span class="sxs-lookup"><span data-stu-id="daec9-113">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="daec9-114">Element</span><span class="sxs-lookup"><span data-stu-id="daec9-114">Element</span></span>](element-xelement-dynamic-property.md)
- [<span data-ttu-id="daec9-115">Descendants</span><span class="sxs-lookup"><span data-stu-id="daec9-115">Descendants</span></span>](descendants-xelement-dynamic-property.md)
