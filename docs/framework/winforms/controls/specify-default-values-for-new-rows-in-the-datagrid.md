---
title: "Gewusst wie: Angeben von Standardwerten f&#252;r neue Zeilen im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Standardwerte für neue Zeilen"
  - "DataGridView-Steuerelement [Windows Forms], Dateneingabe"
  - "DataGridView-Steuerelement [Windows Forms], Standardwerte für neue Zeilen"
  - "Zeilen, Festlegen von Standardwerten"
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Angeben von Standardwerten f&#252;r neue Zeilen im DataGridView-Steuerelement in Windows Forms
Sie können die Dateneingabe erleichtern, indem die Anwendung Standardwerte für neu hinzugefügte Zeilen vorgibt.  Mit der <xref:System.Windows.Forms.DataGridView>\-Klasse können Sie Standardwerte mit dem <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>\-Ereignis einfügen.  Dieses Ereignis wird ausgelöst, wenn der Benutzer in die Zeile für neue Datensätze klickt.  Wenn der Code dieses Ereignis behandelt, können Sie gewünschte Zellen mit beliebigen Werten füllen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Standardwerte für neue Zeilen mithilfe des <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>\-Ereignisses angegeben werden.  
  
## Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen`dataGridView1` muss vorhanden sein.  
  
-   Eine `NewCustomerId`\-Funktion zum Generieren eindeutiger `CustomerID`\-Werte.  
  
-   Verweise auf die <xref:System?displayProperty=fullName>\-Assembly und die <xref:System.Windows.Forms?displayProperty=fullName>\-Assembly.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=fullName>   
 [Dateneingabe im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Verwenden der Zeile für neue Datensätze im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)