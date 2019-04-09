---
title: 'Vorgehensweise: Erstellen eines Expanders mit einem ScrollViewer'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: ef0bc5d344f7d465de9209708430d3e61d40d4f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59114649"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="bc697-102">Vorgehensweise: Erstellen eines Expanders mit einem ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="bc697-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="bc697-103">Dieses Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Expander> -Steuerelement, das komplexen Inhalt, z. B. ein Bild und Text enthält.</span><span class="sxs-lookup"><span data-stu-id="bc697-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="bc697-104">Dieses Beispiel enthält auch den Inhalt der <xref:System.Windows.Controls.Expander> in einem <xref:System.Windows.Controls.ScrollViewer> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bc697-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc697-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc697-105">Example</span></span>  
 <span data-ttu-id="bc697-106">Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Expander>.</span><span class="sxs-lookup"><span data-stu-id="bc697-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="bc697-107">Im Beispiel wird eine <xref:System.Windows.Controls.Primitives.BulletDecorator> Steuerelement, das ein Bild und Text enthält, um zu definieren die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc697-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="bc697-108">Ein <xref:System.Windows.Controls.ScrollViewer> Steuerelement stellt eine Methode zum Durchführen eines Bildlaufs des erweiterten Inhalts.</span><span class="sxs-lookup"><span data-stu-id="bc697-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="bc697-109">Beachten Sie, die im Beispiel wird die <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft für die <xref:System.Windows.Controls.ScrollViewer> anstelle von auf dem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="bc697-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="bc697-110">Wenn die <xref:System.Windows.FrameworkElement.Height%2A> festgelegt ist, auf dem Inhalt der <xref:System.Windows.Controls.ScrollViewer> lässt sich nicht auf der Benutzer den Inhalt einen Bildlauf durchführen.</span><span class="sxs-lookup"><span data-stu-id="bc697-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="bc697-111">Die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft wird festgelegt, auf die <xref:System.Windows.Controls.Expander> Kontrolle und diese Einstellung gilt für die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> und den erweiterten Inhalt.</span><span class="sxs-lookup"><span data-stu-id="bc697-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="bc697-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc697-112">See also</span></span>

- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="bc697-113">Übersicht über Expander-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="bc697-113">Expander Overview</span></span>](expander-overview.md)
- [<span data-ttu-id="bc697-114">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="bc697-114">How-to Topics</span></span>](expander-how-to-topics.md)
