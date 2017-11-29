---
title: 'Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fdc478d62ca97f8f61c26fbbf1ee6c3ea8b4e189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="1c24b-102">Gewusst wie: Verwendung von SelectedValue, SelectedValuePath und SelectedItem</span><span class="sxs-lookup"><span data-stu-id="1c24b-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="1c24b-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Controls.TreeView.SelectedValue%2A> und <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaften zur Angabe eines Werts für die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> von einem <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="1c24b-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c24b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c24b-104">Example</span></span>  
 <span data-ttu-id="1c24b-105">Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft bietet eine Möglichkeit zum Angeben einer <xref:System.Windows.Controls.TreeView.SelectedValue%2A> für die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in einer <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="1c24b-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="1c24b-106">Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> stellt ein Objekt in der <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung und die <xref:System.Windows.Controls.TreeView> zeigt den Wert einer einzelnen Eigenschaft des ausgewählten Elements.</span><span class="sxs-lookup"><span data-stu-id="1c24b-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="1c24b-107">Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft gibt den Pfad zu der Eigenschaft, die verwendet wird, um den Wert der Festlegen der <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1c24b-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="1c24b-108">Die Beispiele in diesem Thema veranschaulichen dieses Konzept.</span><span class="sxs-lookup"><span data-stu-id="1c24b-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="1c24b-109">Das folgende Beispiel zeigt eine <xref:System.Windows.Data.XmlDataProvider> , die Mitarbeiterinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="1c24b-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="1c24b-110">Das folgende Beispiel definiert eine <xref:System.Windows.HierarchicalDataTemplate> , anzeigt der `EmployeeName` und `EmployeeWorkDay` von der `Employee`.</span><span class="sxs-lookup"><span data-stu-id="1c24b-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="1c24b-111">Beachten Sie, dass die <xref:System.Windows.HierarchicalDataTemplate> gibt keinen der `EmployeeNumber` als Teil der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="1c24b-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="1c24b-112">Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.TreeView> , verwendet die zuvor definierte <xref:System.Windows.HierarchicalDataTemplate> und legt sie fest, die die <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft, um die `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="1c24b-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="1c24b-113">Bei Auswahl einer `EmployeeName` in der <xref:System.Windows.Controls.TreeView>, die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> -Eigenschaft gibt die `EmployeeInfo` Datenelement, das dem ausgewählten `EmployeeName`.</span><span class="sxs-lookup"><span data-stu-id="1c24b-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="1c24b-114">Jedoch, da die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> dieses <xref:System.Windows.Controls.TreeView> auf festgelegt ist `EmployeeNumber`, die <xref:System.Windows.Controls.TreeView.SelectedValue%2A> auf festgelegt ist die `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="1c24b-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="1c24b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c24b-115">See Also</span></span>  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [<span data-ttu-id="1c24b-116">Übersicht über TreeView</span><span class="sxs-lookup"><span data-stu-id="1c24b-116">TreeView Overview</span></span>](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [<span data-ttu-id="1c24b-117">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="1c24b-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
