---
title: 'Vorgehensweise: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: 96d6584debe3e0dc85121cbcde5e6b4d1ac8c75c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352477"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a><span data-ttu-id="1ad4f-102">Vorgehensweise: Anwenden von Stretch-Eigenschaften auf den Inhalt einer Viewbox</span><span class="sxs-lookup"><span data-stu-id="1ad4f-102">How to: Apply Stretch Properties to the Contents of a Viewbox</span></span>
## <a name="example"></a><span data-ttu-id="1ad4f-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ad4f-103">Example</span></span>  
 <span data-ttu-id="1ad4f-104">Dieses Beispiel zeigt, wie Sie den Wert ändern der <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> und <xref:System.Windows.Controls.Viewbox.Stretch%2A> Eigenschaften eine <xref:System.Windows.Controls.Viewbox>.</span><span class="sxs-lookup"><span data-stu-id="1ad4f-104">This example shows how to change the value of the <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> and <xref:System.Windows.Controls.Viewbox.Stretch%2A> properties of a <xref:System.Windows.Controls.Viewbox>.</span></span>  
  
 <span data-ttu-id="1ad4f-105">Im ersten Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Definieren einer <xref:System.Windows.Controls.Viewbox> Element.</span><span class="sxs-lookup"><span data-stu-id="1ad4f-105">The first example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.Viewbox> element.</span></span> <span data-ttu-id="1ad4f-106">Weist eine <xref:System.Windows.FrameworkElement.MaxWidth%2A> und <xref:System.Windows.FrameworkElement.MaxHeight%2A> 400.</span><span class="sxs-lookup"><span data-stu-id="1ad4f-106">It assigns a <xref:System.Windows.FrameworkElement.MaxWidth%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> of 400.</span></span> <span data-ttu-id="1ad4f-107">Das Beispiel schachtelt einen <xref:System.Windows.Controls.Image> Element innerhalb der <xref:System.Windows.Controls.Viewbox>.</span><span class="sxs-lookup"><span data-stu-id="1ad4f-107">The example nests an <xref:System.Windows.Controls.Image> element within the <xref:System.Windows.Controls.Viewbox>.</span></span> <span data-ttu-id="1ad4f-108"><xref:System.Windows.Controls.Button> Elemente, die die Eigenschaftswerte für entsprechen, den <xref:System.Windows.Controls.Viewbox.Stretch%2A> und <xref:System.Windows.Controls.StretchDirection> Enumerationen ändern das stretching Verhalten des geschachtelten <xref:System.Windows.Controls.Image>.</span><span class="sxs-lookup"><span data-stu-id="1ad4f-108"><xref:System.Windows.Controls.Button> elements that correspond to the property values for the <xref:System.Windows.Controls.Viewbox.Stretch%2A> and <xref:System.Windows.Controls.StretchDirection> enumerations manipulate the stretching behavior of the nested <xref:System.Windows.Controls.Image>.</span></span>  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="1ad4f-109">Der folgende Code-Behind-Datei verarbeitet die <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisse, die den vorherigen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="1ad4f-109">The following code-behind file handles the <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events that the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example defines.</span></span>  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1ad4f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ad4f-110">See also</span></span>
- <xref:System.Windows.Controls.Viewbox>
- <xref:System.Windows.Media.Stretch>
- <xref:System.Windows.Controls.StretchDirection>
