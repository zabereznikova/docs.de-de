---
title: "Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a465ae44d3b8a4c43e5e34eaeedcd739d328bff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="6ec99-102">Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element</span><span class="sxs-lookup"><span data-stu-id="6ec99-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="6ec99-103">Standardmäßig wird der Inhalt jeder Spalte in einer <xref:System.Windows.Controls.ListViewItem> linksbündig ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="6ec99-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="6ec99-104">Sie können die Ausrichtung der einzelnen Spalten ändern, durch die Bereitstellung einer <xref:System.Windows.DataTemplate> verwendet wird und die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> -Eigenschaft des Elements innerhalb der <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="6ec99-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="6ec99-105">In diesem Thema wird gezeigt, wie eine <xref:System.Windows.Controls.ListView> richtet dessen Inhalt standardmäßig und so ändern Sie die Ausrichtung einer Spalte in einer <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="6ec99-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ec99-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ec99-106">Example</span></span>  
 <span data-ttu-id="6ec99-107">Im folgenden Beispiel werden die Daten in der `Title` und `ISBN` Spalten wird linksbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="6ec99-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="6ec99-108">So ändern Sie die Ausrichtung des der `ISBN` Spalte müssen Sie angeben, dass die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> -Eigenschaft jedes <xref:System.Windows.Controls.ListViewItem> ist <xref:System.Windows.HorizontalAlignment.Stretch>, sodass die Elemente in jedem <xref:System.Windows.Controls.ListViewItem> kann umfassen bzw. die gesamte Breite der einzelnen Spalten einnehmen.</span><span class="sxs-lookup"><span data-stu-id="6ec99-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="6ec99-109">Da die <xref:System.Windows.Controls.ListView> gebunden ist mit einer Datenquelle müssen Sie einen Stil zu erstellen, der festlegt der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ec99-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="6ec99-110">Als Nächstes müssen Sie verwenden eine <xref:System.Windows.DataTemplate> zum Anzeigen des Inhalts statt der <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6ec99-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="6ec99-111">Zum Anzeigen der `ISBN` jeder Vorlage der <xref:System.Windows.DataTemplate> darf nur eine <xref:System.Windows.Controls.TextBlock> mit dem seine <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> -Eigenschaftensatz auf <xref:System.Windows.HorizontalAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="6ec99-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="6ec99-112">Das folgende Beispiel definiert das Format und <xref:System.Windows.DataTemplate> erforderlich, erstellen die `ISBN` Spalte rechts ausgerichtet und Änderungen der <xref:System.Windows.Controls.GridViewColumn> zu verweisen die <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="6ec99-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="6ec99-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ec99-113">See Also</span></span>  
 [<span data-ttu-id="6ec99-114">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="6ec99-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="6ec99-115">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="6ec99-115">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="6ec99-116">Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen</span><span class="sxs-lookup"><span data-stu-id="6ec99-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="6ec99-117">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="6ec99-117">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
