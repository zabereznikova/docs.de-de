---
title: 'Vorgehensweise: Löschen von Bindungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: 8140928d44555e399ddf4ebd73407a251ad3cffe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101418"
---
# <a name="how-to-clear-bindings"></a><span data-ttu-id="77ff0-102">Vorgehensweise: Löschen von Bindungen</span><span class="sxs-lookup"><span data-stu-id="77ff0-102">How to: Clear Bindings</span></span>
<span data-ttu-id="77ff0-103">Dieses Beispiel zeigt, wie Bindungen aus einem Objekt gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="77ff0-103">This example shows how to clear bindings from an object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77ff0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77ff0-104">Example</span></span>  
 <span data-ttu-id="77ff0-105">Um eine Bindung aus einer einzelnen Eigenschaft für ein Objekt zu löschen, rufen <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="77ff0-105">To clear a binding from an individual property on an object, call <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> as shown in the following example.</span></span> <span data-ttu-id="77ff0-106">Im folgenden Beispiel wird die Bindung aus der <xref:System.Windows.Controls.TextBlock.TextProperty> von *"MyText"*, <xref:System.Windows.Controls.TextBlock> Objekt.</span><span class="sxs-lookup"><span data-stu-id="77ff0-106">The following example removes the binding from the <xref:System.Windows.Controls.TextBlock.TextProperty> of *mytext*, a <xref:System.Windows.Controls.TextBlock> object.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 <span data-ttu-id="77ff0-107">Durch das Löschen einer Bindung wird diese entfernt, sodass die Abhängigkeitseigenschaft einen außerhalb der Bindung gültigen Wert annimmt.</span><span class="sxs-lookup"><span data-stu-id="77ff0-107">Clearing the binding removes the binding so that the value of the dependency property is changed to whatever it would have been without the binding.</span></span> <span data-ttu-id="77ff0-108">Dabei kann es sich um einen Standardwert, einen geerbten Wert oder um einen Wert aus einer Datenvorlagenbindung handeln.</span><span class="sxs-lookup"><span data-stu-id="77ff0-108">This value could be a default value, an inherited value, or a value from a data template binding.</span></span>  
  
 <span data-ttu-id="77ff0-109">Um Bindungen aus allen möglichen Eigenschaften eines Objekts zu löschen, verwenden <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span><span class="sxs-lookup"><span data-stu-id="77ff0-109">To clear bindings from all possible properties on an object, use <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77ff0-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77ff0-110">See also</span></span>

- <xref:System.Windows.Data.BindingOperations>
- [<span data-ttu-id="77ff0-111">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="77ff0-111">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="77ff0-112">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="77ff0-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
