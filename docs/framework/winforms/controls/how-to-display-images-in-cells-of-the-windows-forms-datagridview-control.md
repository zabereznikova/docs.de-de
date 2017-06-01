---
title: "Gewusst wie: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms | Microsoft Docs"
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
  - "Zellen, Anzeigen von Bildern"
  - "Datenblätter, Anzeigen von Bildern in Zellen"
  - "Datenblätter, Anzeigen in Datenblättern"
  - "DataGridView-Steuerelement [Windows Forms], Anzeigen von Bildern"
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Anzeigen von Bildern in Zellen des DataGridView-Steuerelements in Windows Forms
Zu den Werten, die in einer Datenzeile angezeigt werden können, gehören Bilder und Grafiken.  Häufig handelt es sich hierbei um das Foto eines Mitarbeiters oder ein Firmenlogo.  
  
 Wenn Daten innerhalb des <xref:System.Windows.Forms.DataGridView>\-Steuerelements angezeigt werden, können mühelos Bilder integriert werden.  Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement behandelt jedes Bildformat, das von der <xref:System.Drawing.Image>\-Klasse unterstützt wird, sowie das von einigen Datenbanken verwendete OLE\-Bildformat.  
  
 Wenn die Datenquelle des <xref:System.Windows.Forms.DataGridView>\-Steuerelements über eine Spalte mit Bildern verfügt, werden diese automatisch durch das <xref:System.Windows.Forms.DataGridView>\-Steuerelement angezeigt.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein Symbol aus einer eingebetteten Ressource extrahiert und anschließend in ein Bitmap konvertiert wird, um es in jeder Zelle einer Bilderspalte anzuzeigen.  Ein weiteres Beispiel, bei dem Zellenwerte in Form von Text durch entsprechende Bilder ersetzt werden, finden Sie unter [Gewusst wie: Anpassen der Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen`dataGridView1` muss vorhanden sein.  
  
-   Eine eingebettete Symbolressource mit dem Namen `tree.ico`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> und <xref:System.Drawing?displayProperty=fullName>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [Grundlegende Spalten\-, Zeilen\- und Zellfeatures im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Gewusst wie: Anpassen der Datenformatierung im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)