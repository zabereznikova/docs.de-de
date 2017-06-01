---
title: "Gewusst wie: Hinzuf&#252;gen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Spalten [Windows Forms], Nicht gebundene Daten"
  - "Datenblätter, Hinzufügen von nicht gebundenen Spalten"
  - "DataGridView-Steuerelement [Windows Forms], Nicht gebundene Daten"
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Hinzuf&#252;gen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms
Die Daten, die Sie im <xref:System.Windows.Forms.DataGridView>\-Steuerelement anzeigen, stammen normalerweise aus einer Datenquelle einer bestimmten Art, aber möglicherweise möchten Sie eine Spalte mit Daten anzeigen, die nicht aus der Datenquelle stammen.  Diese Art von Spalte wird als ungebundene Spalte bezeichnet.  Ungebundene Spalten können viele Formen annehmen.  Häufig werden sie verwendet, um Zugriff auf die Details einer Datenzeile bereitzustellen.  
  
 Im folgenden Codebeispiel wird das Erstellen einer nicht gebundenen Spalte von **Details**\-Schaltflächen für die Anzeige einer untergeordneten Tabelle veranschaulicht, die zu einer bestimmten Zeile in einer übergeordneten Tabelle gehört, wenn Sie ein Master\-\/Detail\-Szenario implementieren.  Um auf Klicks auf Schaltflächen zu reagieren, implementieren Sie einen <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName>\-Ereignishandler, der ein Formular mit der untergeordneten Tabelle anzeigt.  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch [Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/dyyesckz\(v=vs.110\)).  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Datenanzeigemodi im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)