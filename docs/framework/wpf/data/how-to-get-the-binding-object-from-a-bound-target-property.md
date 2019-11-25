---
title: 'Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: cf2ddc93a7c46ee6956d2731a786289f64086360
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976425"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="52d56-102">Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft</span><span class="sxs-lookup"><span data-stu-id="52d56-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="52d56-103">Dieses Beispiel zeigt, wie das Bindungsobjekt aus einer datengebundenen Zieleigenschaft abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="52d56-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>

## <a name="example"></a><span data-ttu-id="52d56-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52d56-104">Example</span></span>
 <span data-ttu-id="52d56-105">Sie können Folgendes ausführen, um das <xref:System.Windows.Data.Binding> Objekt zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="52d56-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> <span data-ttu-id="52d56-106">Sie müssen die Abhängigkeitseigenschaft für die abzurufende Bindung angeben, da eventuell mehrere Eigenschaften des Zielobjekts die Datenbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="52d56-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>

 <span data-ttu-id="52d56-107">Alternativ dazu können Sie den <xref:System.Windows.Data.BindingExpression> erhalten und dann den Wert der Eigenschaft <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> erhalten.</span><span class="sxs-lookup"><span data-stu-id="52d56-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>

 <span data-ttu-id="52d56-108">Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](https://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="52d56-108">For the complete example see [Binding Validation Sample](https://go.microsoft.com/fwlink/?LinkID=159972).</span></span>

> [!NOTE]
> <span data-ttu-id="52d56-109">Wenn die Bindung eine <xref:System.Windows.Data.MultiBinding>ist, verwenden Sie <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="52d56-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="52d56-110">Wenn es sich um einen <xref:System.Windows.Data.PriorityBinding>handelt, verwenden Sie <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="52d56-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="52d56-111">Wenn Sie nicht sicher sind, ob die Ziel Eigenschaft über eine <xref:System.Windows.Data.Binding>, eine <xref:System.Windows.Data.MultiBinding>oder eine <xref:System.Windows.Data.PriorityBinding>gebunden ist, können Sie <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>verwenden.</span><span class="sxs-lookup"><span data-stu-id="52d56-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="52d56-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52d56-112">See also</span></span>

- [<span data-ttu-id="52d56-113">Erstellen einer Bindung in Code</span><span class="sxs-lookup"><span data-stu-id="52d56-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="52d56-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="52d56-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
