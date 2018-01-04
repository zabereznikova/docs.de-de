---
title: "Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a465ae44d3b8a4c43e5e34eaeedcd739d328bff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Gewusst wie: Ändern der horizontalen Ausrichtung einer Spalte in einem ListView-Element
Standardmäßig wird der Inhalt jeder Spalte in einer <xref:System.Windows.Controls.ListViewItem> linksbündig ausgerichtet ist. Sie können die Ausrichtung der einzelnen Spalten ändern, durch die Bereitstellung einer <xref:System.Windows.DataTemplate> verwendet wird und die <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> -Eigenschaft des Elements innerhalb der <xref:System.Windows.DataTemplate>. In diesem Thema wird gezeigt, wie eine <xref:System.Windows.Controls.ListView> richtet dessen Inhalt standardmäßig und so ändern Sie die Ausrichtung einer Spalte in einer <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Daten in der `Title` und `ISBN` Spalten wird linksbündig ausgerichtet.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 So ändern Sie die Ausrichtung des der `ISBN` Spalte müssen Sie angeben, dass die <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> -Eigenschaft jedes <xref:System.Windows.Controls.ListViewItem> ist <xref:System.Windows.HorizontalAlignment.Stretch>, sodass die Elemente in jedem <xref:System.Windows.Controls.ListViewItem> kann umfassen bzw. die gesamte Breite der einzelnen Spalten einnehmen. Da die <xref:System.Windows.Controls.ListView> gebunden ist mit einer Datenquelle müssen Sie einen Stil zu erstellen, der festlegt der <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. Als Nächstes müssen Sie verwenden eine <xref:System.Windows.DataTemplate> zum Anzeigen des Inhalts statt der <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft. Zum Anzeigen der `ISBN` jeder Vorlage der <xref:System.Windows.DataTemplate> darf nur eine <xref:System.Windows.Controls.TextBlock> mit dem seine <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> -Eigenschaftensatz auf <xref:System.Windows.HorizontalAlignment.Right>.  
  
 Das folgende Beispiel definiert das Format und <xref:System.Windows.DataTemplate> erforderlich, erstellen die `ISBN` Spalte rechts ausgerichtet und Änderungen der <xref:System.Windows.Controls.GridViewColumn> zu verweisen die <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
