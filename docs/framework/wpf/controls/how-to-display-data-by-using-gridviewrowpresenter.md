---
title: 'Vorgehensweise: Anzeigen von Daten mithilfe von GridViewRowPresenter'
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: 0e471df3ab6fd10417fc58ece4cdb8ff1c457c95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149148"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a><span data-ttu-id="504ef-102">Vorgehensweise: Anzeigen von Daten mithilfe von GridViewRowPresenter</span><span class="sxs-lookup"><span data-stu-id="504ef-102">How to: Display Data by Using GridViewRowPresenter</span></span>
<span data-ttu-id="504ef-103">Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.GridViewRowPresenter> und <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Objekte zum Anzeigen von Daten in Spalten.</span><span class="sxs-lookup"><span data-stu-id="504ef-103">This example shows how to use the <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects to display data in columns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="504ef-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="504ef-104">Example</span></span>  
 <span data-ttu-id="504ef-105">Das folgende Beispiel zeigt, wie eine <xref:System.Windows.Controls.GridViewColumnCollection> , die anzeigt der <xref:System.DateTime.DayOfWeek%2A> und <xref:System.DateTime.Year%2A> von eine <xref:System.DateTime> Objekt mit <xref:System.Windows.Controls.GridViewRowPresenter> und <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Objekte.</span><span class="sxs-lookup"><span data-stu-id="504ef-105">The following example shows how to specify a <xref:System.Windows.Controls.GridViewColumnCollection> that displays the <xref:System.DateTime.DayOfWeek%2A> and <xref:System.DateTime.Year%2A> of a <xref:System.DateTime> object by using <xref:System.Windows.Controls.GridViewRowPresenter> and <xref:System.Windows.Controls.GridViewHeaderRowPresenter> objects.</span></span> <span data-ttu-id="504ef-106">Im Beispiel definiert auch eine <xref:System.Windows.Style> für die <xref:System.Windows.Controls.GridViewColumn.Header%2A> von einem <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="504ef-106">The example also defines a <xref:System.Windows.Style> for the <xref:System.Windows.Controls.GridViewColumn.Header%2A> of a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a><span data-ttu-id="504ef-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="504ef-107">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [<span data-ttu-id="504ef-108">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="504ef-108">GridView Overview</span></span>](gridview-overview.md)
