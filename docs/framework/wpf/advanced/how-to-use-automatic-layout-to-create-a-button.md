---
title: "Gewusst wie: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c642e6491722e9bfe35337d066e3870f5a70f38c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a><span data-ttu-id="b8449-102">Gewusst wie: Verwenden des automatischen Layouts zum Erstellen einer Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b8449-102">How to: Use Automatic Layout to Create a Button</span></span>
<span data-ttu-id="b8449-103">Dieses Beispiel beschreibt, wie der automatische Layoutansatz zum Erstellen einer Schaltfläche in einer lokalisierbaren Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8449-103">This example describes how to use the automatic layout approach to create a button in a localizable application.</span></span>  
  
 <span data-ttu-id="b8449-104">Lokalisierung von einem [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] kann zeitaufwändig sein.</span><span class="sxs-lookup"><span data-stu-id="b8449-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="b8449-105">Oft müssen Lokalisierungsexperten die Größe von Elementen ändern und sie neu positionieren, um Text zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="b8449-105">Often localizers need to resize and reposition elements in addition to translating text.</span></span> <span data-ttu-id="b8449-106">In der Vergangenheit jede Sprache, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für erforderliche Anpassung angepasst wurde.</span><span class="sxs-lookup"><span data-stu-id="b8449-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="b8449-107">Jetzt mit den Funktionen von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] können Sie Elemente, die die Notwendigkeit einer Anpassung reduzieren entwerfen.</span><span class="sxs-lookup"><span data-stu-id="b8449-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="b8449-108">Der Ansatz zum Schreiben von Anwendungen, die leichter dessen Größe geändert wurde und neu positioniert werden können heißt `automatic layout`.</span><span class="sxs-lookup"><span data-stu-id="b8449-108">The approach to writing applications that can be more easily resized and repositioned is called `automatic layout`.</span></span>  
  
 <span data-ttu-id="b8449-109">Die folgenden beiden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Beispiele für Anwendungen erstellen, die eine Schaltfläche, eine mit englischem Text und eine spanische Text zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="b8449-109">The following two [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples create applications that instantiate a button; one with English text and one with Spanish text.</span></span> <span data-ttu-id="b8449-110">Beachten Sie, dass der Code mit Ausnahme des Texts der gleiche ist; die Schaltfläche wird an den Text angepasst.</span><span class="sxs-lookup"><span data-stu-id="b8449-110">Notice that the code is the same except for the text; the button adjusts to fit the text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8449-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8449-111">Example</span></span>  
 [!code-xaml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xaml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="b8449-112">Die folgende Grafik zeigt die Ausgabe der Codebeispiele.</span><span class="sxs-lookup"><span data-stu-id="b8449-112">The following graphic shows the output of the code samples.</span></span>  
  
 <span data-ttu-id="b8449-113">![Die gleiche Schaltfläche mit Text in unterschiedlichen Sprachen](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span><span class="sxs-lookup"><span data-stu-id="b8449-113">![The same button with text in different languages](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")</span></span>  
<span data-ttu-id="b8449-114">Schaltfläche zur automatischen Größenanpassung</span><span class="sxs-lookup"><span data-stu-id="b8449-114">Auto Resizable Button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8449-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8449-115">See Also</span></span>  
 [<span data-ttu-id="b8449-116">Übersicht über die Verwendung eines automatischen Layouts</span><span class="sxs-lookup"><span data-stu-id="b8449-116">Use Automatic Layout Overview</span></span>](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)  
 [<span data-ttu-id="b8449-117">Verwenden eines Rasters für automatisches Layout</span><span class="sxs-lookup"><span data-stu-id="b8449-117">Use a Grid for Automatic Layout</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)
