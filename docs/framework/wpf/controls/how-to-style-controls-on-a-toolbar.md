---
title: "Gewusst wie: Formatieren von Steuerelementen auf einer Symbolleiste | Microsoft Docs"
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
  - "Anpassen von Steuerelementen in einer Symbolleiste"
  - "Formatieren von Steuerelementen in einer Symbolleiste"
  - "Symbolleisten"
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Gewusst wie: Formatieren von Steuerelementen auf einer Symbolleiste
Das <xref:System.Windows.Controls.ToolBar>\-Element definiert <xref:System.Windows.ResourceKey>\-Objekte, um den Stil von Steuerelementen auf der <xref:System.Windows.Controls.ToolBar> anzugeben.  Um ein Steuerelement auf einer <xref:System.Windows.Controls.ToolBar> zu formatieren, legen Sie das `x:key`\-Attribut des Stils auf einen in <xref:System.Windows.Controls.ToolBar> definierten <xref:System.Windows.ResourceKey> fest.  
  
 Das <xref:System.Windows.Controls.ToolBar>\-Element definiert die folgenden <xref:System.Windows.ResourceKey>\-Objekte:  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## Beispiel  
 Im folgenden Beispiel werden Stile für die Steuerelemente auf einer <xref:System.Windows.Controls.ToolBar> definiert.  
  
 [!code-xml[ToolBar_snip#ToolBarAllStyles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xml[ToolBar_snip#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)