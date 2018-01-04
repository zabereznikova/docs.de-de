---
title: 'Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f5369bc770a31aa99f1fb11bfec790eb8fe091d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="46ddb-102">Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft</span><span class="sxs-lookup"><span data-stu-id="46ddb-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="46ddb-103">Dieses Beispiel zeigt, wie das Bindungsobjekt aus einer datengebundenen Zieleigenschaft abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="46ddb-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46ddb-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46ddb-104">Example</span></span>  
 <span data-ttu-id="46ddb-105">Sie können Folgendes zum Abrufen der <xref:System.Windows.Data.Binding> Objekt:</span><span class="sxs-lookup"><span data-stu-id="46ddb-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  <span data-ttu-id="46ddb-106">Sie müssen die Abhängigkeitseigenschaft für die abzurufende Bindung angeben, da eventuell mehrere Eigenschaften des Zielobjekts die Datenbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="46ddb-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>  
  
 <span data-ttu-id="46ddb-107">Alternativ können Sie Abrufen der <xref:System.Windows.Data.BindingExpression> und rufen Sie anschließend den Wert, der die <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="46ddb-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>  
  
 <span data-ttu-id="46ddb-108">Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](http://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="46ddb-108">For the complete example see [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46ddb-109">Wenn die Bindung ist eine <xref:System.Windows.Data.MultiBinding>, verwenden Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="46ddb-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span></span> <span data-ttu-id="46ddb-110">Es ist ein <xref:System.Windows.Data.PriorityBinding>, verwenden Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="46ddb-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span></span> <span data-ttu-id="46ddb-111">Wenn Sie unsicher sind, ob die Eigenschaft gebunden ist mit einem <xref:System.Windows.Data.Binding>, eine <xref:System.Windows.Data.MultiBinding>, oder ein <xref:System.Windows.Data.PriorityBinding>, können Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="46ddb-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ddb-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46ddb-112">See Also</span></span>  
 [<span data-ttu-id="46ddb-113">Erstellen einer Bindung in Code</span><span class="sxs-lookup"><span data-stu-id="46ddb-113">Create a Binding in Code</span></span>](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [<span data-ttu-id="46ddb-114">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="46ddb-114">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
