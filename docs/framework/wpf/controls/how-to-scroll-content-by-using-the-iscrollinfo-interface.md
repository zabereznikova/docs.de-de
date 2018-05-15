---
title: 'Gewusst wie: Durchführen eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 8154a626c6bf48a59be0540f857c0c51d59a26c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a><span data-ttu-id="8b369-102">Gewusst wie: Durchführen eines Bildlaufs von Inhalten mithilfe der IScrollInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b369-102">How to: Scroll Content by Using the IScrollInfo Interface</span></span>
<span data-ttu-id="8b369-103">In diesem Beispiel wird gezeigt, wie einen Bildlauf im Inhalt mithilfe der <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="8b369-103">This example shows how to scroll content by using the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b369-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b369-104">Example</span></span>  
 <span data-ttu-id="8b369-105">Das folgende Beispiel veranschaulicht die Funktionen des die <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="8b369-105">The following example demonstrates the features of the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface.</span></span> <span data-ttu-id="8b369-106">Das Beispiel erstellt eine <xref:System.Windows.Controls.StackPanel> Element im [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , die in ein übergeordnetes Element geschachtelt ist <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="8b369-106">The example creates a <xref:System.Windows.Controls.StackPanel> element in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that is nested in a parent <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="8b369-107">Die untergeordneten Elemente des der <xref:System.Windows.Controls.StackPanel> können mithilfe von definierten Methoden logisch gescrollt werden die <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle und die Umwandlung in der Instanz von <xref:System.Windows.Controls.StackPanel> (`sp1`) im Code.</span><span class="sxs-lookup"><span data-stu-id="8b369-107">The child elements of the <xref:System.Windows.Controls.StackPanel> can be scrolled logically by using the methods defined by the <xref:System.Windows.Controls.Primitives.IScrollInfo> interface and cast to the instance of <xref:System.Windows.Controls.StackPanel> (`sp1`) in code.</span></span>  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="8b369-108">Jede <xref:System.Windows.Controls.Button> in der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei löst eine zugeordnete benutzerdefinierte Methode, die in Scrollverhalten steuert <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="8b369-108">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file triggers an associated custom method that controls scrolling behavior in <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="8b369-109">Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> und <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> -Methoden auch generisch wird gezeigt, wie die Positionierung Methoden verwenden, die die <xref:System.Windows.Controls.Primitives.IScrollInfo> Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="8b369-109">The following example shows how to use the <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> and <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> methods; it also generically shows how to use all the positioning methods that the <xref:System.Windows.Controls.Primitives.IScrollInfo> class defines.</span></span>  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8b369-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b369-110">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 <xref:System.Windows.Controls.StackPanel>  
 [<span data-ttu-id="8b369-111">Übersicht über ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="8b369-111">ScrollViewer Overview</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)  
 [<span data-ttu-id="8b369-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="8b369-112">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)  
 [<span data-ttu-id="8b369-113">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="8b369-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
