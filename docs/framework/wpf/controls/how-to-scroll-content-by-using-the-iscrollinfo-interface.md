---
title: 'Vorgehensweise: Durchführen eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 145c58064b8557f9cb4730ec9272c354c7aa9c1b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378977"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="2efc2-102">Vorgehensweise: Durchführen eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2efc2-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="2efc2-103">Dieses Beispiel veranschaulicht das Scrollen von Inhalt mithilfe der <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2efc2-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2efc2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2efc2-104">Example</span></span>  
 <span data-ttu-id="2efc2-105">Das folgende Beispiel veranschaulicht die Funktionen von der <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2efc2-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="2efc2-106">Das Beispiel erstellt eine <xref:System.Windows.Controls.StackPanel> Element im [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , die in ein übergeordnetes Element geschachtelt ist <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="2efc2-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="2efc2-107">Die untergeordneten Elemente des der <xref:System.Windows.Controls.StackPanel> Bildlauf möglich logisch mithilfe von definierten Methoden den <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle und die Umwandlung in die Instanz von <xref:System.Windows.Controls.StackPanel> (`sp1`) im Code.</span><span class="sxs-lookup"><span data-stu-id="2efc2-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="2efc2-108">Jede <xref:System.Windows.Controls.Button> in die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei löst eine zugeordnete benutzerdefinierte Methode, die in Scrollverhalten steuert <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="2efc2-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="2efc2-109">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> und <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> Methoden es zeigt auch generisch wie alle Methoden, die die Positionierung verwenden, die die <xref:System.Windows.Controls.Primitives.IScrollInfo> -Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="2efc2-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2efc2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2efc2-110">See also</span></span>
- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [<span data-ttu-id="2efc2-111">Übersicht über ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="2efc2-111">ScrollViewer Overview</span></span>](scrollviewer-overview.md)
- [<span data-ttu-id="2efc2-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="2efc2-112">How-to Topics</span></span>](scrollviewer-how-to-topics.md)
- [<span data-ttu-id="2efc2-113">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="2efc2-113">Panels Overview</span></span>](panels-overview.md)
