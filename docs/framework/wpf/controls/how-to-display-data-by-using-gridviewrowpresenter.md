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
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>Vorgehensweise: Anzeigen von Daten mithilfe von GridViewRowPresenter
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.Controls.GridViewRowPresenter> und <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Objekte zum Anzeigen von Daten in Spalten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie eine <xref:System.Windows.Controls.GridViewColumnCollection> , die anzeigt der <xref:System.DateTime.DayOfWeek%2A> und <xref:System.DateTime.Year%2A> von eine <xref:System.DateTime> Objekt mit <xref:System.Windows.Controls.GridViewRowPresenter> und <xref:System.Windows.Controls.GridViewHeaderRowPresenter> Objekte. Im Beispiel definiert auch eine <xref:System.Windows.Style> für die <xref:System.Windows.Controls.GridViewColumn.Header%2A> von einem <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [Übersicht über GridView](gridview-overview.md)
