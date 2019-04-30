---
title: 'Vorgehensweise: Anpassen der Größe des Ziehpunkts auf einer Scrollleiste'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 60ae7c4e95801036c5deb0c485645297509b830c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911052"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="ac29b-102">Vorgehensweise: Anpassen der Größe des Ziehpunkts auf einer Scrollleiste</span><span class="sxs-lookup"><span data-stu-id="ac29b-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="ac29b-103">In diesem Thema erläutert das Einrichten der <xref:System.Windows.Controls.Primitives.Thumb> von eine <xref:System.Windows.Controls.Primitives.ScrollBar> eine feste Größe und eine Mindestgröße für angeben der <xref:System.Windows.Controls.Primitives.Thumb> von eine <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="ac29b-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac29b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac29b-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="ac29b-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac29b-105">Description</span></span>  
 <span data-ttu-id="ac29b-106">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.ScrollBar> , bei dem ein <xref:System.Windows.Controls.Primitives.Thumb> mit fester Größe.</span><span class="sxs-lookup"><span data-stu-id="ac29b-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="ac29b-107">Im Beispiel wird die <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> Eigenschaft der <xref:System.Windows.Controls.Primitives.Thumb> zu <xref:System.Double.NaN> und legt die Höhe des der <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="ac29b-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="ac29b-108">Zum Erstellen einer horizontalen <xref:System.Windows.Controls.Primitives.ScrollBar> mit einer <xref:System.Windows.Controls.Primitives.Thumb> , der eine feste Breite hat, legen Sie die Breite der <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="ac29b-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="ac29b-109">Code</span><span class="sxs-lookup"><span data-stu-id="ac29b-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="ac29b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac29b-110">Description</span></span>  
 <span data-ttu-id="ac29b-111">Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.ScrollBar> , bei dem ein <xref:System.Windows.Controls.Primitives.Thumb> mit einer Mindestgröße.</span><span class="sxs-lookup"><span data-stu-id="ac29b-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="ac29b-112">Im Beispiel wird den Wert des <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac29b-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="ac29b-113">Zum Erstellen einer horizontalen <xref:System.Windows.Controls.Primitives.ScrollBar> mit einem <xref:System.Windows.Controls.Primitives.Thumb> , die eine minimale Breite hat, legen Sie die <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac29b-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="ac29b-114">Code</span><span class="sxs-lookup"><span data-stu-id="ac29b-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ac29b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac29b-115">See also</span></span>

- [<span data-ttu-id="ac29b-116">ScrollBar-Stile und -Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ac29b-116">ScrollBar Styles and Templates</span></span>](scrollbar-styles-and-templates.md)
