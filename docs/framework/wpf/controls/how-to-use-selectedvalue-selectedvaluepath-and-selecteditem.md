---
title: 'Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem'
description: Erfahren Sie, wie Sie mit den Eigenschaften SelectedValue und SelectedValuePath einen Wert für das SelectedItem-Element einer Windows Presentation Foundation TreeView angeben.
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: ddac2455dee0bf69d25307340eddd5364e43e823
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166272"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="414bf-103">Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem</span><span class="sxs-lookup"><span data-stu-id="414bf-103">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="414bf-104">In diesem Beispiel wird gezeigt, wie die-Eigenschaft und die-Eigenschaft verwendet werden <xref:System.Windows.Controls.TreeView.SelectedValue%2A> <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> , um einen Wert für den einer anzugeben <xref:System.Windows.Controls.TreeView.SelectedItem%2A> <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="414bf-104">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="414bf-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="414bf-105">Example</span></span>  
 <span data-ttu-id="414bf-106">Die- <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft stellt eine Möglichkeit zum Angeben eines <xref:System.Windows.Controls.TreeView.SelectedValue%2A> für den <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in einer bereit <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="414bf-106">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="414bf-107"><xref:System.Windows.Controls.TreeView.SelectedItem%2A>Stellt ein Objekt in der Auflistung dar <xref:System.Windows.Controls.ItemsControl.Items%2A> und <xref:System.Windows.Controls.TreeView> zeigt den Wert einer einzelnen Eigenschaft des ausgewählten Elements an.</span><span class="sxs-lookup"><span data-stu-id="414bf-107">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="414bf-108">Die- <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft gibt den Pfad zu der Eigenschaft an, die verwendet wird, um den Wert der-Eigenschaft zu bestimmen <xref:System.Windows.Controls.TreeView.SelectedValue%2A> .</span><span class="sxs-lookup"><span data-stu-id="414bf-108">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="414bf-109">In den Beispielen in diesem Thema wird dieses Konzept veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="414bf-109">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="414bf-110">Das folgende Beispiel zeigt eine <xref:System.Windows.Data.XmlDataProvider> , die Mitarbeiter Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="414bf-110">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="414bf-111">Im folgenden Beispiel wird eine definiert <xref:System.Windows.HierarchicalDataTemplate> , `EmployeeName` mit der und der angezeigt werden `EmployeeWorkDay` `Employee` .</span><span class="sxs-lookup"><span data-stu-id="414bf-111">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="414bf-112">Beachten Sie, dass die <xref:System.Windows.HierarchicalDataTemplate> nicht `EmployeeNumber` als Teil der Vorlage angibt.</span><span class="sxs-lookup"><span data-stu-id="414bf-112">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="414bf-113">Das folgende Beispiel zeigt einen <xref:System.Windows.Controls.TreeView> , der den zuvor definierten verwendet <xref:System.Windows.HierarchicalDataTemplate> und die- <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft auf festlegt `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="414bf-113">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="414bf-114">Wenn Sie ein `EmployeeName` in der auswählen <xref:System.Windows.Controls.TreeView> , gibt die- <xref:System.Windows.Controls.TreeView.SelectedItem%2A> Eigenschaft das `EmployeeInfo` Datenelement zurück, das dem ausgewählten entspricht `EmployeeName` .</span><span class="sxs-lookup"><span data-stu-id="414bf-114">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="414bf-115">Da jedoch <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> <xref:System.Windows.Controls.TreeView> auf festgelegt ist `EmployeeNumber` , <xref:System.Windows.Controls.TreeView.SelectedValue%2A> wird der auf festgelegt `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="414bf-115">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="414bf-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="414bf-116">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="414bf-117">Übersicht über TreeView</span><span class="sxs-lookup"><span data-stu-id="414bf-117">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="414bf-118">Artikel zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="414bf-118">How-to Topics</span></span>](treeview-how-to-topics.md)
