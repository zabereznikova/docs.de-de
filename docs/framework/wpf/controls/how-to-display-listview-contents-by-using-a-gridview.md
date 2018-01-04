---
title: 'Gewusst wie: Anzeigen von ListView-Inhalten mit GridView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee2885868c07b00f16290b6414e7f7bdd64fd68c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="80a09-102">Gewusst wie: Anzeigen von ListView-Inhalten mit GridView</span><span class="sxs-lookup"><span data-stu-id="80a09-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="80a09-103">In diesem Beispiel wird gezeigt, wie zum Definieren einer <xref:System.Windows.Controls.GridView> Ansichtsmodus für eine <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="80a09-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80a09-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80a09-104">Example</span></span>  
 <span data-ttu-id="80a09-105">Sie können den Anzeigemodus der definieren eine <xref:System.Windows.Controls.GridView> durch Angabe <xref:System.Windows.Controls.GridViewColumn> Objekte.</span><span class="sxs-lookup"><span data-stu-id="80a09-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="80a09-106">Das folgende Beispiel zeigt, wie definiert <xref:System.Windows.Controls.GridViewColumn> Objekte, die auf den Dateninhalt zu binden, der für angegeben wird die <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="80a09-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="80a09-107">Dies <xref:System.Windows.Controls.GridView> Beispiel gibt drei <xref:System.Windows.Controls.GridViewColumn> Objekte, die zum Zuordnen der `FirstName`, `LastName`, und `EmployeeNumber` Felder des der `EmployeeInfoDataSource` , als festgelegt ist die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> von der <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="80a09-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="80a09-108">Die folgende Abbildung zeigt, wie in diesem Beispiel wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80a09-108">The following illustration shows how this example appears.</span></span>  
  
 <span data-ttu-id="80a09-109">![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span><span class="sxs-lookup"><span data-stu-id="80a09-109">![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a09-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80a09-110">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="80a09-111">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="80a09-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="80a09-112">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="80a09-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="80a09-113">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="80a09-113">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
