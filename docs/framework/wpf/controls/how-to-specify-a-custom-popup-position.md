---
title: 'Gewusst wie: Angeben einer benutzerdefinierten Popup-Position'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: b48dedc044b418062642af5c5bb40afab78a3c97
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635751"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="bf440-102">Gewusst wie: Angeben einer benutzerdefinierten Popup-Position</span><span class="sxs-lookup"><span data-stu-id="bf440-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="bf440-103">In diesem Beispiel wird gezeigt, <xref:System.Windows.Controls.Primitives.Popup> wie Sie <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> eine benutzerdefinierte Position für ein Steuerelement angeben, wenn die Eigenschaft auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="bf440-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf440-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf440-104">Example</span></span>  
 <span data-ttu-id="bf440-105">Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> die Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>auf <xref:System.Windows.Controls.Primitives.Popup> festgelegt ist, ruft <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> der eine definierte Instanz des Delegaten auf.</span><span class="sxs-lookup"><span data-stu-id="bf440-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="bf440-106">Dieser Delegat gibt eine Reihe möglicher Punkte zurück, die relativ zur oberen linken <xref:System.Windows.Controls.Primitives.Popup>Ecke des Zielbereichs und der oberen linken Ecke des sind.</span><span class="sxs-lookup"><span data-stu-id="bf440-106">This delegate returns a set of possible points that are relative to the top-left corner of the target area and the top-left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="bf440-107">Die <xref:System.Windows.Controls.Primitives.Popup> Platzierung erfolgt an dem Punkt, der die beste Sichtbarkeit bietet.</span><span class="sxs-lookup"><span data-stu-id="bf440-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="bf440-108">Das folgende Beispiel zeigt, wie <xref:System.Windows.Controls.Primitives.Popup> Sie die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Position <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>von a definieren, indem Sie die Eigenschaft auf festlegen.</span><span class="sxs-lookup"><span data-stu-id="bf440-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="bf440-109">Außerdem wird gezeigt, wie <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Sie einen Delegaten <xref:System.Windows.Controls.Primitives.Popup>erstellen und zuweisen, um die zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="bf440-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="bf440-110">Der Rückrufseleger gibt zwei <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="bf440-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="bf440-111">Wenn <xref:System.Windows.Controls.Primitives.Popup> der durch eine Bildschirmkante an der <xref:System.Windows.Controls.Primitives.Popup> ersten Position ausgeblendet wird, wird der an der zweiten Position platziert.</span><span class="sxs-lookup"><span data-stu-id="bf440-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="bf440-112">Das vollständige Beispiel finden Sie unter [Popup-Platzierungsbeispiel](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span><span class="sxs-lookup"><span data-stu-id="bf440-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf440-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf440-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="bf440-114">Popup-Übersicht</span><span class="sxs-lookup"><span data-stu-id="bf440-114">Popup overview</span></span>](popup-overview.md)
- [<span data-ttu-id="bf440-115">How-to-Artikel</span><span class="sxs-lookup"><span data-stu-id="bf440-115">How-to articles</span></span>](popup-how-to-topics.md)
