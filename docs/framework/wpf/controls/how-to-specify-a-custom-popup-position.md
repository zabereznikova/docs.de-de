---
title: 'Gewusst wie: Angeben einer benutzerdefinierten Popup-Position'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: e6e81a6e0819ba3eb39a1c568e6872414e671544
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46473381"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="f1e4e-102">Gewusst wie: Angeben einer benutzerdefinierten Popup-Position</span><span class="sxs-lookup"><span data-stu-id="f1e4e-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="f1e4e-103">Dieses Beispiel zeigt, wie eine benutzerdefinierte Position für ein <xref:System.Windows.Controls.Primitives.Popup> steuern, wann die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="f1e4e-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1e4e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1e4e-104">Example</span></span>  
 <span data-ttu-id="f1e4e-105">Wenn die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> Ruft eine definierte Instanz von der <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegieren.</span><span class="sxs-lookup"><span data-stu-id="f1e4e-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="f1e4e-106">Dieser Delegat gibt eine Reihe von möglichen Punkte, die relativ zu der oberen linken Ecke des Zielbereichs und der oberen linken Ecke des sind die <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="f1e4e-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="f1e4e-107">Die <xref:System.Windows.Controls.Primitives.Popup> Platzierung tritt ein, an dem Punkt, der der besten Sichtbarkeit.</span><span class="sxs-lookup"><span data-stu-id="f1e4e-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="f1e4e-108">Das folgende Beispiel zeigt, wie Sie die Position des definieren eine <xref:System.Windows.Controls.Primitives.Popup> durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="f1e4e-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="f1e4e-109">Darüber hinaus wird zum Erstellen und Zuweisen einer <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Delegat zum Positionieren der <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="f1e4e-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="f1e4e-110">Gibt der Callback-Delegaten zurück, zwei <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="f1e4e-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="f1e4e-111">Wenn die <xref:System.Windows.Controls.Primitives.Popup> von einem Bildschirmrand bei der ersten Position wird ausgeblendet, die <xref:System.Windows.Controls.Primitives.Popup> an zweiter Stelle platziert.</span><span class="sxs-lookup"><span data-stu-id="f1e4e-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="f1e4e-112">Das vollständige Beispiel finden Sie unter [Beispiel](https://go.microsoft.com/fwlink/?LinkID=160032).</span><span class="sxs-lookup"><span data-stu-id="f1e4e-112">For the complete sample, see [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e4e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1e4e-113">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="f1e4e-114">Übersicht über Popups</span><span class="sxs-lookup"><span data-stu-id="f1e4e-114">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [<span data-ttu-id="f1e4e-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f1e4e-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)
