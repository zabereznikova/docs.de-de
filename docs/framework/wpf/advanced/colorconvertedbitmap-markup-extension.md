---
title: ColorConvertedBitmap-Markuperweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: a5b491723a036c1b1fd0bb61736e6f2ee53fbcd3
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141230"
---
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="45d57-102">ColorConvertedBitmap-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="45d57-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="45d57-103">Bietet eine Möglichkeit, eine Bitmapquelle anzugeben, die kein eingebettetes Profil besitzt.</span><span class="sxs-lookup"><span data-stu-id="45d57-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="45d57-104">Farb Kontexte/-Profile werden durch den URI angegeben, ebenso wie der Bildquellen-URI.</span><span class="sxs-lookup"><span data-stu-id="45d57-104">Color contexts / profiles are specified by URI, as is the image source URI.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="45d57-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="45d57-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" ... />
```  
  
## <a name="xaml-values"></a><span data-ttu-id="45d57-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="45d57-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="45d57-107">Der URI der Bitmap ohne Profilerstellung.</span><span class="sxs-lookup"><span data-stu-id="45d57-107">The URI of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="45d57-108">Der URI der Quell Profil Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="45d57-108">The URI of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="45d57-109">Der URI der Ziel Profil Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="45d57-109">The URI of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45d57-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="45d57-110">Remarks</span></span>  
 <span data-ttu-id="45d57-111">Diese Markup Erweiterung dient zum Auffüllen eines verknüpften Satzes von Bildquellen-Eigenschafts Werten, <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>wie z. b..</span><span class="sxs-lookup"><span data-stu-id="45d57-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="45d57-112">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="45d57-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="45d57-113">`ColorConvertedBitmap`(oder `ColorConvertedBitmapExtension`) kann nicht in der Eigenschafts Element Syntax verwendet werden, da die Werte nur als Werte für den ursprünglichen Konstruktor festgelegt werden können. Dies ist die Zeichenfolge, die auf den Erweiterungs Bezeichner folgt.</span><span class="sxs-lookup"><span data-stu-id="45d57-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="45d57-114">`ColorConvertedBitmap` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="45d57-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="45d57-115">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="45d57-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="45d57-116">Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="45d57-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="45d57-117">Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="45d57-117">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d57-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45d57-118">See also</span></span>

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [<span data-ttu-id="45d57-119">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="45d57-119">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="45d57-120">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="45d57-120">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
