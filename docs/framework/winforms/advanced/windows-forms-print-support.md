---
title: Druckunterstützung in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 8e008f2cb4b2f32cdba676e68d9fd790530e2b06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011847"
---
# <a name="windows-forms-print-support"></a>Druckunterstützung in Windows Forms
Beim Drucken in Windows Forms besteht in erster Linie mit der [PrintDocument-Komponente](../controls/printdocument-component-windows-forms.md) Komponente, bei dem Benutzer ermöglichen, zu drucken, und die [PrintPreviewDialog-Steuerelement](../controls/printpreviewdialog-control-windows-forms.md) Steuerelement ["PrintDialog" Komponente](../controls/printdialog-component-windows-forms.md) und [PageSetupDialog-Komponente](../controls/pagesetupdialog-component-windows-forms.md) Komponenten eine vertraute grafische Oberfläche für Benutzer, die mit dem Windows-Betriebssystem vertraut zu sein.  
  
 Normalerweise erstellen Sie eine neue Instanz der der <xref:System.Drawing.Printing.PrintDocument> Komponente legen Sie die Eigenschaften, die beschreiben, was gedruckt, mit der <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings> Klassen, und rufen die <xref:System.Drawing.Printing.PrintDocument.Print%2A> Methode, um das Dokument zu drucken.  
  
 Im Verlauf der Druck aus einer Windows-basierten Anwendung die <xref:System.Drawing.Printing.PrintDocument> Komponente zeigt ein Dialogfeld abbrechen, um Benutzer auf die Tatsache, dass die Drucken stattfindet und den Druckauftrag abgebrochen werden soll.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Erstellen von Druckaufträgen in Standard-Windows Forms](how-to-create-standard-windows-forms-print-jobs.md)  
 Erläutert, wie die <xref:System.Drawing.Printing.PrintDocument> Komponente zum Drucken in Windows Forms.  
  
 [Vorgehensweise: Erfassen von Benutzereingaben in einem "PrintDialog" zur Laufzeit](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Erläutert, wie so ändern Sie die ausgewählten Druckoptionen programmgesteuert mithilfe der <xref:System.Windows.Forms.PrintDialog> Komponente.  
  
 [Vorgehensweise: Auswählen der Drucker, die angefügt werden, auf dem Computer eines Benutzers in Windows Forms](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Beschreibt das Ändern der Drucker zum Drucken auf mit der <xref:System.Windows.Forms.PrintDialog> -Komponente zur Laufzeit.  
  
 [Vorgehensweise: Drucken von Grafiken in Windows Forms](how-to-print-graphics-in-windows-forms.md)  
 Beschreibt, sendende von Grafiken an den Drucker.  
  
 [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Beschreibt senden Text an den Drucker.  
  
 [Vorgehensweise: Vollständige Windows Forms-Druckaufträge](how-to-complete-windows-forms-print-jobs.md)  
 Erläutert, wie Benutzer bis zum Abschluss eines Druckauftrags benachrichtigt.  
  
 [Vorgehensweise: Drucken eines Windows Form](how-to-print-a-windows-form.md)  
 Zeigt, wie eine Kopie des aktuellen Formulars gedruckt.  
  
 [Vorgehensweise: Drucken Sie in Windows Forms unter Verwendung der Seitenansicht](how-to-print-in-windows-forms-using-print-preview.md)  
 Zeigt, wie eine <xref:System.Windows.Forms.PrintPreviewDialog> zum Drucken eines Dokuments.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [PrintDocument-Komponente](../controls/printdocument-component-windows-forms.md)  
 Erläutert die Verwendung des der <xref:System.Drawing.Printing.PrintDocument> Komponente.  
  
 [PrintDialog-Komponente](../controls/printdialog-component-windows-forms.md)  
 Erläutert die Verwendung des der <xref:System.Windows.Forms.PrintDialog> Komponente.  
  
 [PrintPreviewDialog-Steuerelement](../controls/printpreviewdialog-control-windows-forms.md)  
 Erläutert die Verwendung des der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement.  
  
 [PageSetupDialog-Komponente](../controls/pagesetupdialog-component-windows-forms.md)  
 Erläutert die Verwendung des der <xref:System.Windows.Forms.PageSetupDialog> Komponente.  
  
 <xref:System.Drawing.Printing>  
 Beschreibt die Klassen in der <xref:System.Drawing.Printing> Namespace.
