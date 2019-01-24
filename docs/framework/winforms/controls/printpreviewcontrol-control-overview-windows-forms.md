---
title: Übersicht über das PrintPreviewControl-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: acf21365d2694cdc1bf2213187fb2ae047205c4c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665374"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Übersicht über das PrintPreviewControl-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.PrintPreviewControl> dient zum Anzeigen einer [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) wie es gedruckt wird. Da dieses Steuerelement weder Schaltflächen noch andere Elemente einer Benutzeroberfläche besitzt, verwenden Sie <xref:System.Windows.Forms.PrintPreviewControl> in der Regel nur, wenn Sie eine eigene Benutzeroberfläche für die Seitenansicht programmieren möchten. Wenn Sie die Standardbenutzeroberfläche möchten, verwenden eine <xref:System.Windows.Forms.PrintPreviewDialog> steuern, finden Sie unter [Übersicht über das PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) eine Übersicht über.  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Die Schlüsseleigenschaft des Steuerelements ist <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, wodurch das Dokument, in der Vorschau angezeigt werden. Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt. Einen Überblick über das Erstellen von Dokumenten für das Drucken finden Sie unter [Übersicht über die PrintDocument-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) und [drucken-Unterstützung für Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md). Die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> Eigenschaften bestimmen die Anzahl der Seiten, die horizontal und vertikal auf dem Steuerelement angezeigt. Antialiasing kann legen Sie den Text, der reibungslose angezeigt werden kann, jedoch auch die Anzeige langsamer; um es zu verwenden, legen die <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> Eigenschaft `true`.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.PrintPreviewControl>
- [Übersicht über das PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)
- [PrintPreviewControl-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)
- [Dialogfeld-Steuerelemente und -Komponenten](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
