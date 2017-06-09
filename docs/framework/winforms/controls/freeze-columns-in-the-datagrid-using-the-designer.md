---
title: "Gewusst wie: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers | Microsoft Docs"
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
  - "Spalten [Windows Forms], Fixieren"
  - "Daten [Windows Forms], Anzeigen"
  - "DataGridView-Steuerelement [Windows Forms], Spaltenfixierung"
  - "Windows Forms, Spalten"
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Wenn Benutzer Daten in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement in Windows Forms anzeigen, müssen sie in manchen Fällen auf eine einzelne Spalte oder Gruppe von Spalten zugreifen.  Wenn Sie beispielsweise eine Tabelle mit Kundendaten anzeigen, die viele Spalten enthält, ist es hilfreich, wenn die Namen der Kunden immer angezeigt werden, während andere Spalten außerhalb des sichtbaren Bereichs liegen.  
  
 Zu diesem Zweck können Sie Spalten im Steuerelement fixieren.  Wenn Sie eine Spalte fixieren, werden automatisch auch alle Spalten links daneben \(bzw. rechts daneben in von rechts nach links geschriebenen Sprachen\) fixiert.  Fixierte Spalten behalten ihre Position bei, während alle anderen Spalten bei einem Bildlauf mitwandern.  Wenn die Neuanordnung von Spalten aktiviert ist, werden die fixierten Spalten als eine von den nicht fixierten Spalten unterschiedene Gruppe behandelt.  Benutzer können Spalten in beiden Gruppen neu positionieren, jedoch keine Spalte aus einer Gruppe in die andere verschieben.  
  
 Für die folgende Prozedur ist ein **Windows\-Anwendung**\-Projekt mit einem Formular erforderlich, das ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fixieren Sie eine Spalte mithilfe des Designers  
  
1.  Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) in der oberen rechten Ecke des <xref:System.Windows.Forms.DataGridView>\-Steuerelements, und wählen Sie dann **Spalten bearbeiten** aus.  
  
2.  Wählen Sie eine Spalte aus der Liste **Ausgewählte Spalten** aus.  
  
3.  Legen Sie im Raster **Spalteneigenschaften** die <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A>\-Eigenschaft auf `true` fest.  
  
    > [!NOTE]
    >  Sie können eine Spalte auch beim Hinzufügen fixieren, indem Sie im Dialogfeld **Spalte hinzufügen** das Feld **Fixiert** auswählen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName>   
 [Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [Gewusst wie: Aktivieren der Neuanordnung von Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)   
 [How to: Display Right\-to\-Left Text in Windows Forms for Globalization](http://msdn.microsoft.com/de-de/f0663385-2354-4c65-8676-706422283b14)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)