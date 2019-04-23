---
title: 'Vorgehensweise: Erstellen einer Bindung in Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 57ec845c5c9a5bddb801428b9ecde035a97cf447
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089262"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="05a30-102">Vorgehensweise: Erstellen einer Bindung in Code</span><span class="sxs-lookup"><span data-stu-id="05a30-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="05a30-103">Dieses Beispiel veranschaulicht das Erstellen und Festlegen einer <xref:System.Windows.Data.Binding> im Code.</span><span class="sxs-lookup"><span data-stu-id="05a30-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05a30-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05a30-104">Example</span></span>  
 <span data-ttu-id="05a30-105">Die <xref:System.Windows.FrameworkElement> Klasse und die <xref:System.Windows.FrameworkContentElement> Klasse, die beide verfügbar machen, eine `SetBinding` Methode.</span><span class="sxs-lookup"><span data-stu-id="05a30-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="05a30-106">Wenn Sie ein Element, die eine dieser Klassen erbt binden, können Sie rufen die <xref:System.Windows.FrameworkElement.SetBinding%2A> -Methode direkt.</span><span class="sxs-lookup"><span data-stu-id="05a30-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="05a30-107">Das folgende Beispiel erstellt eine Klasse, die mit dem Namen `MyData`, enthält eine Eigenschaft namens `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="05a30-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="05a30-108">Das folgende Beispiel zeigt, wie Sie erstellen ein Binding-Objekt, um die Quelle der Bindung festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="05a30-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="05a30-109">Im Beispiel wird <xref:System.Windows.FrameworkElement.SetBinding%2A> zum Binden der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft `myText`, d.h. eine <xref:System.Windows.Controls.TextBlock> Steuerelements, auf `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="05a30-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="05a30-110">Das vollständige Codebeispiel finden Sie unter [nur ein Beispiel für die Bindung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="05a30-110">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="05a30-111">Statt <xref:System.Windows.FrameworkElement.SetBinding%2A>, können Sie die <xref:System.Windows.Data.BindingOperations.SetBinding%2A> statische Methode der <xref:System.Windows.Data.BindingOperations> Klasse.</span><span class="sxs-lookup"><span data-stu-id="05a30-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="05a30-112">Das folgende Beispiel auszuführen, ruft <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> anstelle von <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> binden `myText` zu `myDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="05a30-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="05a30-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05a30-113">See also</span></span>

- [<span data-ttu-id="05a30-114">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="05a30-114">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="05a30-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="05a30-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
