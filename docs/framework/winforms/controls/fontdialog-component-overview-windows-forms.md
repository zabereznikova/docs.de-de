---
title: "&#220;bersicht &#252;ber die FontDialog-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "FontDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Schriftart (Dialogfeld)"
  - "Schriftart (Dialogfeld), Windows Forms"
  - "FontDialog-Komponente [Windows Forms], Informationen über die FontDialog-Komponente"
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber die FontDialog-Komponente (Windows&#160;Forms)
Die <xref:System.Windows.Forms.FontDialog>\-Komponente in Windows Forms ist ein vorkonfiguriertes Dialogfeld, bei dem es sich um das Windows\-Standarddialogfeld **Schriftart** handelt, in dem die auf dem System installierten Schriftarten angezeigt werden.  Verwenden Sie es in Ihrer Windows\-basierten Anwendung anstelle eines eigenen Dialogfelds als einfache Lösung zur Auswahl von Schriftarten.  
  
 Standardmäßig zeigt das Dialogfeld Listenfelder für Schriftart, Schriftschnitt und Schriftgröße, Kontrollkästchen für Effekte wie Durchgestrichen und Unterstrichen, eine Dropdownliste für Skripts sowie ein Beispiel dafür, wie die Schriftart aussehen wird.  \("Skript" bezieht sich auf verschiedene Zeichenskripts, die für eine bestimmte Schriftart, z. B. Hebräisch oder Japanisch, verfügbar sind.\) Rufen Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode auf, um das Dialogfeld Schriftart anzuzeigen.  
  
## Haupteigenschaften  
 Die Komponente besitzt eine Reihe von Eigenschaften, mit denen ihre Darstellung konfiguriert wird.  Die Eigenschaften, die die Auswahlmöglichkeiten im Dialogfeld festlegen, sind <xref:System.Windows.Forms.FontDialog.Font%2A> und <xref:System.Windows.Forms.FontDialog.Color%2A>.  Die <xref:System.Windows.Forms.FontDialog.Font%2A>\-Eigenschaft legt Schriftart, Schriftschnitt, Schriftgröße, Skript und Effekte fest, z. B.  `Arial, 10pt, style=Italic, Strikeout`.  
  
## Siehe auch  
 <xref:System.Windows.Forms.FontDialog>   
 [FontDialog\-Komponente](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)