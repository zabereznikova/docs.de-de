---
title: Element (dynamische XElement-Eigenschaft)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.openlocfilehash: fc0277d0dc38574696f01e6915e5382744345771
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921185"
---
# <a name="element-xelement-dynamic-property"></a><span data-ttu-id="cc05c-102">Element (dynamische XElement-Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="cc05c-102">Element (XElement dynamic property)</span></span>

<span data-ttu-id="cc05c-103">Ermittelt einen Indexer, der zum Abrufen der Instanz des untergeordneten Elements verwendet wird, die dem angegebenen erweiterten Namen entspricht.</span><span class="sxs-lookup"><span data-stu-id="cc05c-103">Gets an indexer used to retrieve the child element instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc05c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc05c-104">Syntax</span></span>

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="cc05c-105">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cc05c-105">Property value/return value</span></span>

<span data-ttu-id="cc05c-106">Indexer des Typs `XElement Item(String expandedName)`.</span><span class="sxs-lookup"><span data-stu-id="cc05c-106">An indexer of the type `XElement Item(String expandedName)`.</span></span> <span data-ttu-id="cc05c-107">Dieser Indexer nimmt einen erweiterten Namensparameter und gibt das zugehörige <xref:System.Xml.Linq.XElement> oder, wenn kein Element mit dem angegebenen Namen existiert, `null` zurück.</span><span class="sxs-lookup"><span data-stu-id="cc05c-107">This indexer takes an expanded name parameter and returns the corresponding <xref:System.Xml.Linq.XElement>, or `null` if there is no element with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc05c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc05c-108">Remarks</span></span>

<span data-ttu-id="cc05c-109">Diese Eigenschaft entspricht der <xref:System.Xml.Linq.XContainer.Element%2A>-Methode der <xref:System.Xml.Linq.XContainer?displayProperty=fullName>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="cc05c-109">This property is equivalent to <xref:System.Xml.Linq.XContainer.Element%2A> method of the <xref:System.Xml.Linq.XContainer?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc05c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc05c-110">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [<span data-ttu-id="cc05c-111">Dynamische Eigenschaften der XElement-Klasse</span><span class="sxs-lookup"><span data-stu-id="cc05c-111">XElement class dynamic properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="cc05c-112">Elemente</span><span class="sxs-lookup"><span data-stu-id="cc05c-112">Elements</span></span>](elements-xelement-dynamic-property.md)
