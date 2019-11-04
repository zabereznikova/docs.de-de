---
title: xml:space-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458796"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="80922-102">xml:space-Behandlung in XAML</span><span class="sxs-lookup"><span data-stu-id="80922-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="80922-103">Das `xml:space`-Attribut ist ein XML-definiertes Attribut, das das signifikante Verhalten der Leerraum Verarbeitung in einem Object-Element deklariert.</span><span class="sxs-lookup"><span data-stu-id="80922-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="80922-104">Dieses Verhalten ist relevant für den gesamten Inhalt (inneren Text), der in dem Element enthalten ist, in dem `xml:space` deklariert ist, und auch Bereiche für untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="80922-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="80922-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="80922-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="80922-106">\- oder -</span><span class="sxs-lookup"><span data-stu-id="80922-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="80922-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80922-107">Remarks</span></span>  
 <span data-ttu-id="80922-108">Die Definition für das `xml:space`-Attribut in XAML, einschließlich der beiden möglichen Werte, wird von `xml:space` abgeleitet, wie von den W3C-Spezifikationen für XML als "spezielles Attribut" definiert.</span><span class="sxs-lookup"><span data-stu-id="80922-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="80922-109">Der Standardwert des `xml:space` Attributs ist der Literalwert `"default"`.</span><span class="sxs-lookup"><span data-stu-id="80922-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="80922-110">Für den Wert `"default"`oder wenn `xml:space` überhaupt nicht angegeben wird, ist das Verhalten der signifikanten Leerraum-Verarbeitung die Standardbehandlung, wie im Thema [Leerraum Verarbeitung in XAML](whitespace-processing-in-xaml.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="80922-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="80922-111">Um Leerraum im Inhalt von Objekt Elementen beizubehalten, geben Sie `xml:space="preserve"` für dieses Objekt Element an.</span><span class="sxs-lookup"><span data-stu-id="80922-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="80922-112">Bei den meisten Interpretationen werden die Auswirkungen des `xml:space` Attributs und der Wert des Attributs auf untergeordnete Elemente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="80922-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="80922-113">Eine vollständige Erläuterung der Leerraum Verarbeitung in XAML finden Sie unter [Leerraum Verarbeitung in XAML](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="80922-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80922-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80922-114">See also</span></span>

- [<span data-ttu-id="80922-115">Leerraum Verarbeitung in XAML</span><span class="sxs-lookup"><span data-stu-id="80922-115">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
- [<span data-ttu-id="80922-116">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="80922-116">XAML Overview (WPF)</span></span>](../../desktop-wpf/fundamentals/xaml.md)
