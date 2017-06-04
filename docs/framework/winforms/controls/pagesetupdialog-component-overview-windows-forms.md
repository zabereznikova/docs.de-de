---
title: "&#220;bersicht &#252;ber die PageSetupDialog-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "PageSetupDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Seite einrichten (Dialogfeld), Anzeigen"
  - "PageSetupDialog-Komponente"
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# &#220;bersicht &#252;ber die PageSetupDialog-Komponente (Windows&#160;Forms)
Die <xref:System.Windows.Forms.PageSetupDialog>\-Komponente in Windows Forms ist ein vorkonfiguriertes Dialogfeld, mit dem Seiten für das Drucken in Windows\-basierten Anwendungen eingerichtet werden.  Verwenden Sie die Komponente in einer Windows\-basierten Anwendung als einfache Lösung zum Festlegen von Seiteneinstellungen durch Benutzer, statt ein eigenes Dialogfeld zu konfigurieren.  Sie können Benutzern die Möglichkeit geben, die Einstellungen für Rahmen und Ränder sowie Kopf\- und Fußzeilen festzulegen und zwischen Hoch\- und Querformat zu wählen.  Wenn Sie Windows\-Standarddialogfelder verwenden, erstellen Sie Anwendungen, mit deren Basisfunktionen Benutzer sofort vertraut sind.  
  
## Wichtige Eigenschaften und Methoden  
 Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode, um das Dialogfeld zur Laufzeit anzuzeigen.  Diese Komponente besitzt einstellbare Eigenschaften, die sich entweder auf eine einzelne Seite \(<xref:System.Drawing.Printing.PrintDocument>\-Klasse\) oder ein Dokument \(<xref:System.Drawing.Printing.PageSettings>\-Klasse\) beziehen.  Außerdem können Sie die <xref:System.Windows.Forms.PageSetupDialog>\-Komponente zum Festlegen bestimmter Druckereinstellungen verwenden, die in der <xref:System.Drawing.Printing.PrinterSettings>\-Klasse gespeichert sind.  
  
 Nachdem die <xref:System.Windows.Forms.PageSetupDialog>\-Komponente einem Formular hinzugefügt wurde, wird sie auf der Komponentenleiste am unteren Rand des Windows Forms\-Designers angezeigt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.PageSetupDialog>   
 [PageSetupDialog\-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)