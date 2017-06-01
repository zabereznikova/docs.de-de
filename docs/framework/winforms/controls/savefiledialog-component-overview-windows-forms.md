---
title: "&#220;bersicht &#252;ber die SaveFileDialog-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "SaveFileDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datei speichern (Dialogfeld), Anzeigen"
  - "SaveFileDialog-Komponente, Informationen über SaveFileDialog"
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# &#220;bersicht &#252;ber die SaveFileDialog-Komponente (Windows&#160;Forms)
Die <xref:System.Windows.Forms.SaveFileDialog>\-Komponente in Windows Forms ist ein vorkonfiguriertes Dialogfeld.  Es entspricht dem in Windows verwendeten Standarddialogfeld **Datei speichern**.  Es erbt von der <xref:System.Windows.Forms.CommonDialog>\-Klasse.  
  
## Arbeiten mit der SaveFileDialog\-Komponente  
 Verwenden Sie es anstelle eines eigenen Dialogfelds als einfache Lösung, um Benutzern das Speichern von Dateien zu ermöglichen.  Wenn Sie Windows\-Standarddialogfelder verwenden, sind die Benutzer sofort mit den Basisfunktionen Ihrer Anwendungen vertraut.  Sie müssen sich jedoch darüber im Klaren sein, dass Sie, wenn Sie die <xref:System.Windows.Forms.SaveFileDialog>\-Komponente verwenden, Ihre eigene Logik zum Speichern von Dateien schreiben müssen.  
  
 Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode, um das Dialogfeld zur Laufzeit anzuzeigen.  Außerdem können Sie eine Datei mit der <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>\-Methode im Lese\-\/Schreibmodus öffnen.  
  
 Nachdem die <xref:System.Windows.Forms.SaveFileDialog>\-Komponente einem Formular hinzugefügt wurde, wird sie auf der Komponentenleiste am unteren Rand des Windows Forms\-Designers angezeigt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.SaveFileDialog>   
 [SaveFileDialog\-Komponente](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)