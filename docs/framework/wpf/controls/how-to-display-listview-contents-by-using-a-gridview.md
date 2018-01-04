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
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a>Gewusst wie: Anzeigen von ListView-Inhalten mit GridView
In diesem Beispiel wird gezeigt, wie zum Definieren einer <xref:System.Windows.Controls.GridView> Ansichtsmodus für eine <xref:System.Windows.Controls.ListView> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Sie können den Anzeigemodus der definieren eine <xref:System.Windows.Controls.GridView> durch Angabe <xref:System.Windows.Controls.GridViewColumn> Objekte. Das folgende Beispiel zeigt, wie definiert <xref:System.Windows.Controls.GridViewColumn> Objekte, die auf den Dateninhalt zu binden, der für angegeben wird die <xref:System.Windows.Controls.ListView> Steuerelement. Dies <xref:System.Windows.Controls.GridView> Beispiel gibt drei <xref:System.Windows.Controls.GridViewColumn> Objekte, die zum Zuordnen der `FirstName`, `LastName`, und `EmployeeNumber` Felder des der `EmployeeInfoDataSource` , als festgelegt ist die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> von der <xref:System.Windows.Controls.ListView> Steuerelement.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 Die folgende Abbildung zeigt, wie in diesem Beispiel wird angezeigt.  
  
 ![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
