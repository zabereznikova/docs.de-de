---
title: 'Vorgehensweise: Verwendung von SelectedValue, SelectedValuePath und SelectedItem'
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
ms.openlocfilehash: d9f7a8f04f53b7d38a49dfef2c947dfa1c2d263d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699135"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="d7a5f-102">Vorgehensweise: Verwendung von SelectedValue, SelectedValuePath und SelectedItem</span><span class="sxs-lookup"><span data-stu-id="d7a5f-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="d7a5f-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.TreeView.SelectedValue%2A> und <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaften, die einen Wert für die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> von einem <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7a5f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7a5f-104">Example</span></span>  
 <span data-ttu-id="d7a5f-105">Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> Eigenschaft bietet eine Möglichkeit zum Angeben einer <xref:System.Windows.Controls.TreeView.SelectedValue%2A> für die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in eine <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="d7a5f-106">Die <xref:System.Windows.Controls.TreeView.SelectedItem%2A> stellt ein Objekt in der <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung und die <xref:System.Windows.Controls.TreeView> zeigt den Wert einer einzelnen Eigenschaft des ausgewählten Elements.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="d7a5f-107">Die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> -Eigenschaft gibt den Pfad der Eigenschaft, die verwendet wird, um zu bestimmen, den Wert des der <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="d7a5f-108">In die Beispielen in diesem Thema veranschaulichen dieses Konzept.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="d7a5f-109">Das folgende Beispiel zeigt eine <xref:System.Windows.Data.XmlDataProvider> , die Mitarbeiterinformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="d7a5f-110">Das folgende Beispiel definiert eine <xref:System.Windows.HierarchicalDataTemplate> angezeigt, die die `EmployeeName` und `EmployeeWorkDay` von der `Employee`.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="d7a5f-111">Beachten Sie, dass die <xref:System.Windows.HierarchicalDataTemplate> gibt keinen der `EmployeeNumber` als Teil der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="d7a5f-112">Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.TreeView> , verwendet die zuvor definierte <xref:System.Windows.HierarchicalDataTemplate> und legt sie fest, die die <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Eigenschaft, um die `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="d7a5f-113">Bei der Auswahl einer `EmployeeName` in die <xref:System.Windows.Controls.TreeView>, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> -Eigenschaft gibt die `EmployeeInfo` Datenelement, das dem ausgewählten `EmployeeName`.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="d7a5f-114">Allerdings da die <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> dieses <xref:System.Windows.Controls.TreeView> ist eingestellt auf `EmployeeNumber`, <xref:System.Windows.Controls.TreeView.SelectedValue%2A> ist eingestellt auf der `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="d7a5f-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="d7a5f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7a5f-115">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="d7a5f-116">Übersicht über TreeView</span><span class="sxs-lookup"><span data-stu-id="d7a5f-116">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="d7a5f-117">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="d7a5f-117">How-to Topics</span></span>](treeview-how-to-topics.md)
