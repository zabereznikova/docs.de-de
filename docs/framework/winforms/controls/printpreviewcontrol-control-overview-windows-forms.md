---
title: Übersicht über das PrintPreviewControl-Steuerelement
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741435"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Übersicht über das PrintPreviewControl-Steuerelement (Windows Forms)
Die Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> wird zum Anzeigen eines [PrintDocument](printdocument-component-windows-forms.md) verwendet, das beim Drucken angezeigt wird. Da dieses Steuerelement weder Schaltflächen noch andere Elemente einer Benutzeroberfläche besitzt, verwenden Sie <xref:System.Windows.Forms.PrintPreviewControl> in der Regel nur, wenn Sie eine eigene Benutzeroberfläche für die Seitenansicht programmieren möchten. Wenn Sie die Standardbenutzer Oberfläche verwenden möchten, verwenden Sie ein <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement. eine Übersicht finden Sie unter [Übersicht über das PrintPreviewDialog-Steuer](printpreviewdialog-control-overview-windows-forms.md) Element.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Die Schlüsseleigenschaft des Steuer Elements ist <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, wodurch das Dokument als Vorschau angezeigt wird. Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt sein. Eine Übersicht über das Erstellen von Dokumenten für den Druck finden Sie unter Übersicht über die [PrintDocument-Komponente](printdocument-component-overview-windows-forms.md) und [Windows Forms Druckunterstützung](../advanced/windows-forms-print-support.md). Die Eigenschaften <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> bestimmen die Anzahl der Seiten, die auf dem Steuerelement horizontal und vertikal angezeigt werden. Das Antialiasing kann dazu führen, dass der Text glatter erscheint, aber auch die Anzeige langsamer wird. Legen Sie die <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A>-Eigenschaft auf `true`fest, um Sie zu verwenden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.PrintPreviewControl>
- [Übersicht über das PrintPreviewDialog-Steuerelement](printpreviewdialog-control-overview-windows-forms.md)
- [PrintPreviewControl-Steuerelement](printpreviewcontrol-control-windows-forms.md)
- [Dialogfeld-Steuerelemente und -Komponenten](dialog-box-controls-and-components-windows-forms.md)
