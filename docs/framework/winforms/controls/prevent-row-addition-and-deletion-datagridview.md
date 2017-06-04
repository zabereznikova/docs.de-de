---
title: "Gewusst wie: Verhindern, das Zeilen im DataGridView-Steuerelement in Windows Forms hinzugef&#252;gt und gel&#246;scht werden | Microsoft Docs"
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
  - "Dateneingabe, Deaktivieren in Datenblättern"
  - "Datenblätter, Deaktivieren der Dateneingabe"
  - "DataGridView-Steuerelement [Windows Forms], Deaktivieren der Dateneingabe"
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Verhindern, das Zeilen im DataGridView-Steuerelement in Windows Forms hinzugef&#252;gt und gel&#246;scht werden
Gelegentlich möchten Sie Benutzer daran hindern, neue Zeilen von Daten einzugeben oder vorhandene Zeilen in Ihrem <xref:System.Windows.Forms.DataGridView>\-Steuerelement zu löschen.  Die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>\-Eigenschaft gibt an, ob die Zeile für neue Datensätze am unteren Rand des Steuerelements vorhanden ist, während die <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A>\-Eigenschaft angibt, ob Zeilen entfernt werden können.  Das folgende Codebeispiel verwendet diese Eigenschaften und legt außerdem die <xref:System.Windows.Forms.DataGridView.ReadOnly%2A>\-Eigenschaft fest, damit das Steuerelement vollständig schreibgeschützt ist.  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch [Gewusst wie: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName> und <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=fullName>   
 [Grundlegende Spalten\-, Zeilen\- und Zellfeatures im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)