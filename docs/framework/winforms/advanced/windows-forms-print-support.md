---
title: "Druckunterst&#252;tzung in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Formulare, Drucken (mit dem Designer)"
  - "Drucken [Windows Forms]"
  - "Drucken [Windows Forms], -Druckunterstützung"
  - "Drucken, Windows Forms, Unterstützung"
  - "Windows Forms, Drucken"
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Druckunterst&#252;tzung in Windows&#160;Forms
Das Drucken in Windows Forms besteht hauptsächlich in der Verwendung von [PrintDocument\-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md), um dem Benutzer das eigentliche Drucken zu ermöglichen, und in der Verwendung von [PrintPreviewDialog\-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) sowie von [PrintDialog\-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) und von [PageSetupDialog\-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md), um Benutzern, die mit dem Windows\-Betriebssystem vertraut sind, die gewohnte grafische Benutzeroberfläche bereitzustellen.  
  
 Zum Drucken erstellen Sie i. d. R. eine neue Instanz der <xref:System.Drawing.Printing.PrintDocument>\-Komponente, legen mithilfe der <xref:System.Drawing.Printing.PrinterSettings>\-Klasse und der <xref:System.Drawing.Printing.PageSettings>\-Klasse die Eigenschaften fest, die die Druckeinstellungen angeben, und rufen zum eigentlichen Drucken des Dokuments die <xref:System.Drawing.Printing.PrintDocument.Print%2A>\-Methode auf.  
  
 Während Sie aus einer Windows\-basierten Anwendung heraus drucken, zeigt die <xref:System.Drawing.Printing.PrintDocument>\-Komponente ein Dialogfeld zum Abbrechen des Druckvorgangs an. Dieses informiert die Benutzer über den laufenden Druckvorgang und ermöglicht das Abbrechen.  
  
## In diesem Abschnitt  
 [Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 Erläutert die Verwendung der <xref:System.Drawing.Printing.PrintDocument>\-Komponente zum Drucken eines Windows Forms.  
  
 [Gewusst wie: Erfassen von Benutzereingaben in einem "PrintDialog" zur Laufzeit](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Erläutert die programmgesteuerte Änderung ausgewählter Druckoptionen mithilfe der <xref:System.Windows.Forms.PrintDialog>\-Komponente.  
  
 [Gewusst wie: Auswählen der einem Benutzercomputer zugewiesenen Drucker in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Beschreibt das Ändern des zum Drucken ausgewählten Druckers zur Laufzeit mithilfe der <xref:System.Windows.Forms.PrintDialog>\-Komponente.  
  
 [Gewusst wie: Drucken von Grafiken in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 Beschreibt das Senden von Grafiken an den Drucker.  
  
 [Gewusst wie: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Beschreibt das Senden von Text an den Drucker.  
  
 [Gewusst wie: Fertigstellen von Druckaufträgen in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 Erläutert, wie Benutzer über die Beendigung eines Druckauftrags benachrichtigt werden können.  
  
 [Gewusst wie: Drucken eines Windows Form](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 Veranschaulicht das Drucken des aktuellen Formulars.  
  
 [Gewusst wie: Drucken in Windows Forms unter Verwendung der Seitenansicht](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 Zeigt die Verwendung von <xref:System.Windows.Forms.PrintPreviewDialog> zum Drucken eines Dokuments.  
  
## Verwandte Abschnitte  
 [PrintDocument\-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 Erläutert die Verwendung der <xref:System.Drawing.Printing.PrintDocument>\-Komponente.  
  
 [PrintDialog\-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 Erläutert die Verwendung der <xref:System.Windows.Forms.PrintDialog>\-Komponente.  
  
 [PrintPreviewDialog\-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 Erläutert die Verwendung des <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelements.  
  
 [PageSetupDialog\-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 Erläutert die Verwendung der <xref:System.Windows.Forms.PageSetupDialog>\-Komponente.  
  
 <xref:System.Drawing.Printing>  
 Beschreibt die Klassen im <xref:System.Drawing.Printing>\-Namespace.