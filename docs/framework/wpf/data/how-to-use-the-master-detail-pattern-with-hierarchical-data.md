---
title: "Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten | Microsoft Docs"
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
  - "Datenbindung, Master/Detail-Datenparadigma"
  - "Master/Detail-Datenparadigma"
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen Daten
In diesem Beispiel wird gezeigt, wie das Master\/Detail\-Szenario implementiert wird.  
  
## Beispiel  
 In diesem Beispiel steht `LeagueList` für eine Auflistung von `Leagues`.  Jede `League` verfügt über einen `Name` und eine Auflistung von `Divisions`, und jede `Division` verfügt über einen Namen und eine Auflistung von `Teams`.  Jedes `Team` besitzt einen Teamnamen.  
  
 [!code-xml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 Im Folgenden finden Sie eine Bildschirmaufnahme des Beispiels.  Das `Divisions`\-<xref:System.Windows.Controls.ListBox> verfolgt automatisch die Auswahlmöglichkeiten im `Leagues`\-<xref:System.Windows.Controls.ListBox> und zeigt die entsprechenden Daten an.  Das `Teams`\-<xref:System.Windows.Controls.ListBox> verfolgt die Auswahlmöglichkeiten in den anderen zwei <xref:System.Windows.Controls.ListBox>\-Steuerelementen.  
  
 ![Master&#47;Detail&#45;Beispiel](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 Zwei Punkte sind in diesem Beispiel zu beachten:  
  
1.  Die drei <xref:System.Windows.Controls.ListBox>\-Steuerelemente werden an dieselbe Quelle gebunden.  Sie legen die <xref:System.Windows.Data.Binding.Path%2A>\-Eigenschaft der Bindung fest, um anzugeben, welche Datenebene das <xref:System.Windows.Controls.ListBox> anzeigen soll.  
  
2.  Sie müssen die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>\-Eigenschaft für die <xref:System.Windows.Controls.ListBox>\-Steuerelemente, deren Auswahl Sie verfolgen, auf `true` festlegen.  Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer als <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> festgelegt wird.  Wenn hingegen das <xref:System.Windows.Controls.ListBox> die Daten von <xref:System.Windows.Data.CollectionViewSource> abruft, werden Auswahl und Währung automatisch synchronisiert.  
  
 Die Vorgehensweise unterscheidet sich etwas, wenn Sie [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten verwenden.  Ein Beispiel finden Sie unter [Verwenden des Master\-\/Detailmusters mit hierarchischen XML\-Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).  
  
## Siehe auch  
 <xref:System.Windows.HierarchicalDataTemplate>   
 [Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)