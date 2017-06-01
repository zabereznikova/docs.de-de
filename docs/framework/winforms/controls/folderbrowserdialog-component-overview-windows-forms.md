---
title: "&#220;bersicht &#252;ber die FolderBrowserDialog-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "FolderBrowserDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Verzeichnisse [Windows Forms], Aktivieren des Navigierens in Anwendungen"
  - "FolderBrowserDialog-Komponente [Windows Forms], Informationen über FolderBrowserDialog"
  - "Ordner [Windows Forms], Aktivieren des Navigierens in Anwendungen"
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# &#220;bersicht &#252;ber die FolderBrowserDialog-Komponente (Windows&#160;Forms)
Die <xref:System.Windows.Forms.FolderBrowserDialog>\-Komponente in Windows Forms ist ein modales Dialogfeld, das zum Durchsuchen und Auswählen von Ordnern verwendet wird.  Aus der <xref:System.Windows.Forms.FolderBrowserDialog>\-Komponente heraus können auch neue Ordner erstellt werden.  
  
> [!NOTE]
>  Um anstelle von Ordnern Dateien auszuwählen, verwenden Sie die [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)\-Komponente.  
  
 Die <xref:System.Windows.Forms.FolderBrowserDialog>\-Komponente wird zur Laufzeit unter Verwendung der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode angezeigt.  Legen Sie mit der <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>\-Eigenschaft den obersten Ordner und die Unterordner fest, die in der Strukturansicht des Dialogfelds angezeigt werden sollen.  Wenn das Dialogfeld angezeigt wurde, können Sie mit der <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>\-Eigenschaft den Pfad des gewählten Ordners abrufen.  
  
 Nachdem die <xref:System.Windows.Forms.FolderBrowserDialog>\-Komponente einem Formular hinzugefügt wurde, wird sie auf der Komponentenleiste am unteren Rand des Windows Forms\-Designers angezeigt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.FolderBrowserDialog>   
 [Gewusst wie: Auswählen von Ordnern mit der FolderBrowserDialog\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)   
 [FolderBrowserDialog\-Komponente](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)