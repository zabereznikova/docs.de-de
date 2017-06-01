---
title: "Gewusst wie: Anzeigen der PrintDialog-Komponente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Drucken (Dialogfeld), Anzeigen"
  - "PrintDialog-Komponente [Windows Forms], Anzeigen"
  - "Drucken [Windows Forms], Anzeigen des Dialogfelds Drucken"
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Anzeigen der PrintDialog-Komponente
Die <xref:System.Windows.Forms.PrintDialog>\-Komponente ist das standardmäßige Druckdialogfeld in Windows, das den meisten Benutzern vertraut ist.  Da Benutzer sich darin sofort zurechtfinden werden, ist die Verwendung der <xref:System.Windows.Forms.PrintDialog>\-Komponente zu empfehlen.  
  
### So zeigen Sie die PrintDialog\-Komponente an  
  
-   Rufen Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A>\-Methode im Code der Anwendung auf.  
  
     Wenn die Komponente angezeigt wird, können die Benutzer damit interagieren und die Eigenschaften für den Druckauftrag einstellen.  Diese werden in der mit dem Druckauftrag verknüpften [PrinterSettings](frlrfSystemDrawingPrintingPrinterSettingsMembersTopic)\-Klasse gespeichert \(sowie in der [PageSettings](frlrfSystemDrawingPrintingPageSettingsMembersTopic)\-Klasse, wenn der Benutzer über die <xref:System.Windows.Forms.PrintDialog>\-Komponente auf [PageSetupDialog\-Komponente](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) zugreift\).  Dann können Sie Aufrufe an die von ihnen eingestellten Eigenschaften durchführen, um die spezifischen Merkmale des Druckauftrags anzugeben.  
  
## Siehe auch  
 [Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)   
 [Gewusst wie: Erfassen von Benutzereingaben in einem "PrintDialog" zur Laufzeit](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)   
 [PrintPreviewDialog\-Steuerelement](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [PrintDialog\-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)   
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)