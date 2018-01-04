---
title: "Druckunterstützung in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81f89ee41eb9f8b492ab12e30ae4580cdffbd8f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-print-support"></a>Druckunterstützung in Windows Forms
Beim Drucken in Windows Forms besteht im Wesentlichen aus mithilfe der [PrintDocument-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) -Komponente verwendet, damit der Benutzer das Drucken, und die [PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) Steuerelement [PrintDialog Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) und [PageSetupDialog-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) Komponenten zum Bereitstellen einer vertrauten grafischen Oberfläche für Benutzer, die daran gewöhnt, zu der Windows-Betriebssystem.  
  
 Normalerweise erstellen Sie eine neue Instanz der der <xref:System.Drawing.Printing.PrintDocument> Komponente, legen Sie die Eigenschaften, die beschreiben, was gedruckt, mit der <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings> Klassen, und rufen die <xref:System.Drawing.Printing.PrintDocument.Print%2A> Methode, um das Dokument zu drucken.  
  
 Im Verlauf der Druck aus einer Windows-basierten Anwendung die <xref:System.Drawing.Printing.PrintDocument> Komponente wird ein Dialogfeld zum Drucken von Abort anzeigen, um Benutzer darauf aufmerksam die Tatsache, dass heraus drucken und ermöglichen den Druckauftrag abgebrochen wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 Erklärt, wie die <xref:System.Drawing.Printing.PrintDocument> Komponente zum Drucken aus einem Windows Form.  
  
 [Gewusst wie: Erfassen von Benutzereingaben in einem „PrintDialog“ zur Laufzeit](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Erläutert, wie so ändern Sie die ausgewählten Druckoptionen programmgesteuert mithilfe der <xref:System.Windows.Forms.PrintDialog> Komponente.  
  
 [Gewusst wie: Auswählen der einem Benutzercomputer zugewiesenen Drucker in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Beschreibt das Ändern der Drucker zum Drucken auf die Verwendung der <xref:System.Windows.Forms.PrintDialog> -Komponente zur Laufzeit.  
  
 [Vorgehensweise: Drucken von Grafiken in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 Beschreibt, an den Drucker sendende von Grafiken.  
  
 [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Beschreibt, Senden von Text an den Drucker.  
  
 [Gewusst wie: Fertigstellen von Druckaufträgen in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 Erläutert, wie Benutzer bis zum Abschluss eines Druckauftrags benachrichtigt.  
  
 [Gewusst wie: Drucken eines Windows Form](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 Zeigt, wie eine Kopie des aktuellen Formulars gedruckt.  
  
 [Gewusst wie: Drucken in Windows Forms unter Verwendung der Seitenansicht](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 Zeigt, wie eine <xref:System.Windows.Forms.PrintPreviewDialog> für das Drucken eines Dokuments.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [PrintDocument-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 Erläutert die Verwendung des der <xref:System.Drawing.Printing.PrintDocument> Komponente.  
  
 [PrintDialog-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 Erläutert die Verwendung des der <xref:System.Windows.Forms.PrintDialog> Komponente.  
  
 [PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 Erläutert die Verwendung des der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement.  
  
 [PageSetupDialog-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 Erläutert die Verwendung des der <xref:System.Windows.Forms.PageSetupDialog> Komponente.  
  
 <xref:System.Drawing.Printing>  
 Beschreibt die Klassen in der <xref:System.Drawing.Printing> Namespace.
