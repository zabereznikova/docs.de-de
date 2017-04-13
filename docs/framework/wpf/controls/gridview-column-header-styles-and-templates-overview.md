---
title: "&#220;bersicht &#252;ber GridView-Spaltenheaderstile und -Spaltenheadervorlagen | Microsoft Docs"
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
  - "Spaltenheader, Anpassen"
  - "Steuerelemente, ListView"
  - "GridView-Ansichtsmodus, Anpassen von Spaltenheadern"
  - "Kopfzeilen, Anpassen"
  - "ListView-Steuerelemente [WPF], GridView-Spaltenheaderstile"
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;bersicht &#252;ber GridView-Spaltenheaderstile und -Spaltenheadervorlagen
In dieser Übersicht wird die Rangfolge für Eigenschaften erläutert, mit denen Sie einen Spaltenheader im <xref:System.Windows.Controls.GridView>\-Ansichtsmodus eines <xref:System.Windows.Controls.ListView>\-Steuerelements anpassen.  
  
## Anpassen eines Spaltenheaders in einem GridView  
 Die Eigenschaften, die den Inhalt, das Layout und den Stil eines Spaltenheaders in einem <xref:System.Windows.Controls.GridView> definieren, befinden sich in vielen verwandten Klassen.  Einige dieser Eigenschaften haben eine ähnliche oder sogar identische Funktion.  
  
 In der folgenden Tabelle sind Gruppen von Eigenschaften, die dieselbe Funktion erfüllen, aufgeführt.  Mithilfe dieser Eigenschaften können Sie die Spaltenheader in einem <xref:System.Windows.Controls.GridView> anpassen.  Die Rangfolge bei verwandten Eigenschaften verläuft von rechts nach links, wobei die Eigenschaft in der Spalte ganz rechts die höchste Priorität besitzt.  Wenn <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> beispielsweise über das <xref:System.Windows.Controls.GridViewColumnHeader>\-Objekt und <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> über das zugehörige <xref:System.Windows.Controls.GridViewColumn>\-Objekt festgelegt werden, hat <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Vorrang.  In diesem Szenario hat <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> keine Auswirkungen.  
  
 **Verwandte Eigenschaften für Spaltenheader in einem GridView**  
  
|||||  
|-|-|-|-|  
|**Klassen**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**Kontextmenüeigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|Nicht zutreffend|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**ToolTip**<br /><br /> **Eigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|Nicht zutreffend|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**Headervorlage**<br /><br /> **Eigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>\/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**Formateigenschaften**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>Wenn Sie bei **Headervorlageneigenschaften** sowohl die Vorlagen\- als auch die Vorlagenauswahleigenschaft festlegen, hat die Vorlageneigenschaft Vorrang.  Wenn Sie zum Beispiel sowohl die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>\-Eigenschaft als auch die <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>\-Eigenschaft festlegen, hat die <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>\-Eigenschaft Vorrang.  
  
## Siehe auch  
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)