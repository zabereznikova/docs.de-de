---
title: "&#220;bersicht &#252;ber die PrintDocument-Komponente (Windows&#160;Forms) | Microsoft Docs"
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
  - "PrintDocument"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "PrintDocument-Komponente [Windows Forms], Informationen über die PrintDocument-Komponente"
  - "Drucken [Windows Forms], PrintDocument-Komponente"
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# &#220;bersicht &#252;ber die PrintDocument-Komponente (Windows&#160;Forms)
Die [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)\-Komponente in Windows Forms wird verwendet, um die Eigenschaften der zu druckenden Elemente festzulegen und das Dokument anschließend innerhalb von Windows\-Anwendungen zu drucken.  Sie kann in Verbindung mit der [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)\-Komponente verwendet werden, um alle Aspekte zu steuern, die mit dem Drucken von Dokumenten zusammenhängen.  
  
## Arbeiten mit der PrintDocument\-Komponente  
 Die beiden Hauptszenarien für die <xref:System.Drawing.Printing.PrintDocument>\-Komponente sind folgende:  
  
-   Einfache Druckaufträge, z. B. das Drucken einer einzelnen Textdatei.  In einem solchen Fall würden Sie die <xref:System.Drawing.Printing.PrintDocument>\-Komponente in ein Windows Form einfügen und dann eine Programmierlogik hinzufügen, die eine Datei im <xref:System.Drawing.Printing.PrintDocument.PrintPage>\-Ereignishandler ausgibt.  Die Programmierlogik muss zum Drucken des Dokuments mit der <xref:System.Drawing.Printing.PrintDocument.Print%2A>\-Methode zusammenwirken.  Diese Methode sendet ein <xref:System.Drawing.Graphics>\-Objekt an den Drucker, das in der <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>\-Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs>\-Klasse enthalten ist.  Ein Beispiel, das veranschaulicht, wie ein Textdokument mit der <xref:System.Drawing.Printing.PrintDocument>\-Komponente gedruckt wird, finden Sie unter [Gewusst wie: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).  
  
-   Komplexere Druckaufträge, wenn Sie z. B. die geschriebene Drucklogik wiederverwenden möchten.  In einem solchen Fall würden Sie eine neue Komponente von der <xref:System.Drawing.Printing.PrintDocument>\-Komponente ableiten und das <xref:System.Drawing.Printing.PrintDocument.PrintPage>\-Ereignis überschreiben \(siehe [Overrides](../Topic/Overrides%20\(Visual%20Basic\).md) für Visual Basic oder [override](../Topic/override%20\(C%23%20Reference\).md) für C\#\).  
  
 Nachdem die <xref:System.Drawing.Printing.PrintDocument>\-Komponente einem Formular hinzugefügt wurde, wird sie auf der Komponentenleiste am unteren Rand des Windows Forms\-Designers angezeigt.  
  
## Siehe auch  
 <xref:System.Drawing.Graphics>   
 <xref:System.Drawing.Printing.PrintDocument>   
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [PrintDocument\-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)