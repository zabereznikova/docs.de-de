---
title: "Gewusst wie: Erstellen eines Rahmens um ein Windows Forms-Steuerelement mithilfe von Abst&#228;nden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Margin-Eigenschaft"
  - "Steuerelemente [Windows Forms], Gliedern"
  - "Steuerelemente [Windows Forms], Padding-Eigenschaft"
  - "Margin-Eigenschaft [Windows Forms]"
  - "Ränder"
  - "Ränder, Windows Forms"
  - "Padding-Eigenschaft [Windows Forms]"
  - "Abstand, Windows Forms"
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Erstellen eines Rahmens um ein Windows Forms-Steuerelement mithilfe von Abst&#228;nden
Im folgenden Codebeispiel wird veranschaulicht, wie ein Rahmen oder eine Kontur um ein <xref:System.Windows.Forms.RichTextBox>\-Steuerelement erstellt wird.  In dem Beispiel wird der Wert der <xref:System.Windows.Forms.Padding>\-Eigenschaft eines <xref:System.Windows.Forms.Panel>\-Steuerelements auf 5 und die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft eines untergeordneten <xref:System.Windows.Forms.RichTextBox>\-Steuerelements auf <xref:System.Windows.Forms.DockStyle> festgelegt.  Die <xref:System.Windows.Forms.Control.BackColor%2A> des <xref:System.Windows.Forms.Panel>\-Steuerelements wird auf <xref:System.Drawing.Color.Blue%2A> festgelegt, sodass ein blauer Rahmen um das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement erstellt wird.  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## Siehe auch  
 <xref:System.Windows.Forms.Padding>   
 [Rand und Abstand in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)