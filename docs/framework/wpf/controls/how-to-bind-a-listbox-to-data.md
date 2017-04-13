---
title: "Gewusst wie: Binden eines Listenfelds an Daten | Microsoft Docs"
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
  - "Binden von Daten, In ListBox-Steuerelement"
  - "Datenbindung, ListBox-Steuerelement"
  - "ListBox-Steuerelemente, Binden von Daten an"
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Binden eines Listenfelds an Daten
Ein Anwendungsentwickler kann <xref:System.Windows.Controls.ListBox>\-Steuerelemente erstellen, ohne den Inhalt von jedem <xref:System.Windows.Controls.ListBoxItem> getrennt anzugeben.  Sie können Datenbindung verwenden, um Daten an die einzelnen Elemente zu binden.  
  
 Das folgende Beispiel veranschaulicht die Erstellung eines <xref:System.Windows.Controls.ListBox>\-Elements, das die <xref:System.Windows.Controls.ListBoxItem>\-Elemente durch Datenbindung an eine Datenquelle mit dem Namen *Colors* auffüllt.  In diesem Fall ist es nicht erforderlich, mit <xref:System.Windows.Controls.ListBoxItem>\-Tags den Inhalt der einzelnen Elemente anzugeben.  
  
## Beispiel  
 [!code-xml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## Siehe auch  
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.Controls.ListBoxItem>   
 [Steuerelemente](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)