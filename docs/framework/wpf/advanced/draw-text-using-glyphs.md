---
title: Zeichnen von Text mit Symbolen
ms.date: 03/30/2017
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
ms.openlocfilehash: 155f0b756b43ad8cfd0ddde63a5e86854f5f1624
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363006"
---
# <a name="draw-text-using-glyphs"></a><span data-ttu-id="e544f-102">Zeichnen von Text mit Symbolen</span><span class="sxs-lookup"><span data-stu-id="e544f-102">Draw Text Using Glyphs</span></span>
<span data-ttu-id="e544f-103">In diesem Thema wird erläutert, wie Sie mit der Low-Level <xref:System.Windows.Documents.Glyphs> Objekt zum Anzeigen von Text in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e544f-103">This topic explains how to use the low-level <xref:System.Windows.Documents.Glyphs> object to display text in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="e544f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e544f-104">Example</span></span>  
 <span data-ttu-id="e544f-105">Die folgenden Beispiele zeigen, wie Eigenschaften für definiert eine <xref:System.Windows.Documents.Glyphs> im-Objekt [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e544f-105">The following examples show how to define properties for a <xref:System.Windows.Documents.Glyphs> object in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="e544f-106">Die <xref:System.Windows.Documents.Glyphs> Objekt darstellt, die Ausgabe des einen <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e544f-106">The <xref:System.Windows.Documents.Glyphs> object represents the output of a <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="e544f-107">In den Beispielen wird davon ausgegangen, dass die Schriftarten Arial, Courier New und Times New Roman im Ordner C:\WINDOWS\Fonts auf dem lokalen Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="e544f-107">The examples assume that the Arial, Courier New, and Times New Roman fonts are installed in the C:\WINDOWS\Fonts folder on the local computer.</span></span>  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 <span data-ttu-id="e544f-108">In diesem Beispiel wird gezeigt, wie andere Eigenschaften des definiert <xref:System.Windows.Documents.Glyphs> Objekte im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e544f-108">This example shows how to define other properties of <xref:System.Windows.Documents.Glyphs> objects in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e544f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e544f-109">See also</span></span>
- [<span data-ttu-id="e544f-110">Typografie in WPF</span><span class="sxs-lookup"><span data-stu-id="e544f-110">Typography in WPF</span></span>](typography-in-wpf.md)
