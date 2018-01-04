---
title: ColorConvertedBitmap-Markuperweiterung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df6fac332f20d64ddf6569554a75ef96a5536c0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="colorconvertedbitmap-markup-extension"></a><span data-ttu-id="7bc1b-102">ColorConvertedBitmap-Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="7bc1b-102">ColorConvertedBitmap Markup Extension</span></span>
<span data-ttu-id="7bc1b-103">Bietet eine Möglichkeit, eine Bitmapquelle angeben, die nicht über ein eingebettetes Profil verfügt.</span><span class="sxs-lookup"><span data-stu-id="7bc1b-103">Provides a way to specify a bitmap source that does not have an embedded profile.</span></span> <span data-ttu-id="7bc1b-104">Farbe von Kontexten / Profile werden angegeben, indem [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], wie die Bildquelle [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bc1b-104">Color contexts / profiles are specified by [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], as is the image source [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="7bc1b-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="7bc1b-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7bc1b-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="7bc1b-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`imageSource`|<span data-ttu-id="7bc1b-107">Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] der profillosen Bitmap.</span><span class="sxs-lookup"><span data-stu-id="7bc1b-107">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the nonprofiled bitmap.</span></span>|  
|`sourceIIC`|<span data-ttu-id="7bc1b-108">Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] der Profil-Quellkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="7bc1b-108">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the source profile configuration.</span></span>|  
|`destinationIIC`|<span data-ttu-id="7bc1b-109">Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] des Ziel-Profilkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7bc1b-109">The [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] of the destination profile configuration</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bc1b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7bc1b-110">Remarks</span></span>  
 <span data-ttu-id="7bc1b-111">Dieser Markuperweiterung soll z. B. eine zusammengehörige Gruppe von Image-Source-Eigenschaftswerte füllen <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="7bc1b-111">This markup extension is intended to fill a related set of image-source property values such as <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.</span></span>  
  
 <span data-ttu-id="7bc1b-112">Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.</span><span class="sxs-lookup"><span data-stu-id="7bc1b-112">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="7bc1b-113">`ColorConvertedBitmap`(oder `ColorConvertedBitmapExtension`) kann nicht in eine Eigenschaftenelementsyntax, verwendet werden, da die Werte nur als Werte für den ursprünglichen Konstruktor festgelegt werden können, die Zeichenfolge ist der Erweiterungsbezeichner befolgen.</span><span class="sxs-lookup"><span data-stu-id="7bc1b-113">`ColorConvertedBitmap` (or `ColorConvertedBitmapExtension`) cannot be used in property element syntax, because the values can only be set as values on the initial constructor, which is the string following the extension identifier.</span></span>  
  
 <span data-ttu-id="7bc1b-114">`ColorConvertedBitmap` ist eine Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="7bc1b-114">`ColorConvertedBitmap` is a markup extension.</span></span> <span data-ttu-id="7bc1b-115">Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7bc1b-115">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="7bc1b-116">Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="7bc1b-116">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="7bc1b-117">Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="7bc1b-117">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc1b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7bc1b-118">See Also</span></span>  
 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>  
 [<span data-ttu-id="7bc1b-119">Markuperweiterungen und WPF-XAML</span><span class="sxs-lookup"><span data-stu-id="7bc1b-119">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="7bc1b-120">Übersicht über die Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="7bc1b-120">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
