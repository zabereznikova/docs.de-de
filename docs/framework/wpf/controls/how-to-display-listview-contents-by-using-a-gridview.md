---
title: "Gewusst wie: Anzeigen von ListView-Inhalten mit GridView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GridView, Anzeigen von ListView-Inhalt"
  - "ListView-Steuerelemente, Anzeigen von Inhalt mit GridView"
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Anzeigen von ListView-Inhalten mit GridView
Dieses Beispiel zeigt, wie ein <xref:System.Windows.Controls.GridView>\-Anzeigemodus für ein <xref:System.Windows.Controls.ListView>\-Steuerelement definiert wird.  
  
## Beispiel  
 Sie können den <xref:System.Windows.Controls.GridView>\-Anzeigemodus definieren, indem Sie <xref:System.Windows.Controls.GridViewColumn>\-Objekte angeben.  Das folgende Beispiel zeigt, wie Sie <xref:System.Windows.Controls.GridViewColumn>\-Objekte definieren, die an den für das <xref:System.Windows.Controls.ListView>\-Steuerelement angegebenen Dateninhalt gebunden sind.  In diesem <xref:System.Windows.Controls.GridView>\-Beispiel werden drei <xref:System.Windows.Controls.GridViewColumn>\-Objekte angegeben, die den Feldern `FirstName`, `LastName` und `EmployeeNumber` der `EmployeeInfoDataSource` zugeordnet sind, die als <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für das <xref:System.Windows.Controls.ListView>\-Steuerelement festgelegt ist.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 In der folgenden Abbildung ist dieses Beispiel dargestellt.  
  
 ![ListView mit GridView&#45;Ausgabe](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
## Siehe auch  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)