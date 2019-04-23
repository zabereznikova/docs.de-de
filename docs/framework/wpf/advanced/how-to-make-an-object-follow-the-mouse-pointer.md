---
title: 'Vorgehensweise: Konfigurieren eines Objekts zum Folgen des Mauszeigers'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: b9b13b4eec3e42744ba2be6031ec841fb5f215e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107314"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="6f3c6-102">Vorgehensweise: Konfigurieren eines Objekts zum Folgen des Mauszeigers</span><span class="sxs-lookup"><span data-stu-id="6f3c6-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="6f3c6-103">Dieses Beispiel zeigt, wie Sie die Dimensionen eines Objekts ändern, wenn der Mauszeiger bewegt, auf dem Bildschirm wird.</span><span class="sxs-lookup"><span data-stu-id="6f3c6-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="6f3c6-104">Das Beispiel enthält eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei, erstellt die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] und eine Code-Behind-Datei, die der Ereignishandler erstellt.</span><span class="sxs-lookup"><span data-stu-id="6f3c6-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f3c6-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f3c6-105">Example</span></span>  
 <span data-ttu-id="6f3c6-106">Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], bestehend ein <xref:System.Windows.Shapes.Ellipse> innerhalb von einer <xref:System.Windows.Controls.StackPanel>, und fügt den Ereignishandler für die <xref:System.Windows.UIElement.MouseMove> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="6f3c6-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="6f3c6-107">Der folgende Code hinter erstellt die <xref:System.Windows.UIElement.MouseMove> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="6f3c6-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="6f3c6-108">Wenn der Mauszeiger bewegt wird, die Höhe und Breite des der <xref:System.Windows.Shapes.Ellipse> erhöht und gesenkt werden.</span><span class="sxs-lookup"><span data-stu-id="6f3c6-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="6f3c6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f3c6-109">See also</span></span>

- [<span data-ttu-id="6f3c6-110">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="6f3c6-110">Input Overview</span></span>](input-overview.md)
