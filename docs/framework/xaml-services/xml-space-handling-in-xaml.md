---
title: xml:space-Behandlung in XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b8356cdb47b6b834e8d9a6bb84b26445af6d865
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="80755-102">xml:space-Behandlung in XAML</span><span class="sxs-lookup"><span data-stu-id="80755-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="80755-103">Die `xml:space` -Attribut ist ein in XML definierten-Attribut, das Verarbeitungsverhalten für signifikante Leerräume innerhalb einer Object-Element deklariert.</span><span class="sxs-lookup"><span data-stu-id="80755-103">The `xml:space` attribute is an XML-defined attribute that declares the significant whitespace processing behavior within an object element.</span></span> <span data-ttu-id="80755-104">Dieses Verhalten ist relevant für den gesamten Inhalt (inneren Text), die im Element enthalten sind, in denen `xml:space` deklariert ist, und auch Bereiche untergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="80755-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="80755-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="80755-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="80755-106">\- oder –</span><span class="sxs-lookup"><span data-stu-id="80755-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="80755-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80755-107">Remarks</span></span>  
 <span data-ttu-id="80755-108">Die Definition für die `xml:space` -Attribut in XAML, einschließlich der beiden möglichen Werte abgeleitet `xml:space` als "spezielles Attribut" von W3C-Spezifikationen für XML definiert.</span><span class="sxs-lookup"><span data-stu-id="80755-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="80755-109">Der Standardwert der `xml:space` Attribut wird der Literalwert `"default"`.</span><span class="sxs-lookup"><span data-stu-id="80755-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="80755-110">Für den Wert `"default"`, oder wenn `xml:space` ist nicht angegeben, das Verhalten der Analyse signifikanten Leerräume in diesem Thema definiert die Standardbehandlung entspricht [Leerstellenverarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="80755-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant whitespace parsing is the default handling, as defined in the topic [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="80755-111">Geben Sie zum Beibehalten von Leerräumen in Objekt-Elementinhalt `xml:space="preserve"` für das Objektelement.</span><span class="sxs-lookup"><span data-stu-id="80755-111">To preserve whitespace within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="80755-112">Bei den meisten Interpretationen der `xml:space` -Attributeffekte und der Wert des Attributs auf untergeordnete Elemente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="80755-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="80755-113">Eine detaillierte Erläuterung der leerstellenverarbeitung in XAML, finden Sie unter [Leerstellenverarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="80755-113">For a complete discussion of whitespace processing in XAML, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80755-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80755-114">See Also</span></span>  
 [<span data-ttu-id="80755-115">Leerstellenverarbeitung in XAML</span><span class="sxs-lookup"><span data-stu-id="80755-115">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="80755-116">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="80755-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
