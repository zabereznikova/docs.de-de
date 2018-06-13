---
title: 'Gewusst wie: Löschen von Bindungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: f66477fc857a9e7a065e01b8cddf43789042b59c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555856"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="f7568-102">Gewusst wie: Löschen von Bindungen</span><span class="sxs-lookup"><span data-stu-id="f7568-102">How to: Clear Bindings</span></span>
<span data-ttu-id="f7568-103">Dieses Beispiel zeigt, wie Bindungen aus einem Objekt gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f7568-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7568-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7568-104">Example</span></span>  
 <span data-ttu-id="f7568-105">Um eine Bindung aus einer einzelnen Eigenschaft für ein Objekt zu löschen, rufen <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7568-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="f7568-106">Im folgende Beispiel entfernt die Bindung aus der <xref:System.Windows.Controls.TextBlock.TextProperty> von *Mytext*ein <xref:System.Windows.Controls.TextBlock> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f7568-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="f7568-107">Durch das Löschen einer Bindung wird diese entfernt, sodass die Abhängigkeitseigenschaft einen außerhalb der Bindung gültigen Wert annimmt.</span><span class="sxs-lookup"><span data-stu-id="f7568-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="f7568-108">Dabei kann es sich um einen Standardwert, einen geerbten Wert oder um einen Wert aus einer Datenvorlagenbindung handeln.</span><span class="sxs-lookup"><span data-stu-id="f7568-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="f7568-109">Verwenden, um Bindungen aus allen möglichen Eigenschaften für ein Objekt zu löschen, <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7568-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7568-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7568-110">See Also</span></span>  
 <xref:System.Windows.Data.BindingOperations>  
 [<span data-ttu-id="f7568-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="f7568-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f7568-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f7568-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
