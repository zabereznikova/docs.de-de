---
title: "Gewusst wie: Anzeigen von Daten durch Verwenden von GridViewRowPresenter | Microsoft Docs"
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
  - "Anzeigen von Daten mit GridViewRowPresenter"
  - "GridViewRowPresenter"
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Anzeigen von Daten durch Verwenden von GridViewRowPresenter
Dieses Beispiel zeigt, wie das <xref:System.Windows.Controls.GridViewRowPresenter>\-Objekt und das <xref:System.Windows.Controls.GridViewHeaderRowPresenter>\-Objekt verwendet werden, um Daten in Spalten anzuzeigen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine <xref:System.Windows.Controls.GridViewColumnCollection> angegeben wird, die <xref:System.DateTime.DayOfWeek%2A> und <xref:System.DateTime.Year%2A> eines <xref:System.DateTime>\-Objekts mithilfe der Objekte <xref:System.Windows.Controls.GridViewRowPresenter> und <xref:System.Windows.Controls.GridViewHeaderRowPresenter> anzeigt.  Im Beispiel wird ebenfalls ein <xref:System.Windows.Style> für den <xref:System.Windows.Controls.GridViewColumn.Header%2A> einer <xref:System.Windows.Controls.GridViewColumn> definiert.  
  
 [!code-xml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>   
 <xref:System.Windows.Controls.GridViewRowPresenter>   
 <xref:System.Windows.Controls.GridViewColumnCollection>   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)