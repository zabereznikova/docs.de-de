---
title: "&#220;bersicht &#252;ber das PrintPreviewDialog-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
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
  - "PrintPreviewDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "PrintPreviewDialog-Steuerelement (mit dem Designer), Informationen über PrintPreviewDialog"
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# &#220;bersicht &#252;ber das PrintPreviewDialog-Steuerelement (Windows&#160;Forms)
Das <xref:System.Windows.Forms.PrintPreviewDialog>\-Steuerelement in Windows Forms ist ein vorkonfiguriertes Dialogfeld, mit dem ein [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) so angezeigt wird, wie es gedruckt wird.  Verwenden Sie es als einfache Lösung in der Windows\-basierten Anwendung, anstatt ein eigenes Dialogfeld zu konfigurieren.  Das Steuerelement enthält Schaltflächen zum Drucken, Vergrößern, Anzeigen einer oder mehrerer Seiten sowie zum Schließen des Dialogfelds.  
  
## Wichtige Eigenschaften und Methoden  
 Die Schlüsseleigenschaft dieses Steuerelements ist <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, mit der das Dokument für die Seitenansicht festgelegt wird.  Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument>\-Objekt sein.  Um das Dialogfeld anzuzeigen, müssen Sie seine <xref:System.Windows.Forms.Form.ShowDialog%2A>\-Methode aufrufen.  Mit der Bildkantenglättung können Sie den Text glatter erscheinen lassen, unter Umständen wird die Anzeige dadurch allerdings verlangsamt. Um diese Funktion zu verwenden, legen Sie die <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A>\-Eigenschaft auf `true` fest.  
  
 Bestimmte Eigenschaften sind über das <xref:System.Windows.Forms.PrintPreviewControl> im <xref:System.Windows.Forms.PrintPreviewDialog> verfügbar.  \(Sie müssen dem Formular das <xref:System.Windows.Forms.PrintPreviewControl> nicht extra hinzufügen, es ist automatisch in <xref:System.Windows.Forms.PrintPreviewDialog> enthalten, wenn Sie dem Formular das Dialogfeld hinzufügen.\) Beispiele für Eigenschaften, die über das <xref:System.Windows.Forms.PrintPreviewControl> verfügbar sind, sind die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>\-Eigenschaft und die <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>\-Eigenschaft, mit denen die Anzahl der Seiten festgelegt wird, die horizontal oder vertikal auf dem Steuerelement angezeigt wird.  Sie können die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>\-Eigenschaft als `PrintPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] oder `printPreviewDialog1->PrintPreviewControl->Columns` in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] aufrufen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.PrintPreviewDialog>   
 [Übersicht über das PrintPreviewControl\-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)   
 [PrintPreviewDialog\-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [Dialogfeld\-Steuerelemente und \-Komponenten](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)