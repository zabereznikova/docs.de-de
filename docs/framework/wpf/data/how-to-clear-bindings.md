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
ms.openlocfilehash: 66f7eb0209d23660b9c7351ca793f509b2f4bb8d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458877"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="a1892-102">Gewusst wie: Löschen von Bindungen</span><span class="sxs-lookup"><span data-stu-id="a1892-102">How to: Clear Bindings</span></span>
<span data-ttu-id="a1892-103">Dieses Beispiel zeigt, wie Bindungen aus einem Objekt gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a1892-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1892-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1892-104">Example</span></span>  
 <span data-ttu-id="a1892-105">Um eine Bindung aus einer einzelnen Eigenschaft eines Objekts zu löschen, nennen Sie <xref:System.Windows.Data.BindingOperations.ClearBinding%2A>, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1892-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="a1892-106">Im folgenden Beispiel wird die-Bindung aus dem <xref:System.Windows.Controls.TextBlock.TextProperty> von *MyText*entfernt, einem <xref:System.Windows.Controls.TextBlock>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="a1892-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="a1892-107">Durch das Löschen einer Bindung wird diese entfernt, sodass die Abhängigkeitseigenschaft einen außerhalb der Bindung gültigen Wert annimmt.</span><span class="sxs-lookup"><span data-stu-id="a1892-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="a1892-108">Dabei kann es sich um einen Standardwert, einen geerbten Wert oder um einen Wert aus einer Datenvorlagenbindung handeln.</span><span class="sxs-lookup"><span data-stu-id="a1892-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="a1892-109">Um Bindungen aus allen möglichen Eigenschaften eines Objekts zu löschen, verwenden Sie <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="a1892-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1892-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1892-110">See also</span></span>

- <xref:System.Windows.Data.BindingOperations>
- [<span data-ttu-id="a1892-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="a1892-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="a1892-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="a1892-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
