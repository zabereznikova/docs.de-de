---
title: "Übersicht über das PrintPreviewControl-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d50e772cf870d47314a25347f4909367062ffb94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Übersicht über das PrintPreviewControl-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> dient zum Anzeigen einer [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) wie es gedruckt wird. Da dieses Steuerelement weder Schaltflächen noch andere Elemente einer Benutzeroberfläche besitzt, verwenden Sie <xref:System.Windows.Forms.PrintPreviewControl> in der Regel nur, wenn Sie eine eigene Benutzeroberfläche für die Seitenansicht programmieren möchten. Wenn Sie die Standardbenutzeroberfläche möchten, verwenden eine <xref:System.Windows.Forms.PrintPreviewDialog> steuern, finden Sie unter [Übersicht über das PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) eine Übersicht über.  
  
## <a name="key-properties"></a>Wichtige Eigenschaften  
 Das Steuerelement Schlüsseleigenschaft ist <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, wodurch das Dokument in der Vorschau angezeigt werden. Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt. Einen Überblick über das Erstellen von Dokumenten für das Drucken finden Sie unter [Übersicht über die PrintDocument-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) und [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md). Die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> Eigenschaften bestimmen die Anzahl der Seiten, die horizontal und vertikal auf dem Steuerelement angezeigt. Antialiasing kann den Text glattere angezeigt, aber es kann auch die Anzeige langsamer, Legen Sie zur Verwendung der <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> Eigenschaft `true`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [Übersicht über das PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [PrintPreviewControl-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [Dialogfeld-Steuerelemente und -Komponenten](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
