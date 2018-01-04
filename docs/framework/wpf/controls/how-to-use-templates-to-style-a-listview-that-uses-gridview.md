---
title: 'Gewusst wie: Formatieren eines ListView-Steuerelements mit einem GridView mithilfe von Vorlagen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9abc19ca14cf512deff898f5f20d23870b8b7847
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="0c3ee-102">Gewusst wie: Formatieren eines ListView-Steuerelements mit einem GridView mithilfe von Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0c3ee-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="0c3ee-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.DataTemplate> und <xref:System.Windows.Style> Objekte an, die Darstellung des eine <xref:System.Windows.Controls.ListView> -Steuerelements, verwendet eine <xref:System.Windows.Controls.GridView> Ansichtsmodus.</span><span class="sxs-lookup"><span data-stu-id="0c3ee-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c3ee-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c3ee-104">Example</span></span>  
 <span data-ttu-id="0c3ee-105">Das folgende Beispiel zeigt <xref:System.Windows.Style> und <xref:System.Windows.DataTemplate> Objekte, die einen Spaltenheader für die Darstellung anpassen einer <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="0c3ee-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="0c3ee-106">Das folgende Beispiel zeigt, wie diese <xref:System.Windows.Style> und <xref:System.Windows.DataTemplate> Objekte Festlegen der <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> und <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> Eigenschaften einer <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="0c3ee-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="0c3ee-107">Die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> -Eigenschaft definiert den Inhalt der Spaltenzellen.</span><span class="sxs-lookup"><span data-stu-id="0c3ee-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="0c3ee-108">Die <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> und <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> sind nur zwei verschiedene Eigenschaften, die Sie, zum Anpassen der Darstellung eines Spaltenheaders für verwenden können eine <xref:System.Windows.Controls.GridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0c3ee-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="0c3ee-109">Weitere Informationen finden Sie unter [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0c3ee-109">For more information, see [GridView Column Header Styles and Templates Overview](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="0c3ee-110">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.DataTemplate> , die passt der Darstellung der Zellen in einer <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="0c3ee-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="0c3ee-111">Das folgende Beispiel zeigt die Verwendung dieses <xref:System.Windows.DataTemplate> zum Definieren des Inhalts von einem <xref:System.Windows.Controls.GridViewColumn> Zelle.</span><span class="sxs-lookup"><span data-stu-id="0c3ee-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="0c3ee-112">Diese Vorlage dient dazu, statt die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> -Eigenschaft, die in der vorherigen angezeigt wird <xref:System.Windows.Controls.GridViewColumn> Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0c3ee-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="0c3ee-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c3ee-113">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="0c3ee-114">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="0c3ee-114">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="0c3ee-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0c3ee-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="0c3ee-116">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="0c3ee-116">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
