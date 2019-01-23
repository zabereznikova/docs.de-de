---
title: 'Vorgehensweise: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 501341f0e71e6e5a224c51e4ae01c68ce6b845cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543486"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="bccb2-102">Vorgehensweise: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="bccb2-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="bccb2-103">Dieses Beispiel beschreibt, wie der automatische Layoutansatz zum Erstellen einer Schaltfläche in einer lokalisierbaren Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bccb2-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="bccb2-104">Lokalisierung von einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann ein zeitaufwändiger Prozess sein.</span><span class="sxs-lookup"><span data-stu-id="bccb2-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="bccb2-105">Oft müssen Lokalisierungsexperten die Größe von Elementen ändern und sie neu positionieren, um Text zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="bccb2-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="bccb2-106">In der Vergangenheit jede Sprache, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für musste angepasst wurde.</span><span class="sxs-lookup"><span data-stu-id="bccb2-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="bccb2-107">Jetzt mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie Elemente, die die Notwendigkeit der Anpassung reduzieren entwerfen.</span><span class="sxs-lookup"><span data-stu-id="bccb2-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="bccb2-108">Der Ansatz zum Schreiben von Anwendungen, die einfacher geändert und neu positioniert werden können, heißt `automatic layout`.</span><span class="sxs-lookup"><span data-stu-id="bccb2-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
 <span data-ttu-id="bccb2-109">Die folgenden beiden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Beispiele erstellen Anwendungen, die eine Schaltfläche, eine mit englischem Text und eine mit spanischem Text zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="bccb2-109">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="bccb2-110">Beachten Sie, dass der Code mit Ausnahme des Texts der gleiche ist; die Schaltfläche wird an den Text angepasst.</span><span class="sxs-lookup"><span data-stu-id="bccb2-110">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bccb2-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bccb2-111">Example</span></span>  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="bccb2-112">Die folgende Grafik zeigt die Ausgabe der Codebeispiele.</span><span class="sxs-lookup"><span data-stu-id="bccb2-112">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="bccb2-113">![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="bccb2-113">![The same button with text in different languages](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="bccb2-114">Schaltfläche zur automatischen Größenanpassung</span><span class="sxs-lookup"><span data-stu-id="bccb2-114">Auto Resizable Button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bccb2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bccb2-115">See also</span></span>
- [<span data-ttu-id="bccb2-116">Übersicht über die Verwendung eines automatischen Layouts</span><span class="sxs-lookup"><span data-stu-id="bccb2-116">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)
- [<span data-ttu-id="bccb2-117">Verwenden eines Rasters für automatisches Layout</span><span class="sxs-lookup"><span data-stu-id="bccb2-117">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
