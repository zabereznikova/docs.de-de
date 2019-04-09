---
title: 'Vorgehensweise: Binden an eine Enumeration'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 5026261366d6abde82790f05780d8ba2c29c4a49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210021"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="9db40-102">Vorgehensweise: Binden an eine Enumeration</span><span class="sxs-lookup"><span data-stu-id="9db40-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="9db40-103">Dieses Beispiel zeigt, wie an eine Enumeration, durch Bindung an eine Methode für die Enumeration des GetValues gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="9db40-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9db40-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9db40-104">Example</span></span>  
 <span data-ttu-id="9db40-105">Im folgenden Beispiel die <xref:System.Windows.Controls.ListBox> zeigt die Liste der <xref:System.Windows.HorizontalAlignment> Enumerationswerte mithilfe der Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="9db40-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="9db40-106">Die <xref:System.Windows.Controls.ListBox> und <xref:System.Windows.Controls.Button> gebunden sind, sodass Sie ändern können, die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Eigenschaftswert, der die <xref:System.Windows.Controls.Button> durch Auswählen eines Werts in der <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="9db40-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="9db40-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9db40-107">See also</span></span>

- [<span data-ttu-id="9db40-108">Binden an eine Methode</span><span class="sxs-lookup"><span data-stu-id="9db40-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="9db40-109">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="9db40-109">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="9db40-110">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="9db40-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
