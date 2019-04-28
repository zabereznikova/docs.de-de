---
title: 'Vorgehensweise: Ändern der Farbe eines Elements mithilfe von Fokusereignissen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 744963cc543110121a777e1d4c3cdcb3cec40d9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776876"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="6be1b-102">Vorgehensweise: Ändern der Farbe eines Elements mithilfe von Fokusereignissen</span><span class="sxs-lookup"><span data-stu-id="6be1b-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="6be1b-103">In diesem Beispiel wird veranschaulicht, wie Sie die Farbe eines Elements ändern, erhält und den Fokus verliert, indem die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="6be1b-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="6be1b-104">In diesem Beispiel besteht aus einem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und eine CodeBehind-Datei.</span><span class="sxs-lookup"><span data-stu-id="6be1b-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6be1b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6be1b-105">Example</span></span>  
 <span data-ttu-id="6be1b-106">Die folgenden [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] erstellt die Benutzeroberfläche besteht aus zwei <xref:System.Windows.Controls.Button> Objekte aus, und fügt Sie Ereignishandler für die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> Ereignisse an die <xref:System.Windows.Controls.Button> Objekte.</span><span class="sxs-lookup"><span data-stu-id="6be1b-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="6be1b-107">Der folgende Code hinter erstellt die <xref:System.Windows.UIElement.GotFocus> und <xref:System.Windows.UIElement.LostFocus> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="6be1b-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="6be1b-108">Wenn die <xref:System.Windows.Controls.Button> Tastaturfokus erhält, die <xref:System.Windows.Controls.Control.Background%2A> von der <xref:System.Windows.Controls.Button> in Rot geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6be1b-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="6be1b-109">Wenn die <xref:System.Windows.Controls.Button> den Tastaturfokus verliert, die <xref:System.Windows.Controls.Control.Background%2A> von der <xref:System.Windows.Controls.Button> wieder auf Weiß geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6be1b-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="6be1b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6be1b-110">See also</span></span>

- [<span data-ttu-id="6be1b-111">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="6be1b-111">Input Overview</span></span>](input-overview.md)
