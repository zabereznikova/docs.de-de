---
title: ColorConvertedBitmap-Markuperweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: 7d14ddc6276b9dd7baee12e267e8af1250bc11ab
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582769"
---
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="bdff4-102">ColorConvertedBitmap-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="bdff4-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="bdff4-103">Bietet eine Möglichkeit, eine Bitmapquelle anzugeben, die kein eingebettetes Profil besitzt.</span><span class="sxs-lookup"><span data-stu-id="bdff4-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="bdff4-104">Farb Kontexte/-Profile werden durch den URI angegeben, ebenso wie der Bildquellen-URI.</span><span class="sxs-lookup"><span data-stu-id="bdff4-104">Color contexts / profiles are specified by URI, as is the image source URI.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="bdff4-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="bdff4-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="bdff4-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="bdff4-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="bdff4-107">Der URI der Bitmap ohne Profilerstellung.</span><span class="sxs-lookup"><span data-stu-id="bdff4-107">The URI of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="bdff4-108">Der URI der Quell Profil Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="bdff4-108">The URI of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="bdff4-109">Der URI der Ziel Profil Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="bdff4-109">The URI of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdff4-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bdff4-110">Remarks</span></span>  
 <span data-ttu-id="bdff4-111">Diese Markup Erweiterung dient zum Auffüllen eines verknüpften Satzes von Eigenschafts Werten für Bildquellen, z. b. <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="bdff4-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="bdff4-112">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="bdff4-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="bdff4-113">`ColorConvertedBitmap` (oder `ColorConvertedBitmapExtension`) kann nicht in der Eigenschafts Element Syntax verwendet werden, da die Werte nur als Werte für den ursprünglichen Konstruktor festgelegt werden können. Dies ist die Zeichenfolge, die auf den Erweiterungs Bezeichner folgt.</span><span class="sxs-lookup"><span data-stu-id="bdff4-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="bdff4-114">`ColorConvertedBitmap` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="bdff4-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="bdff4-115">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bdff4-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="bdff4-116">Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="bdff4-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="bdff4-117">Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="bdff4-117">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdff4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdff4-118">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="bdff4-119">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="bdff4-119">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="bdff4-120">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="bdff4-120">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
