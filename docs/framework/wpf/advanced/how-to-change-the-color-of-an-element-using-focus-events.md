---
title: 'Gewusst wie: Ändern der Farbe eines Elements mithilfe von Fokusereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: d8d8a3e8b24021cf8a5f916ce3f291a3b66d9411
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543113"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="8b5af-102">Gewusst wie: Ändern der Farbe eines Elements mithilfe von Fokusereignissen</span><span class="sxs-lookup"><span data-stu-id="8b5af-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="8b5af-103">In diesem Beispiel wird gezeigt, wie die Farbe eines Elements ändern, wenn er erhält und verliert den Fokus mit der <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="8b5af-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="8b5af-104">In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine Code-Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="8b5af-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b5af-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b5af-105">Example</span></span>  
 <span data-ttu-id="8b5af-106">Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche, die aus zwei <xref:System.Windows.Controls.Button> -Objekte und fügt der Ereignishandler für die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> Ereignisse an die <xref:System.Windows.Controls.Button> Objekte.</span><span class="sxs-lookup"><span data-stu-id="8b5af-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="8b5af-107">Der folgende Code-behind erstellt die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="8b5af-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="8b5af-108">Wenn die <xref:System.Windows.Controls.Button> Tastaturfokus erhält, die <xref:System.Windows.Controls.Control.Background%2A> von der <xref:System.Windows.Controls.Button> in Rot geändert wird.</span><span class="sxs-lookup"><span data-stu-id="8b5af-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="8b5af-109">Wenn die <xref:System.Windows.Controls.Button> den Tastaturfokus verliert, der <xref:System.Windows.Controls.Control.Background%2A> von der <xref:System.Windows.Controls.Button> nicht wieder in Weiß geändert wird.</span><span class="sxs-lookup"><span data-stu-id="8b5af-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="8b5af-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b5af-110">See Also</span></span>  
 [<span data-ttu-id="8b5af-111">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="8b5af-111">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
