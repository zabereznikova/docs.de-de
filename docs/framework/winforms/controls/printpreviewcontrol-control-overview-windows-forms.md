---
title: Übersicht über das PrintPreviewControl-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: e9f1c2ae912b6beeba70c318b94a3052e2f99acb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122498"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Übersicht über das PrintPreviewControl-Steuerelement (Windows Forms)
Die Windows-Formulare <xref:System.Windows.Forms.PrintPreviewControl> dient zum Anzeigen einer [PrintDocument](printdocument-component-windows-forms.md) wie es gedruckt wird. Da dieses Steuerelement weder Schaltflächen noch andere Elemente einer Benutzeroberfläche besitzt, verwenden Sie <xref:System.Windows.Forms.PrintPreviewControl> in der Regel nur, wenn Sie eine eigene Benutzeroberfläche für die Seitenansicht programmieren möchten. Wenn Sie die Standardbenutzeroberfläche möchten, verwenden eine <xref:System.Windows.Forms.PrintPreviewDialog> steuern, finden Sie unter [Übersicht über das PrintPreviewDialog-Steuerelement](printpreviewdialog-control-overview-windows-forms.md) eine Übersicht über.  
  
## <a name="key-properties"></a>Schlüsseleigenschaften  
 Die Schlüsseleigenschaft des Steuerelements ist <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, wodurch das Dokument, in der Vorschau angezeigt werden. Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt. Einen Überblick über das Erstellen von Dokumenten für das Drucken finden Sie unter [Übersicht über die PrintDocument-Komponente](printdocument-component-overview-windows-forms.md) und [drucken-Unterstützung für Windows Forms](../advanced/windows-forms-print-support.md). Die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> Eigenschaften bestimmen die Anzahl der Seiten, die horizontal und vertikal auf dem Steuerelement angezeigt. Antialiasing kann legen Sie den Text, der reibungslose angezeigt werden kann, jedoch auch die Anzeige langsamer; um es zu verwenden, legen die <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> Eigenschaft `true`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.PrintPreviewControl>
- [Übersicht über das PrintPreviewDialog-Steuerelement](printpreviewdialog-control-overview-windows-forms.md)
- [PrintPreviewControl-Steuerelement](printpreviewcontrol-control-windows-forms.md)
- [Dialogfeld-Steuerelemente und -Komponenten](dialog-box-controls-and-components-windows-forms.md)
