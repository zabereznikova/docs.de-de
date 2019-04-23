---
title: 'Vorgehensweise: Anzeigen von ListView-Inhalten mithilfe eines GridView-Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9b467c95d541c326a41d1ed4bd9eb5c87e25bd5c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112787"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="aaf35-102">Vorgehensweise: Anzeigen von ListView-Inhalten mithilfe eines GridView-Objekts</span><span class="sxs-lookup"><span data-stu-id="aaf35-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="aaf35-103">Dieses Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.GridView> Ansichtsmodus für eine <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="aaf35-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaf35-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aaf35-104">Example</span></span>  
 <span data-ttu-id="aaf35-105">Sie können den Anzeigemodus der definieren eine <xref:System.Windows.Controls.GridView> durch Angabe <xref:System.Windows.Controls.GridViewColumn> Objekte.</span><span class="sxs-lookup"><span data-stu-id="aaf35-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="aaf35-106">Das folgende Beispiel zeigt, wie Sie definieren <xref:System.Windows.Controls.GridViewColumn> Objekte, die an den Inhalt der Daten zu binden, die für angegeben wird die <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="aaf35-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="aaf35-107">Dies <xref:System.Windows.Controls.GridView> Beispiel gibt drei <xref:System.Windows.Controls.GridViewColumn> Objekte, die zugeordnet, der `FirstName`, `LastName`, und `EmployeeNumber` Felder der `EmployeeInfoDataSource` , festgelegt ist, als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> von der <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="aaf35-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="aaf35-108">Die folgende Abbildung zeigt, wie in diesem Beispiel wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aaf35-108">The following illustration shows how this example appears.</span></span>  
  
 ![Screenshot mit einer ListView mit GridView-Ausgabe.](./media/gridview-overview/listview-gridview-output.jpg)  
  
## <a name="see-also"></a><span data-ttu-id="aaf35-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaf35-110">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="aaf35-111">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="aaf35-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="aaf35-112">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="aaf35-112">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="aaf35-113">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="aaf35-113">How-to Topics</span></span>](listview-how-to-topics.md)
