---
title: 'Gewusst wie: Erstellen einer Bindung in Code'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d2ad9f855f1051ad6c0afac6bc813eecf87f7d36
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="0f0b0-102">Gewusst wie: Erstellen einer Bindung in Code</span><span class="sxs-lookup"><span data-stu-id="0f0b0-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="0f0b0-103">In diesem Beispiel wird gezeigt, wie das Erstellen und Festlegen einer <xref:System.Windows.Data.Binding> im Code.</span><span class="sxs-lookup"><span data-stu-id="0f0b0-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f0b0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f0b0-104">Example</span></span>  
 <span data-ttu-id="0f0b0-105">Die <xref:System.Windows.FrameworkElement> Klasse und die <xref:System.Windows.FrameworkContentElement> Klasse sowohl verfügbar machen eine `SetBinding` Methode.</span><span class="sxs-lookup"><span data-stu-id="0f0b0-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="0f0b0-106">Wenn Sie ein Element, das entweder dieser Klassen erbt binden, können Sie rufen die <xref:System.Windows.FrameworkElement.SetBinding%2A> -Methode direkt.</span><span class="sxs-lookup"><span data-stu-id="0f0b0-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="0f0b0-107">Das folgende Beispiel erstellt eine Klasse namens, `MyData`, enthält eine Eigenschaft namens `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="0f0b0-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="0f0b0-108">Im folgende Beispiel wird gezeigt, wie zum Erstellen eines Objekts Bindung, um die Quelle der Bindung festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0f0b0-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="0f0b0-109">Im Beispiel wird <xref:System.Windows.FrameworkElement.SetBinding%2A> zum Binden der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft `myText`, also eine <xref:System.Windows.Controls.TextBlock> -Steuerelement zur `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="0f0b0-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="0f0b0-110">Das vollständige Codebeispiel finden Sie unter [Code nur ein Beispiel für die Bindung](http://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).</span><span class="sxs-lookup"><span data-stu-id="0f0b0-110">For the complete code sample, see [Code-only Binding Sample](http://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6).</span></span>  
  
 <span data-ttu-id="0f0b0-111">Statt <xref:System.Windows.FrameworkElement.SetBinding%2A>, können Sie die <xref:System.Windows.Data.BindingOperations.SetBinding%2A> statische Methode der <xref:System.Windows.Data.BindingOperations> Klasse.</span><span class="sxs-lookup"><span data-stu-id="0f0b0-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="0f0b0-112">Das folgende Beispiel, das Aufrufe <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> anstelle von <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> binden `myText` auf `myDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="0f0b0-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="0f0b0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f0b0-113">See Also</span></span>  
 [<span data-ttu-id="0f0b0-114">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="0f0b0-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="0f0b0-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0f0b0-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
