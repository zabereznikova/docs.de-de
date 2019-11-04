---
title: 'Gewusst wie: Erstellen einer Bindung in Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 616487a16ebbe6e23fe067fb7ce72644aa3f919f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458843"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="2e857-102">Gewusst wie: Erstellen einer Bindung in Code</span><span class="sxs-lookup"><span data-stu-id="2e857-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="2e857-103">In diesem Beispiel wird gezeigt, wie eine <xref:System.Windows.Data.Binding> im Code erstellt und festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2e857-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e857-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e857-104">Example</span></span>  
 <span data-ttu-id="2e857-105">Die <xref:System.Windows.FrameworkElement>-Klasse und die <xref:System.Windows.FrameworkContentElement>-Klasse machen beide eine `SetBinding`-Methode verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2e857-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="2e857-106">Wenn Sie ein Element binden, das eine dieser Klassen erbt, können Sie die <xref:System.Windows.FrameworkElement.SetBinding%2A>-Methode direkt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2e857-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="2e857-107">Im folgenden Beispiel wird eine Klasse mit dem Namen `MyData`erstellt, die eine Eigenschaft mit dem Namen `MyDataProperty`enthält.</span><span class="sxs-lookup"><span data-stu-id="2e857-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="2e857-108">Im folgenden Beispiel wird gezeigt, wie ein Bindungs Objekt erstellt wird, um die Quelle der Bindung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2e857-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="2e857-109">Im Beispiel wird <xref:System.Windows.FrameworkElement.SetBinding%2A> verwendet, um die <xref:System.Windows.Controls.TextBlock.Text%2A>-Eigenschaft von `myText`, die ein <xref:System.Windows.Controls.TextBlock> Steuerelement ist, an `MyDataProperty`zu binden.</span><span class="sxs-lookup"><span data-stu-id="2e857-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="2e857-110">Das Codebeispiel für den gesamten Code finden Sie unter Beispiel für reine [Code Bindung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="2e857-110">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="2e857-111">Anstatt <xref:System.Windows.FrameworkElement.SetBinding%2A>aufrufen zu können, können Sie die <xref:System.Windows.Data.BindingOperations.SetBinding%2A> statische Methode der <xref:System.Windows.Data.BindingOperations>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e857-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="2e857-112">Im folgenden Beispiel wird <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> anstelle von <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> aufgerufen, um `myText` an `myDataProperty`zu binden.</span><span class="sxs-lookup"><span data-stu-id="2e857-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="2e857-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e857-113">See also</span></span>

- [<span data-ttu-id="2e857-114">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="2e857-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="2e857-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="2e857-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
