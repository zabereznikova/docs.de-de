---
title: 'Gewusst wie: Anpassen der Größe des Ziehpunkts auf einer Bildlaufleiste'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 689b73eb58cdfceb2ce5d4e76cbbc3d6c5af8967
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551803"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="d9bd7-102">Gewusst wie: Anpassen der Größe des Ziehpunkts auf einer Bildlaufleiste</span><span class="sxs-lookup"><span data-stu-id="d9bd7-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="d9bd7-103">In diesem Thema wird erläutert, wie festzulegende der <xref:System.Windows.Controls.Primitives.Thumb> des eine <xref:System.Windows.Controls.Primitives.ScrollBar> eine feste Größe und zum Angeben der Mindestgröße für die <xref:System.Windows.Controls.Primitives.Thumb> des eine <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="d9bd7-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9bd7-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9bd7-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="d9bd7-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9bd7-105">Description</span></span>  
 <span data-ttu-id="d9bd7-106">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.ScrollBar> , besitzt eine <xref:System.Windows.Controls.Primitives.Thumb> mit fester Größe.</span><span class="sxs-lookup"><span data-stu-id="d9bd7-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="d9bd7-107">Im Beispiel wird die <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> Eigenschaft von der <xref:System.Windows.Controls.Primitives.Thumb> auf <xref:System.Double.NaN> und legt die Höhe des der <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="d9bd7-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="d9bd7-108">Zum Erstellen einer horizontalen <xref:System.Windows.Controls.Primitives.ScrollBar> mit einem <xref:System.Windows.Controls.Primitives.Thumb> , der eine feste Breite hat, legen Sie die Breite der <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="d9bd7-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="d9bd7-109">Code</span><span class="sxs-lookup"><span data-stu-id="d9bd7-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="d9bd7-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9bd7-110">Description</span></span>  
 <span data-ttu-id="d9bd7-111">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.ScrollBar> , besitzt eine <xref:System.Windows.Controls.Primitives.Thumb> mit einer Mindestgröße.</span><span class="sxs-lookup"><span data-stu-id="d9bd7-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="d9bd7-112">Im Beispiel wird den Wert des <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="d9bd7-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="d9bd7-113">Zum Erstellen einer horizontalen <xref:System.Windows.Controls.Primitives.ScrollBar> mit einem <xref:System.Windows.Controls.Primitives.Thumb> , die eine minimale Breite hat, legen Sie die <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="d9bd7-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="d9bd7-114">Code</span><span class="sxs-lookup"><span data-stu-id="d9bd7-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d9bd7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9bd7-115">See Also</span></span>  
 [<span data-ttu-id="d9bd7-116">ScrollBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="d9bd7-116">ScrollBar Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)
