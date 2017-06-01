---
title: "&#220;bersicht &#252;ber die OpenFileDialog-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "OpenFileDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datei öffnen (Dialogfeld), Anzeigen in Windows Forms"
  - "OpenFileDialog-Komponente, Informationen über OpenFileDialog"
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber die OpenFileDialog-Komponente (Windows&#160;Forms)
Die <xref:System.Windows.Forms.OpenFileDialog>\-Komponente in Windows Forms ist ein vorkonfiguriertes Dialogfeld.  Es entspricht dem Dialogfeld **Datei öffnen** des Windows\-Betriebssystems.  Es erbt von der <xref:System.Windows.Forms.CommonDialog>\-Klasse.  
  
## Verwenden dieser Komponente  
 Verwenden Sie diese Komponente in der Windows\-basierten Anwendung als einfache Lösung zur Dateiauswahl anstelle eines eigenen Dialogfelds.  Wenn Sie Windows\-Standarddialogfelder verwenden, erstellen Sie Anwendungen, mit deren Basisfunktionen Benutzer sofort vertraut sind.  Sie müssen sich jedoch darüber im Klaren sein, dass Sie, wenn Sie die <xref:System.Windows.Forms.OpenFileDialog>\-Komponente verwenden, Ihre eigene Logik zum Öffnen von Dateien schreiben müssen.  
  
 Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode, um das Dialogfeld zur Laufzeit anzuzeigen.  Mit der <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>\-Eigenschaft können Sie Benutzern die Auswahl mehrerer zu öffnender Dateien ermöglichen.  Außerdem können Sie mit der <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A>\-Eigenschaft festlegen, ob im Dialogfeld ein Kontrollkästchen für schreibgeschützten Zugriff angezeigt wird.  Die <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A>\-Eigenschaft gibt an, ob das Schreibschutz\-Kontrollkästchen aktiviert ist.  Schließlich legt die <xref:System.Windows.Forms.FileDialog.Filter%2A>\-Eigenschaft die aktuelle Filterzeichenfolge für den Dateinamen fest. Diese bestimmt die Auswahlmöglichkeiten, die im Feld Dateityp angezeigt werden.  
  
 Nachdem die <xref:System.Windows.Forms.OpenFileDialog>\-Komponente einem Formular hinzugefügt wurde, wird sie auf der Komponentenleiste am unteren Rand des Windows Forms\-Designers angezeigt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.OpenFileDialog>   
 [OpenFileDialog\-Komponente](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)