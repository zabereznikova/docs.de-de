---
title: 'Gewusst wie: Anzeigen von Daten durch Verwenden von GridViewRowPresenter'
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: f68bc3a4ffff268138721a6750a0eb50c825377e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550789"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="9d475-102">Gewusst wie: Anzeigen von Daten durch Verwenden von GridViewRowPresenter</span><span class="sxs-lookup"><span data-stu-id="9d475-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="9d475-103">Dieses Beispiel zeigt, wie die <xref:System.Windows.Controls.GridViewRowPresenter> und <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Objekte, Daten in Spalten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9d475-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d475-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d475-104">Example</span></span>  
 <span data-ttu-id="9d475-105">Im folgende Beispiel wird gezeigt, wie an eine <xref:System.Windows.Controls.GridViewColumnCollection> , die anzeigt der <xref:System.DateTime.DayOfWeek%2A> und <xref:System.DateTime.Year%2A> des eine <xref:System.DateTime> -Objekt unter Verwendung der <xref:System.Windows.Controls.GridViewRowPresenter> und <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Objekte.</span><span class="sxs-lookup"><span data-stu-id="9d475-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="9d475-106">Im Beispiel definiert auch eine <xref:System.Windows.Style> für die <xref:System.Windows.Controls.GridViewColumn.Header%2A> von einem <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="9d475-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="9d475-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d475-107">See Also</span></span>  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
 <xref:System.Windows.Controls.GridViewRowPresenter>  
 <xref:System.Windows.Controls.GridViewColumnCollection>  
 [<span data-ttu-id="9d475-108">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="9d475-108">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
