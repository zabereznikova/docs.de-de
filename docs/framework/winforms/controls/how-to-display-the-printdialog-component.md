---
title: Vorgehensweise beim Anzeigen der PrintDialog-Komponente
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: 198ae75d407bd1837033a1cc186d84ff972fdc2f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285154"
---
# <a name="how-to-display-the-printdialog-component"></a>Vorgehensweise beim Anzeigen der PrintDialog-Komponente

Die <xref:System.Windows.Forms.PrintDialog> Komponente ist das standardmäßige Druckdialogfeld in Windows, das viele der Benutzer vertraut werden. Da Ihre Benutzer sofort zurechtfinden werden, ist es wäre vorteilhaft für die Verwendung der <xref:System.Windows.Forms.PrintDialog> Komponente.

## <a name="to-display-the-printdialog-component"></a>So zeigen Sie die PrintDialog-Komponente an

- Rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A> innerhalb des Codes der Anwendung aus.

     Sobald die Komponente angezeigt wird, können die Benutzer damit interagieren und die Eigenschaften für den Druckauftrag einstellen. Diese werden gespeichert, der <xref:System.Drawing.Printing.PrinterSettings> Klasse (und die <xref:System.Drawing.Printing.PageSettings> Klasse, wenn der Benutzer greift auf die [PageSetupDialog-Komponente](pagesetupdialog-component-windows-forms.md) über die <xref:System.Windows.Forms.PrintDialog> Komponente) mit dem Druckauftrag verknüpften. Dann können Sie Aufrufe an die von ihnen eingestellten Eigenschaften durchführen, um die spezifischen Merkmale des Druckauftrags anzugeben.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen von Druckaufträgen in Standard-Windows Forms](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [Vorgehensweise: Erfassen von Benutzereingaben in einem "PrintDialog" zur Laufzeit](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [PrintPreviewDialog-Steuerelement](printpreviewdialog-control-windows-forms.md)
- [PrintDialog-Komponente](printdialog-component-windows-forms.md)
- [Druckunterstützung in Windows Forms](../advanced/windows-forms-print-support.md)
- [Windows Forms-Steuerelemente](index.md)