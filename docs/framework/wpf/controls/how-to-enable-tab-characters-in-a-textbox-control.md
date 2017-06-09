---
title: "Gewusst wie: Aktivieren von Tabstoppzeichen in einem TextBox-Steuerelement | Microsoft Docs"
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
  - "Tabulatorzeichen, Aktivieren"
  - "TextBox-Steuerelement, Aktivieren von Tabulatorzeichen"
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Aktivieren von Tabstoppzeichen in einem TextBox-Steuerelement
In diesem Beispiel wird veranschaulicht, wie die Übernahme von Tabstoppzeichen als normale Eingabe in einem <xref:System.Windows.Controls.TextBox>\-Steuerelement aktiviert wird.  
  
## Beispiel  
 Um die Übernahme von Tabstoppzeichen als Eingabe in einem <xref:System.Windows.Controls.TextBox>\-Steuerelement zu aktivieren, legen Sie das <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A>\-Attribut auf **true** fest.  
  
 [!code-xml[TextBox_EnablingTab#_AcceptsTab](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)