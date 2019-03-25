---
title: 'Vorgehensweise: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 8eb1e93dd87c210812c9b7758c744a616ef2d862
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409782"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="11ac8-102">Vorgehensweise: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="11ac8-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="11ac8-103">Dieses Beispiel beschreibt, wie der automatische Layoutansatz zum Erstellen einer Schaltfläche in einer lokalisierbaren Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11ac8-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="11ac8-104">Lokalisierung von einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann ein zeitaufwändiger Prozess sein.</span><span class="sxs-lookup"><span data-stu-id="11ac8-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="11ac8-105">Oft müssen Lokalisierungsexperten die Größe von Elementen ändern und sie neu positionieren, um Text zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="11ac8-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="11ac8-106">In der Vergangenheit jede Sprache, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für musste angepasst wurde.</span><span class="sxs-lookup"><span data-stu-id="11ac8-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="11ac8-107">Jetzt mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie Elemente, die die Notwendigkeit der Anpassung reduzieren entwerfen.</span><span class="sxs-lookup"><span data-stu-id="11ac8-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="11ac8-108">Der Ansatz zum Schreiben von Anwendungen, die einfacher geändert und neu positioniert werden können, heißt `automatic layout`.</span><span class="sxs-lookup"><span data-stu-id="11ac8-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11ac8-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="11ac8-109">Example</span></span>  

<span data-ttu-id="11ac8-110">Die folgenden beiden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Beispiele erstellen Anwendungen, die eine Schaltfläche, eine mit englischem Text und eine mit spanischem Text zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="11ac8-110">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="11ac8-111">Beachten Sie, dass der Code mit Ausnahme des Texts der gleiche ist; die Schaltfläche wird an den Text angepasst.</span><span class="sxs-lookup"><span data-stu-id="11ac8-111">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="11ac8-112">Die folgende Abbildung zeigt die Ausgabe der Codebeispiele mit fester Größe automatisch Schaltflächen:</span><span class="sxs-lookup"><span data-stu-id="11ac8-112">The following graphic shows the output of the code samples with auto-resizable buttons:</span></span>
  
 ![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
## <a name="see-also"></a><span data-ttu-id="11ac8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11ac8-114">See also</span></span>

- [<span data-ttu-id="11ac8-115">Übersicht über die Verwendung eines automatischen Layouts</span><span class="sxs-lookup"><span data-stu-id="11ac8-115">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="11ac8-116">Verwenden eines Rasters für automatisches Layout</span><span class="sxs-lookup"><span data-stu-id="11ac8-116">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
