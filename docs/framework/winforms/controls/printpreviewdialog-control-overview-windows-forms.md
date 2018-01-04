---
title: "Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed071a4d38a0167ac9414ee7d383736dd38a62a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement ist ein vorkonfiguriertes Dialogfeld zum Anzeigen verwendet wie eine [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) gedruckt wird angezeigt. Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung, anstatt ein eigenes Dialogfeld zu konfigurieren. Das Steuerelement enthält Schaltflächen zum Drucken, Vergrößern, Anzeigen mindestens einer Seite und Schließen des Dialogfelds.  
  
## <a name="key-properties-and-methods"></a>Wichtige Eigenschaften und Methoden  
 Das Steuerelement Schlüsseleigenschaft ist <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, wodurch das Dokument in der Vorschau angezeigt werden. Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt. Um das Dialogfeld anzuzeigen, rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A> Methode. Anti-Aliasing kann den Text glattere angezeigt, aber es kann auch die Anzeige langsamer, Legen Sie zur Verwendung der <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> Eigenschaft `true`.  
  
 Bestimmte Eigenschaften stehen über die <xref:System.Windows.Forms.PrintPreviewControl> , die die <xref:System.Windows.Forms.PrintPreviewDialog> enthält. (Sie müssen nicht dies hinzufügen <xref:System.Windows.Forms.PrintPreviewControl> in das Formular; er ist automatisch enthalten, innerhalb der <xref:System.Windows.Forms.PrintPreviewDialog> Wenn Sie das Dialogfeld zum Formular hinzufügen.) Beispiele für Eigenschaften, die über die <xref:System.Windows.Forms.PrintPreviewControl> sind die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> Eigenschaften, die bestimmen, die Anzahl der Seiten, die horizontal und vertikal auf dem Steuerelement angezeigt. Sie können den Zugriff auf die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> Eigenschaft als `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], oder `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [Übersicht über das PrintPreviewControl-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [PrintPreviewDialog-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Dialogfeld-Steuerelemente und -Komponenten](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
