---
title: 'Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: f98d0e530f502655b9a48819d266a604581d22de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement muss Spalten enthalten, um Daten anzuzeigen. Wenn das Steuerelement manuell gefüllt werden sollen, müssen Sie die Spalten selbst hinzufügen. Klicken Sie Alternativ können Sie das Steuerelement an eine Datenquelle binden, die generiert und füllt die Spalten automatisch. Wenn die Datenquelle mehr Spalten enthält als angezeigt werden soll, können Sie die benötigte Spalten entfernen.  
  
 Erfordern die folgenden Verfahren eine **Windows-Anwendung** Projekt ein Formular mit einem <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-column-using-the-designer"></a>Zum Hinzufügen einer Spalte mithilfe des Designers  
  
1.  Klicken Sie auf das Smarttag-Symbol (![Smart Tag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Add Column**.  
  
2.  In der **Add Column** Dialogfeld Wählen Sie die **datengebundene Spalte** aus, und wählen Sie eine Spalte aus der Datenquelle, oder wählen Sie die **ungebundenen Spalte** aus, und definieren Sie die Spalte verwenden die angezeigten Felder ein.  
  
3.  Klicken Sie auf die **hinzufügen** Schaltfläche zum Hinzufügen der Spalte, die wegen der er im Designer angezeigt wird, wenn die vorhandenen Spalten den Anzeigebereich des Steuerelements nicht bereits aufgefüllt.  
  
    > [!NOTE]
    >  Sie können Spalteneigenschaften im Ändern der **Spalten bearbeiten** (Dialogfeld), die Sie aus dem Smarttag des Steuerelements zugreifen können.  
  
### <a name="to-remove-a-column-using-the-designer"></a>So entfernen Sie eine Spalte mithilfe des Designers  
  
1.  Wählen Sie **Spalten bearbeiten** aus dem Smarttag des Steuerelements.  
  
2.  Wählen Sie eine Spalte aus der **ausgewählte Spalten** Liste.  
  
3.  Klicken Sie auf die **entfernen** Schaltfläche beim Löschen der Spalte, die wegen der er vom Designer nicht mehr angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
