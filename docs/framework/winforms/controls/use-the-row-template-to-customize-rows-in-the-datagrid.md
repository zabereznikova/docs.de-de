---
title: "Gewusst wie: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
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
  - "Datenblätter, Anpassen von Zeilen"
  - "DataGridView-Steuerelement [Windows Forms], Anpassen von Zeilen"
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement verwendet die Zeilenvorlage als Basis für alle Zeilen, die es dem Steuerelement entweder durch Datenbindung oder durch Aufrufen der <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=fullName>\-Methode ohne Angabe einer vorhandenen Zelle hinzufügt.  
  
 Die Zeilenvorlage ermöglicht Ihnen größere Kontrolle über das Aussehen und Verhalten von Zeilen als die <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>\-Eigenschaft.  Mit der Zeilenvorlage können Sie alle <xref:System.Windows.Forms.DataGridViewRow>\-Eigenschaften festlegen, einschließlich <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 Es gibt Situationen, in denen Sie die Zeilenvorlage verwenden müssen, um einen speziellen Effekt zu erreichen.  Beispielsweise können Informationen über die Zeilenhöhe in einem <xref:System.Windows.Forms.DataGridViewCellStyle> gespeichert sein, sodass Sie die von allen Zeilen verwendete Standardhöhe mithilfe einer Zeilenvorlage ändern müssen.  Die Zeilenvorlage ist zudem hilfreich, wenn Sie Ihre eigenen von <xref:System.Windows.Forms.DataGridViewRow> abgeleiteten Klassen erstellen und möchten, dass der benutzerdefinierte Typ verwendet wird, wenn neue Zeilen zum Steuerelement hinzugefügt werden.  
  
> [!NOTE]
>  Die Zeilenvorlage wird nur verwendet, wenn Zeilen hinzugefügt werden.  Sie können keine vorhandenen Zeilen ändern, indem Sie die Zeilenvorlage ändern.  
  
### So verwenden Sie die Zeilenvorlage  
  
-   Legen Sie für das von der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName>\-Eigenschaft abgerufene Objekt Eigenschaften fest.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement mit dem Namen`dataGridView1` muss vorhanden sein.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> und <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridViewRow>   
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName>   
 [Grundlegende Formatierungen und Formate im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)