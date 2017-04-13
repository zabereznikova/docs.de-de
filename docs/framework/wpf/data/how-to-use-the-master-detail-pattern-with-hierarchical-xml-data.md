---
title: "Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten | Microsoft Docs"
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
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten
In diesem Beispiel wird gezeigt, wie das Master\/Detail\-Szenario mit [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Daten implementiert wird.  
  
## Beispiel  
 Dieses Beispiel ist die [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Datenversion des unter [Verwenden des Master\-\/Detailmusters mit hierarchischen Daten](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md) erläuterten Beispiels.  In diesem Beispiel stammen die Daten aus der Datei `League.xml`.  Beachten Sie, wie im dritten <xref:System.Windows.Controls.ListBox>\-Steuerelement Änderungen der Auswahl im zweiten <xref:System.Windows.Controls.ListBox>\-Steuerelement durch Bindung an die <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>\-Eigenschaft verfolgt werden.  
  
 [!code-xml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## Siehe auch  
 <xref:System.Windows.HierarchicalDataTemplate>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)