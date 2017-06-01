---
title: "&#220;bersicht &#252;ber das PrintPreviewControl-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "PrintPreviewControl"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Seitenansicht"
  - "PrintPreviewControl-Steuerelement"
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# &#220;bersicht &#252;ber das PrintPreviewControl-Steuerelement (Windows&#160;Forms)
Mit dem <xref:System.Windows.Forms.PrintPreviewControl> von Windows Forms wird ein [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) so angezeigt, wie es gedruckt wird.  Da dieses Steuerelement weder Schaltflächen noch andere Elemente einer Benutzeroberfläche besitzt, verwenden Sie <xref:System.Windows.Forms.PrintPreviewControl> normalerweise nur, wenn Sie eine eigene Benutzeroberfläche für die Seitenansicht programmieren möchten.  Für die Standardbenutzeroberfläche verwenden Sie ein <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelement. Eine Übersicht finden Sie unter [Übersicht über das PrintPreviewDialog\-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md).  
  
## Haupteigenschaften  
 Die Schlüsseleigenschaft dieses Steuerelements ist <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, mit der das Dokument für die Seitenansicht festgelegt wird.  Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument>\-Objekt sein.  Eine Übersicht über das Erstellen von Dokumenten zum Drucken finden Sie unter [Übersicht über die PrintDocument\-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) und [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).  Mit der <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>\-Eigenschaft und der <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>\-Eigenschaft wird die Anzahl der Seiten festgelegt, die horizontal und vertikal auf dem Steuerelement angezeigt werden.  Mit der Bildkantenglättung können Sie den Text glatter erscheinen lassen, unter Umständen wird die Anzeige dadurch allerdings verlangsamt. Um diese Funktion zu verwenden, legen Sie die <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A>\-Eigenschaft auf `true` fest.  
  
## Siehe auch  
 <xref:System.Windows.Forms.PrintPreviewControl>   
 [Übersicht über das PrintPreviewDialog\-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)   
 [PrintPreviewControl\-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)   
 [Dialogfeld\-Steuerelemente und \-Komponenten](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)