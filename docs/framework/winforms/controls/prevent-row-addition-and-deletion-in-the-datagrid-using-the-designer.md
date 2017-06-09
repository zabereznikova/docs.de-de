---
title: "Gewusst wie: Verhindern des Hinzuf&#252;gens und L&#246;schens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers | Microsoft Docs"
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
  - "DataGridView-Steuerelement [Windows Forms], Verhindern von Hinzufügen oder Löschen von Zeilen"
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Verhindern des Hinzuf&#252;gens und L&#246;schens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Manchmal möchten Sie Benutzer daran hindern, neue Datenzeilen einzugeben oder vorhandene Zeilen im <xref:System.Windows.Forms.DataGridView>\-Steuerelement zu löschen.  Neue Zeilen werden in einer speziellen Zeile für neue Datensätze am unteren Rand des Steuerelements eingegeben.  Wenn Sie das Hinzufügen von Zeilen deaktivieren, wird die Zeile für neue Datensätze nicht angezeigt.  In diesem Fall können Sie das Steuerelement vollständig schreibgeschützt machen, indem Sie das Löschen von Zeilen und Bearbeiten von Zellen deaktivieren.  
  
 Für die folgende Prozedur ist ein **Windows\-Anwendung**\-Projekt mit einem Formular erforderlich, das ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So verhindern Sie das Hinzufügen und Löschen von Zeilen  
  
-   Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) in der oberen rechten Ecke des <xref:System.Windows.Forms.DataGridView>\-Steuerelements, und deaktivieren Sie die Kontrollkästchen **Hinzufügen aktivieren** und **Löschen aktivieren**.  
  
    > [!NOTE]
    >  Um das Steuerelement vollständig schreibgeschützt zu machen, deaktivieren Sie auch das Kontrollkästchen **Bearbeiten aktivieren**.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=fullName>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)