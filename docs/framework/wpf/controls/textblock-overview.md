---
title: "Übersicht über TextBlock"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 404f5677bca0df45d4f7dbf689a297499b36bbab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="textblock-overview"></a><span data-ttu-id="7cbf1-102">Übersicht über TextBlock</span><span class="sxs-lookup"><span data-stu-id="7cbf1-102">TextBlock Overview</span></span>
<span data-ttu-id="7cbf1-103">Die <xref:System.Windows.Controls.TextBlock> Steuerelement bietet flexible Text-Unterstützung für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="7cbf1-103">The <xref:System.Windows.Controls.TextBlock> control provides flexible text support for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="7cbf1-104">Es eignet sich hauptsächlich für einfache [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarios, in denen nicht mehr Text als ein Absatz benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="7cbf1-104">The element is targeted primarily toward basic [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios that do not require more than one paragraph of text.</span></span> <span data-ttu-id="7cbf1-105">Unterstützt eine Reihe von Eigenschaften, die präzise Steuerung der Darstellung, wie z. B. ermöglichen <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, und <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cbf1-105">It supports a number of properties that enable precise control of presentation, such as <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, and <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span></span> <span data-ttu-id="7cbf1-106">Text-Inhalt kann hinzugefügt werden, mithilfe der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7cbf1-106">Text content can be added using the <xref:System.Windows.Controls.TextBlock.Text%2A> property.</span></span> <span data-ttu-id="7cbf1-107">Bei der Verwendung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] wird der Inhalt zwischen dem öffnenden und dem schließenden Tag implizit als Text des Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7cbf1-107">When used in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], content between the open and closing tag is implicitly added as the text of the element.</span></span>  
  
 <span data-ttu-id="7cbf1-108">Ein <xref:System.Windows.Controls.TextBlock> Element kann sehr einfach mit instanziiert werden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cbf1-108">A <xref:System.Windows.Controls.TextBlock> element can be instantiated very simply using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[TextBlockSnip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 <span data-ttu-id="7cbf1-109">Auf ähnliche Weise die Verwendung von der <xref:System.Windows.Controls.TextBlock> Element im Code ist relativ einfach.</span><span class="sxs-lookup"><span data-stu-id="7cbf1-109">Similarly, usage of the <xref:System.Windows.Controls.TextBlock> element in code is relatively simple.</span></span>  
  
 [!code-csharp[TextBlockSnip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7cbf1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cbf1-110">See Also</span></span>  
 <xref:System.Windows.Controls.Label>
