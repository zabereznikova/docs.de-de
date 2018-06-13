---
title: 'Gewusst wie: Angeben einer benutzerdefinierten Popup-Position'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: 8714cfa4f7e5bb0ca157ee9d551392571303f60e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551738"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="055f1-102">Gewusst wie: Angeben einer benutzerdefinierten Popup-Position</span><span class="sxs-lookup"><span data-stu-id="055f1-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="055f1-103">In diesem Beispiel wird gezeigt, wie eine benutzerdefinierte Position für an einer <xref:System.Windows.Controls.Primitives.Popup> steuern, wann die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="055f1-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="055f1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="055f1-104">Example</span></span>  
 <span data-ttu-id="055f1-105">Wenn die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, die <xref:System.Windows.Controls.Primitives.Popup> Ruft eine definierte Instanz von der <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegieren.</span><span class="sxs-lookup"><span data-stu-id="055f1-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="055f1-106">Dieser Delegat gibt einen Satz von möglichen Punkten, die relativ zu der oberen linken Ecke des Zielbereichs und der oberen linken Ecke des sind die <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="055f1-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="055f1-107">Die <xref:System.Windows.Controls.Primitives.Popup> Platzierung tritt auf, an dem Punkt, der die beste Sichtbarkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="055f1-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="055f1-108">Das folgende Beispiel zeigt, wie die Position des definiert eine <xref:System.Windows.Controls.Primitives.Popup> durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="055f1-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="055f1-109">Außerdem wird gezeigt, wie zum Erstellen und Zuweisen einer <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Delegaten zum Positionieren der <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="055f1-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="055f1-110">Der Rückrufdelegat gibt zwei <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="055f1-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="055f1-111">Wenn die <xref:System.Windows.Controls.Primitives.Popup> verborgen ist, indem eine Bildschirmkante der erste Position der <xref:System.Windows.Controls.Primitives.Popup> an zweiter Stelle platziert wird.</span><span class="sxs-lookup"><span data-stu-id="055f1-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="055f1-112">Das vollständige Beispiel finden Sie unter [Popup-Platzierung Sample](http://go.microsoft.com/fwlink/?LinkID=160032).</span><span class="sxs-lookup"><span data-stu-id="055f1-112">For the complete sample, see [Popup Placement Sample](http://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="055f1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="055f1-113">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="055f1-114">Übersicht über Popups</span><span class="sxs-lookup"><span data-stu-id="055f1-114">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [<span data-ttu-id="055f1-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="055f1-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
