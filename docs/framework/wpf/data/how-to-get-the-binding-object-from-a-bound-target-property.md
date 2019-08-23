---
title: 'Vorgehensweise: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c7aacc2145ffe98ec7b58afb3b2e3dca151ef0ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965437"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="193b4-102">Vorgehensweise: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft</span><span class="sxs-lookup"><span data-stu-id="193b4-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="193b4-103">Dieses Beispiel zeigt, wie das Bindungsobjekt aus einer datengebundenen Zieleigenschaft abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="193b4-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="193b4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="193b4-104">Example</span></span>  
 <span data-ttu-id="193b4-105">Zum erhalten des <xref:System.Windows.Data.Binding> -Objekts können Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="193b4-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>  
  
 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
> <span data-ttu-id="193b4-106">Sie müssen die Abhängigkeitseigenschaft für die abzurufende Bindung angeben, da eventuell mehrere Eigenschaften des Zielobjekts die Datenbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="193b4-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>  
  
 <span data-ttu-id="193b4-107">Alternativ können Sie das <xref:System.Windows.Data.BindingExpression> - <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> Objekt und dann den Wert der-Eigenschaft erhalten.</span><span class="sxs-lookup"><span data-stu-id="193b4-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>  
  
 <span data-ttu-id="193b4-108">Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](https://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="193b4-108">For the complete example see [Binding Validation Sample](https://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="193b4-109">Wenn die Bindung eine <xref:System.Windows.Data.MultiBinding>ist, verwenden <xref:System.Windows.Data.BindingOperations>Sie.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A></span><span class="sxs-lookup"><span data-stu-id="193b4-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span></span> <span data-ttu-id="193b4-110">Wenn es sich um <xref:System.Windows.Data.PriorityBinding>einen handelt <xref:System.Windows.Data.BindingOperations>,<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>verwenden Sie.</span><span class="sxs-lookup"><span data-stu-id="193b4-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span></span> <span data-ttu-id="193b4-111">Wenn Sie nicht sicher sind, ob die Ziel Eigenschaft mit einem <xref:System.Windows.Data.Binding>, einem <xref:System.Windows.Data.MultiBinding>oder einem <xref:System.Windows.Data.PriorityBinding>gebunden ist, können Sie <xref:System.Windows.Data.BindingOperations>verwenden<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="193b4-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="193b4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="193b4-112">See also</span></span>

- [<span data-ttu-id="193b4-113">Erstellen einer Bindung in Code</span><span class="sxs-lookup"><span data-stu-id="193b4-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="193b4-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="193b4-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
