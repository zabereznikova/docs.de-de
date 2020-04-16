---
title: xml:space-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432701"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="6edcb-102">xml:space-Behandlung in XAML</span><span class="sxs-lookup"><span data-stu-id="6edcb-102">xml:space Handling in XAML</span></span>

<span data-ttu-id="6edcb-103">Das `xml:space` Attribut ist ein XML-definiertes Attribut, das das signifikante White-Space-Verarbeitungsverhalten innerhalb eines Objektelements deklariert.</span><span class="sxs-lookup"><span data-stu-id="6edcb-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="6edcb-104">Dieses Verhalten ist für alle Inhalte (innerer `xml:space` Text) relevant, die im Element enthalten sind, in dem deklariert wird, sowie für Bereiche für untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="6edcb-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="6edcb-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="6edcb-105">XAML Attribute Usage</span></span>

```xaml
<object xml:space="preserve" />
```

 <span data-ttu-id="6edcb-106">\- oder -</span><span class="sxs-lookup"><span data-stu-id="6edcb-106">\- or -</span></span>

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a><span data-ttu-id="6edcb-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6edcb-107">Remarks</span></span>

<span data-ttu-id="6edcb-108">Die Definition `xml:space` für das Attribut in XAML einschließlich `xml:space` seiner beiden möglichen Werte wird von den W3C-Spezifikationen für XML als "special-Attribut" definiert.</span><span class="sxs-lookup"><span data-stu-id="6edcb-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>

<span data-ttu-id="6edcb-109">Der Standardwert `xml:space` des Attributs `"default"`ist der Literalwert .</span><span class="sxs-lookup"><span data-stu-id="6edcb-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="6edcb-110">Für den `"default"`Wert `xml:space` , oder wenn überhaupt nicht angegeben, ist das Verhalten einer signifikanten Leerraumanalyse die Standardbehandlung, wie im Thema [White-Space-Verarbeitung in XAML](white-space-processing.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="6edcb-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](white-space-processing.md).</span></span>

<span data-ttu-id="6edcb-111">Um Leerraum innerhalb des Objektelementinhalts beizubehalten, geben Sie `xml:space="preserve"` für dieses Objektelement an.</span><span class="sxs-lookup"><span data-stu-id="6edcb-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>

<span data-ttu-id="6edcb-112">Bei den meisten `xml:space` Interpretationen werden die Attributeffekte und der Wert des Attributs auf untergeordnete Elemente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="6edcb-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>

<span data-ttu-id="6edcb-113">Eine vollständige Erläuterung der Whitespace-Verarbeitung in XAML finden Sie [unter Whitespace Processing in XAML](white-space-processing.md).</span><span class="sxs-lookup"><span data-stu-id="6edcb-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](white-space-processing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6edcb-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6edcb-114">See also</span></span>

- [<span data-ttu-id="6edcb-115">Leerstellenverarbeitung in XAML</span><span class="sxs-lookup"><span data-stu-id="6edcb-115">White-space processing in XAML</span></span>](white-space-processing.md)
- [<span data-ttu-id="6edcb-116">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="6edcb-116">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
