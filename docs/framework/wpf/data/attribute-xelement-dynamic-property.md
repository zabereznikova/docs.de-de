---
title: Attribute (dynamische XElement-Eigenschaft)
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 2b645575a5b6876ffbb52a999c4e05a2de037493
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921203"
---
# <a name="attribute-xelement-dynamic-property"></a><span data-ttu-id="42748-102">Attribute (dynamische XElement-Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="42748-102">Attribute (XElement dynamic property)</span></span>

<span data-ttu-id="42748-103">Sucht nach einem Indexer, der zum Abrufen der Attributinstanz verwendet wird, die dem angegebenen erweiterten Namen entspricht.</span><span class="sxs-lookup"><span data-stu-id="42748-103">Gets an indexer used to retrieve the attribute instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="42748-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42748-104">Syntax</span></span>

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="42748-105">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="42748-105">Property value/return value</span></span>

<span data-ttu-id="42748-106">Indexer des Typs `XAttribute Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="42748-106">An indexer of the type `XAttribute Item(String expandedName)`.</span></span> <span data-ttu-id="42748-107">Dieser Indexer nimmt den erweiterten Namen des angegebenen Attributs und gibt das zugehörige <xref:System.Xml.Linq.XAttribute> zurück. Wenn kein Attribut mit dem angegebenen Namen existiert, wird `null` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42748-107">This indexer takes the expanded name of the specified attribute and returns the corresponding <xref:System.Xml.Linq.XAttribute>, or `null` if there is no attribute with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="42748-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42748-108">Remarks</span></span>

<span data-ttu-id="42748-109">Diese Eigenschaft ist identisch mit der <xref:System.Xml.Linq.XElement.Attribute%2A>-Methode der <xref:System.Xml.Linq.XElement?displayProperty=fullName>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="42748-109">This property is equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="42748-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42748-110">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [<span data-ttu-id="42748-111">Dynamische Eigenschaften der XElement-Klasse</span><span class="sxs-lookup"><span data-stu-id="42748-111">XElement Class Dynamic Properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="42748-112">Wert</span><span class="sxs-lookup"><span data-stu-id="42748-112">Value</span></span>](value-xattribute-dynamic-property.md)
