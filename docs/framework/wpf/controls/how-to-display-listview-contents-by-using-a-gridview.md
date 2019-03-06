---
title: 'Vorgehensweise: Anzeigen von ListView-Inhalten mit GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 9a4bcc8b613637521ee91a11b0bdac8f77f90a03
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354400"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="904c2-102">Vorgehensweise: Anzeigen von ListView-Inhalten mit GridView</span><span class="sxs-lookup"><span data-stu-id="904c2-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="904c2-103">Dieses Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.GridView> Ansichtsmodus für eine <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="904c2-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="904c2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="904c2-104">Example</span></span>  
 <span data-ttu-id="904c2-105">Sie können den Anzeigemodus der definieren eine <xref:System.Windows.Controls.GridView> durch Angabe <xref:System.Windows.Controls.GridViewColumn> Objekte.</span><span class="sxs-lookup"><span data-stu-id="904c2-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="904c2-106">Das folgende Beispiel zeigt, wie Sie definieren <xref:System.Windows.Controls.GridViewColumn> Objekte, die an den Inhalt der Daten zu binden, die für angegeben wird die <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="904c2-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="904c2-107">Dies <xref:System.Windows.Controls.GridView> Beispiel gibt drei <xref:System.Windows.Controls.GridViewColumn> Objekte, die zugeordnet, der `FirstName`, `LastName`, und `EmployeeNumber` Felder der `EmployeeInfoDataSource` , festgelegt ist, als die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> von der <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="904c2-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="904c2-108">Die folgende Abbildung zeigt, wie in diesem Beispiel wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="904c2-108">The following illustration shows how this example appears.</span></span>  
  
 <span data-ttu-id="904c2-109">![ListView with GridView output](./media/listviewgridview.JPG "ListViewGridView")</span><span class="sxs-lookup"><span data-stu-id="904c2-109">![ListView with GridView output](./media/listviewgridview.JPG "ListViewGridView")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="904c2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="904c2-110">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="904c2-111">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="904c2-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="904c2-112">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="904c2-112">GridView Overview</span></span>](gridview-overview.md)
- [<span data-ttu-id="904c2-113">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="904c2-113">How-to Topics</span></span>](listview-how-to-topics.md)
