---
title: "Gewusst wie: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers | Microsoft Docs"
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
  - "Spalten [Windows Forms], Ausblenden"
  - "Daten [Windows Forms], Anzeigen"
  - "DataGridView-Steuerelement [Windows Forms], Spalten ausblenden"
  - "Windows Forms, Spalten"
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Manchmal möchten Sie nur einige der Spalten anzeigen, die in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement in Windows Forms verfügbar sind.  Beispielsweise möchten Sie Benutzern, die sich mit Anmeldeinformationen der Geschäftsführung anmelden, eine Spalte mit den Gehältern der Angestellten anzeigen, diese aber für andere Benutzer ausblenden.  Oder aber Sie möchten das Steuerelement an eine Datenquelle binden, die viele Spalten enthält, von denen Sie nur einige anzeigen möchten.  In diesem Fall entfernen Sie die Spalten, deren Anzeige Sie nicht interessiert, anstatt sie auszublenden.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md).  
  
 Für die folgende Prozedur ist ein **Windows\-Anwendung**\-Projekt mit einem Formular erforderlich, das ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So blenden Sie eine Spalte mithilfe des Designers aus  
  
1.  Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) in der oberen rechten Ecke des <xref:System.Windows.Forms.DataGridView>\-Steuerelements, und wählen Sie dann **Spalten bearbeiten** aus.  
  
2.  Wählen Sie eine Spalte aus der Liste **Ausgewählte Spalten** aus.  
  
3.  Legen Sie im Raster **Spalteneigenschaften** die <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>\-Eigenschaft auf `false` fest.  
  
    > [!NOTE]
    >  Sie können eine Spalte auch beim Hinzufügen ausblenden, indem Sie das Kontrollkästchen **Sichtbar** im Dialogfeld **Spalte hinzufügen** deaktivieren.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView\-Steuerelement in Windows Forms mithilfe des Designers](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)