---
title: 'Gewusst wie: Binden an eine Enumeration'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 93f33e497fd7acb81c55f86bf38737d4e7d79bf2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454439"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="18a5b-102">Gewusst wie: Binden an eine Enumeration</span><span class="sxs-lookup"><span data-stu-id="18a5b-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="18a5b-103">Dieses Beispiel zeigt, wie Sie eine Bindung an eine Enumeration durch Binden an die GetValues-Methode der-Enumeration herstellen.</span><span class="sxs-lookup"><span data-stu-id="18a5b-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18a5b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="18a5b-104">Example</span></span>  
 <span data-ttu-id="18a5b-105">Im folgenden Beispiel zeigt der <xref:System.Windows.Controls.ListBox> die Liste der <xref:System.Windows.HorizontalAlignment> Enumerationswerte durch Datenbindung an.</span><span class="sxs-lookup"><span data-stu-id="18a5b-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="18a5b-106">Die <xref:System.Windows.Controls.ListBox> und die <xref:System.Windows.Controls.Button> sind so gebunden, dass Sie den <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>-Eigenschafts Wert der <xref:System.Windows.Controls.Button> ändern können, indem Sie im <xref:System.Windows.Controls.ListBox>einen Wert auswählen.</span><span class="sxs-lookup"><span data-stu-id="18a5b-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="18a5b-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18a5b-107">See also</span></span>

- [<span data-ttu-id="18a5b-108">Binden an eine Methode</span><span class="sxs-lookup"><span data-stu-id="18a5b-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="18a5b-109">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="18a5b-109">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="18a5b-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="18a5b-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
