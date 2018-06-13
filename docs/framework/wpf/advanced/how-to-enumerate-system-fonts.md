---
title: 'Gewusst wie: Auflisten von Systemschriftarten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: 7fc996a2d3ba7042fce70afc20be5d64042c2b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543754"
---
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="960ee-102">Gewusst wie: Auflisten von Systemschriftarten</span><span class="sxs-lookup"><span data-stu-id="960ee-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="960ee-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="960ee-103">Example</span></span>  
 <span data-ttu-id="960ee-104">Im folgende Beispiel wird gezeigt, wie die Schriftarten in der schriftartenauflistung aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="960ee-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="960ee-105">Den Namen der Schriftfamilie der einzelnen <xref:System.Windows.Media.FontFamily> in <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> wird ein Kombinationsfeld als ein Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="960ee-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="960ee-106">Wenn mehrere Versionen der gleichen Schriftfamilie im selben Verzeichnis befinden sich die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Schriftart Aufzählung zurückgegeben, die neueste Version der Schriftart.</span><span class="sxs-lookup"><span data-stu-id="960ee-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="960ee-107">Wenn die Versionsinformationen keine Lösung bereitstellt, wird die Schriftart, mit dem neuesten Zeitstempel zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="960ee-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="960ee-108">Wenn Informationen für den Timestamp entspricht, wird die Schriftartdatei, das zuerst in alphabetischer Reihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="960ee-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>
