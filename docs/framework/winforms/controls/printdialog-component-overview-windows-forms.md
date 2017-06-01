---
title: "&#220;bersicht &#252;ber die PrintDialog-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "PrintDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Drucken (Dialogfeld), Anzeigen"
  - "PrintDialog-Komponente [Windows Forms], Informationen über die PrintDialog-Komponente"
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber die PrintDialog-Komponente (Windows&#160;Forms)
Die [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)\-Komponente in Windows Forms ist ein vordefiniertes Dialogfeld, mit dem ein Drucker und die zu druckenden Seiten ausgewählt sowie andere Eigenschaften festgelegt werden können, die mit dem Drucken in Windows\-basierten Anwendungen zusammenhängen.  Verwenden Sie es anstelle eines eigenen Dialogfelds als einfache Lösung zur Wahl von Druckereinstellungen sowie von mit dem Drucken verbundenen Einstellungen.  Sie können Benutzern ermöglichen, verschiedene Teile ihrer Dokumente zu drucken: das gesamte Dokument, einen bestimmten Seitenbereich oder einen markierten Teil.  Wenn Sie Windows\-Standarddialogfelder verwenden, erstellen Sie Anwendungen, mit deren Basisfunktionen Benutzer sofort vertraut sind.  Die <xref:System.Windows.Forms.PrintDialog>\-Komponente erbt von der <xref:System.Windows.Forms.CommonDialog>\-Klasse.  
  
## Arbeiten mit der Komponente  
 Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode, um das Dialogfeld zur Laufzeit anzuzeigen.  Diese Komponente besitzt Eigenschaften, die sich entweder auf einen einzelnen Druckauftrag  \(<xref:System.Drawing.Printing.PrintDocument>\-Klasse\) oder die Einstellungen eines einzelnen Druckers \(<xref:System.Drawing.Printing.PrinterSettings>\-Klasse\) beziehen.  Diese können der Reihe nach von mehreren Druckern gemeinsam genutzt werden.  
  
 Nachdem die <xref:System.Windows.Forms.PrintDialog>\-Komponente einem Formular hinzugefügt wurde, wird sie auf der Komponentenleiste am unteren Rand des Windows Forms\-Designers angezeigt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.PrintDialog>   
 [PrintDialog\-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)