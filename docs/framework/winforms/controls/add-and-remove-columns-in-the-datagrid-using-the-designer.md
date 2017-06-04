---
title: "Gewusst wie: Hinzuf&#252;gen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.DataGridViewAddColumnDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView-Steuerelement [Windows Forms], Hinzufügen von Spalten"
  - "DataGridView-Steuerelement [Windows Forms], Entfernen von Spalten"
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Hinzuf&#252;gen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement in Windows Forms muss Spalten enthalten, damit Daten angezeigt werden.  Wenn Sie das Steuerelement manuell füllen möchten, müssen Sie die Spalten selbst hinzufügen.  Wahlweise können Sie das Steuerelement an eine Datenquelle binden, die die Spalten generiert und automatisch füllt.  Wenn die Datenquelle mehr Spalten enthält, als Sie anzeigen möchten, können Sie die unerwünschten Spalten entfernen.  
  
 Für die folgenden Prozeduren ist ein **Windows\-Anwendung**\-Projekt mit einem Formular erforderlich, das ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie eine Spalte mithilfe des Designers hinzu  
  
1.  Klicken Sie auf das Smarttagsymbol \(![Smarttag&#45;Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) in der oberen rechten Ecke des <xref:System.Windows.Forms.DataGridView>\-Steuerelements, und wählen Sie dann **Spalte hinzufügen** aus.  
  
2.  Wählen Sie im Dialogfeld **Spalte hinzufügen** die Option **Datengebundene Spalte** aus, und markieren Sie eine Spalte aus der Datenquelle, oder wählen Sie die Option **Ungebundene Spalte**, und definieren Sie die Spalte anhand der bereitgestellten Felder.  
  
3.  Klicken Sie auf die Schaltfläche **Hinzufügen**, um die Spalte hinzuzufügen. Sofern die vorhandenen Spalten den Anzeigebereich des Steuerelements noch nicht füllen, wird sie im Designer angezeigt.  
  
    > [!NOTE]
    >  Sie können Spalteneigenschaften im Dialogfeld **Spalten bearbeiten** anpassen. Dieses wird über das Smarttag des Steuerelements aufgerufen.  
  
### So entfernen Sie eine Spalte mithilfe des Designers  
  
1.  Wählen Sie aus dem Smarttag des Steuerelements **Spalten bearbeiten** aus.  
  
2.  Wählen Sie eine Spalte aus der Liste **Ausgewählte Spalten** aus.  
  
3.  Klicken Sie auf die Schaltfläche **Entfernen**, um die Spalte zu löschen und aus dem Designer zu entfernen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)