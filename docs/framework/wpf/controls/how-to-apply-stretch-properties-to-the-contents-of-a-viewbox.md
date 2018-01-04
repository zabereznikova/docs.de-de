---
title: 'Gewusst wie: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox'
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
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 93e61783f70ee501266a68785350ee0810dff255
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a><span data-ttu-id="89249-102">Gewusst wie: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox</span><span class="sxs-lookup"><span data-stu-id="89249-102">How to: Apply Stretch Properties to the Contents of a Viewbox</span></span>
## <a name="example"></a><span data-ttu-id="89249-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89249-103">Example</span></span>  
 <span data-ttu-id="89249-104">In diesem Beispiel wird gezeigt, wie zum Ändern des Werts von der <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> und <xref:System.Windows.Controls.Viewbox.Stretch%2A> Eigenschaften einer <xref:System.Windows.Controls.Viewbox>.</span><span class="sxs-lookup"><span data-stu-id="89249-104">This example shows how to change the value of the <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> and <xref:System.Windows.Controls.Viewbox.Stretch%2A> properties of a <xref:System.Windows.Controls.Viewbox>.</span></span>  
  
 <span data-ttu-id="89249-105">Im ersten Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.Viewbox> Element.</span><span class="sxs-lookup"><span data-stu-id="89249-105">The first example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.Viewbox> element.</span></span> <span data-ttu-id="89249-106">Weist eine <xref:System.Windows.FrameworkElement.MaxWidth%2A> und <xref:System.Windows.FrameworkElement.MaxHeight%2A> von 400.</span><span class="sxs-lookup"><span data-stu-id="89249-106">It assigns a <xref:System.Windows.FrameworkElement.MaxWidth%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> of 400.</span></span> <span data-ttu-id="89249-107">Das Beispiel schachtelt einen <xref:System.Windows.Controls.Image> Element innerhalb der <xref:System.Windows.Controls.Viewbox>.</span><span class="sxs-lookup"><span data-stu-id="89249-107">The example nests an <xref:System.Windows.Controls.Image> element within the <xref:System.Windows.Controls.Viewbox>.</span></span> <span data-ttu-id="89249-108"><xref:System.Windows.Controls.Button>Elemente, die Eigenschaftswerte für entsprechen, den <xref:System.Windows.Controls.Viewbox.Stretch%2A> und <xref:System.Windows.Controls.StretchDirection> Enumerationen bearbeitet das ausdehnen Verhalten des geschachtelten <xref:System.Windows.Controls.Image>.</span><span class="sxs-lookup"><span data-stu-id="89249-108"><xref:System.Windows.Controls.Button> elements that correspond to the property values for the <xref:System.Windows.Controls.Viewbox.Stretch%2A> and <xref:System.Windows.Controls.StretchDirection> enumerations manipulate the stretching behavior of the nested <xref:System.Windows.Controls.Image>.</span></span>  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="89249-109">Der folgende Code-Behind-Dateihandles der <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisse, die der vorherigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="89249-109">The following code-behind file handles the <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events that the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example defines.</span></span>  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="89249-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89249-110">See Also</span></span>  
 <xref:System.Windows.Controls.Viewbox>  
 <xref:System.Windows.Media.Stretch>  
 <xref:System.Windows.Controls.StretchDirection>
