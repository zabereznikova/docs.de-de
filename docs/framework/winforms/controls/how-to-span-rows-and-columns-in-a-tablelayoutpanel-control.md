---
title: "Gewusst wie: &#220;berspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zellen, Zusammenführen"
  - "Spalten [Windows Forms], Verbinden"
  - "Zusammenführen von Zellen"
  - "Zeilen [Windows Forms], Verbinden"
  - "TableLayoutPanel-Steuerelement [Windows Forms], Verbinden von Zeilen und Spalten"
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: &#220;berspannen von Zeilen und Spalten in einem TableLayoutPanel-Steuerelement
Steuerelemente in einem <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement können nebeneinander liegende Zeilen und Spalten überspannen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So überspannen Sie Spalten und Zeilen  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement aus der **Toolbox** auf das Formular.  
  
2.  Ziehen Sie ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** in die linke obere Zelle des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements.  
  
3.  Legen Sie für die **ColumnSpan**\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements den Wert 2 fest.  Beachten Sie, dass das <xref:System.Windows.Forms.Button>\-Steuerelement die erste und zweite Spalte überspannt.  
  
4.  Legen Sie die **RowSpan**\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements auf den Wert 2 fest.  Beachten Sie, dass das <xref:System.Windows.Forms.Button>\-Steuerelement die erste und zweite Zeile überspannt.  
  
5.  Legen Sie für die **ColumnSpan**\-Eigenschaft des <xref:System.Windows.Forms.Button>\-Steuerelements den Wert 1 fest.  Beachten Sie, dass das <xref:System.Windows.Forms.Button>\-Steuerelement in die erste Spalte verschoben wird und die erste und zweite Zeile überspannt.  
  
## Siehe auch  
 [TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)