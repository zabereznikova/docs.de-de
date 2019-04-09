---
title: 'Vorgehensweise: Verwenden eines Rasters für automatisches Layout'
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 590ad7292fea572b20ccaa09ce2886724e004a6a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227117"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="9eb45-102">Vorgehensweise: Verwenden eines Rasters für automatisches Layout</span><span class="sxs-lookup"><span data-stu-id="9eb45-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="9eb45-103">Dieses Beispiel beschreibt, wie ein Raster im automatischen Layoutansatz zum Erstellen einer lokalisierbaren Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9eb45-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="9eb45-104">Lokalisierung von einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann ein zeitaufwändiger Prozess sein.</span><span class="sxs-lookup"><span data-stu-id="9eb45-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="9eb45-105">Oft müssen Lokalisierungsexperten die Größe von Elementen ändern und sie neu positionieren, um Text zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="9eb45-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="9eb45-106">In der Vergangenheit jede Sprache, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für musste angepasst wurde.</span><span class="sxs-lookup"><span data-stu-id="9eb45-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="9eb45-107">Jetzt mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie Elemente, die die Notwendigkeit der Anpassung reduzieren entwerfen.</span><span class="sxs-lookup"><span data-stu-id="9eb45-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="9eb45-108">Der Ansatz zum Schreiben von Anwendungen, die leichter Größe und neu positioniert werden können, heißt `auto layout`.</span><span class="sxs-lookup"><span data-stu-id="9eb45-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="9eb45-109">Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird veranschaulicht, wie ein Raster zum Positionieren einiger Schaltflächen und Text.</span><span class="sxs-lookup"><span data-stu-id="9eb45-109">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="9eb45-110">Beachten Sie, die die Höhe und Breite der Zellen, um festgelegt werden `Auto`; aus diesem Grund die Zelle mit der Schaltfläche mit einem Bild passt, das Bild angepasst.</span><span class="sxs-lookup"><span data-stu-id="9eb45-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="9eb45-111">Da die <xref:System.Windows.Controls.Grid> Element kann anpassen, an dessen Inhalt, es kann hilfreich sein, beim Erstellen von automatischen Layoutansatz zum Entwerfen von Anwendungen, die lokalisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="9eb45-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9eb45-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9eb45-112">Example</span></span>  
 <span data-ttu-id="9eb45-113">Das folgende Beispiel veranschaulicht die Verwendung von eines Rasters.</span><span class="sxs-lookup"><span data-stu-id="9eb45-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="9eb45-114">Die folgende Grafik zeigt die Ausgabe des Codebeispiels.</span><span class="sxs-lookup"><span data-stu-id="9eb45-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="9eb45-115">![Rasterbeispiel](./media/glob-grid.png "Glob_grid")</span><span class="sxs-lookup"><span data-stu-id="9eb45-115">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="9eb45-116">Raster</span><span class="sxs-lookup"><span data-stu-id="9eb45-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb45-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9eb45-117">See also</span></span>

- [<span data-ttu-id="9eb45-118">Übersicht über die Verwendung eines automatischen Layouts</span><span class="sxs-lookup"><span data-stu-id="9eb45-118">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="9eb45-119">Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="9eb45-119">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
