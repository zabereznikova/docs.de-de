---
title: "Gewusst wie: &#196;ndern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers | Microsoft Docs"
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
  - "Spalten [Windows Forms], Typen"
  - "Daten [Windows Forms], Anzeigen"
  - "DataGridView-Steuerelement [Windows Forms], Ändern des Spaltentyps"
  - "Windows Forms, Spalten"
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: &#196;ndern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers
Gelegentlich müssen Sie den Typ einer Spalte ändern, die bereits einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement in Windows Forms hinzugefügt wurde.  Beispielsweise möchten Sie die Typen einiger Spalten ändern, die automatisch generiert werden, wenn Sie das Steuerelement an eine Datenquelle binden.  Dies ist besonders hilfreich, wenn die Tabelle über Spalten verfügt, die Fremdschlüssel für Zeilen in einer zugehörigen Tabelle enthält.  In diesem Fall sollten Sie die Spalten mit den Textfeldern, in denen diese Fremdschlüssel angezeigt werden, durch Spalten mit Kombinationsfeldern ersetzen, die aussagekräftigere Werte aus der zugehörigen Tabelle anzeigen.  
  
 Für die folgende Prozedur ist ein **Windows\-Anwendung**\-Projekt mit einem Formular erforderlich, das ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So ändern Sie den Typ einer Spalte mithilfe des Designers  
  
1.  Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) in der oberen rechten Ecke des <xref:System.Windows.Forms.DataGridView>\-Steuerelements, und wählen Sie dann **Spalten bearbeiten** aus.  
  
2.  Wählen Sie eine Spalte aus der Liste **Ausgewählte Spalten** aus.  
  
3.  Legen Sie im Raster **Spalteneigenschaften** die `ColumnType`\-Eigenschaft auf den neuen Spaltentyp fest.  
  
    > [!NOTE]
    >  Die `ColumnType`\-Eigenschaft ist eine nur zur Entwurfszeit gültige Eigenschaft, die die Klasse angibt, die den Spaltentyp darstellt.  Sie ist keine eigentliche in einer Spaltenklasse definierte Eigenschaft.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)