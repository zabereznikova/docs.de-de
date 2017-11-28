---
title: "Gewusst wie: Erstellen von ListViewItems mit einem Kontrollkästchen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6ebb3671dcc65d690fde5d4796c9034553eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="260ef-102">Gewusst wie: Erstellen von ListViewItems mit einem Kontrollkästchen</span><span class="sxs-lookup"><span data-stu-id="260ef-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="260ef-103">In diesem Beispiel wird gezeigt, wie eine Spalte des anzuzeigenden <xref:System.Windows.Controls.CheckBox> Steuerelemente in eine <xref:System.Windows.Controls.ListView> -Steuerelements, verwendet eine <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="260ef-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="260ef-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="260ef-104">Example</span></span>  
 <span data-ttu-id="260ef-105">Um eine Spalte zu erstellen, enthält <xref:System.Windows.Controls.CheckBox> Steuerelemente in eine <xref:System.Windows.Controls.ListView>, erstellen eine <xref:System.Windows.DataTemplate> , enthält eine <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="260ef-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="260ef-106">Legen Sie dann die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> von einer <xref:System.Windows.Controls.GridViewColumn> auf die <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="260ef-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="260ef-107">Das folgende Beispiel zeigt eine <xref:System.Windows.DataTemplate> , enthält eine <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="260ef-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="260ef-108">Im Beispiel bindet der <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> Eigenschaft von der <xref:System.Windows.Controls.CheckBox> auf die <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> Eigenschaftswert, der die <xref:System.Windows.Controls.ListViewItem> , die Sie enthält.</span><span class="sxs-lookup"><span data-stu-id="260ef-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="260ef-109">Aus diesem Grund, wenn die <xref:System.Windows.Controls.ListViewItem> , enthält die <xref:System.Windows.Controls.CheckBox> ausgewählt ist, die <xref:System.Windows.Controls.CheckBox> aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="260ef-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="260ef-110">Im folgende Beispiel wird gezeigt, wie zum Erstellen einer Spalte des <xref:System.Windows.Controls.CheckBox> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="260ef-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="260ef-111">Zu der Spalte, die im Beispiel wird die <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> Eigenschaft von der <xref:System.Windows.Controls.GridViewColumn> auf der <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="260ef-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="260ef-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="260ef-112">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="260ef-113">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="260ef-113">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="260ef-114">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="260ef-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="260ef-115">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="260ef-115">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
