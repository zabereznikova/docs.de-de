---
title: "Gewusst wie: Festlegen von abwechselnden Zeilenstilen f&#252;r das Windows Forms-Steuerelement DataGridView mithilfe des Designers | Microsoft Docs"
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
  - "Daten [Windows Forms], Anzeigen"
  - "DataGridView-Steuerelement [Windows Forms], Zeilenstilwechsel"
  - "Ledger-Formate"
  - "Zeilen, Abwechselnde"
  - "Windows Forms, Zeilen"
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Festlegen von abwechselnden Zeilenstilen f&#252;r das Windows Forms-Steuerelement DataGridView mithilfe des Designers
Tabellendaten werden oft in einem Ledger\-ähnlichen Format präsentiert, bei dem die einzelnen Zeilen abwechselnde Hintergrundfarben haben.  Dieses Format erleichtert es dem Benutzer, zu erkennen, welche Zellen sich in einer Zeile befinden, insbesondere bei breiten Tabellen mit vielen Spalten.  
  
 Mit dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement können Sie vollständige Stilinformationen für abwechselnde Zeilen festlegen.  Außer mit der Hintergrundfarbe können Sie auch mit Stilmerkmalen wie Vordergrundfarbe und Schriftart abwechselnde Zeilen unterscheiden.  Weitere Informationen finden Sie unter [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Für die folgende Prozedur ist ein **Windows\-Anwendung**\-Projekt mit einem Formular erforderlich, das ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Definieren von Stilen für abwechselnde Zeilen  
  
1.  Wählen Sie das <xref:System.Windows.Forms.DataGridView>\-Steuerelement im Designer aus.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf die Schaltfläche mit den Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) neben der <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>\-Eigenschaft.  
  
3.  Definieren Sie im Dialogfeld **CellStyle\-Generator** den Stil, indem Sie die Eigenschaften festlegen, und bestätigen Sie mit dem Bereich **Vorschau** Ihre Auswahl.  Die festgelegten Stile werden für jede zweite Zeile im Steuerelement verwendet, beginnend mit der zweiten Zeile.  
  
4.  Um Stile für die übrigen Zeilen zu definieren, wiederholen Sie die Schritte 2 und 3 mit der <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>\-Eigenschaft.  
  
    > [!NOTE]
    >  Zellen werden mit Stilen angezeigt, die von mehreren Eigenschaften geerbt wurden.  Weitere Informationen über Stilvererbung finden Sie unter [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [Zellstile im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Grundlegende Formatierungen und Formate im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Verwenden des Designers mit dem DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/using-the-designer-with-the-windows-forms-datagridview-control.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)