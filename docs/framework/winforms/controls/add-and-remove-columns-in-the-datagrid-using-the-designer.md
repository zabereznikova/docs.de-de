---
title: 'Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 99fe1b8ffb7ccc2a5bef13ea8fef6ace5d5bdfdc
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43452806"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Gewusst wie: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Die Windows-Formulare <xref:System.Windows.Forms.DataGridView> Steuerelement muss Spalten enthalten, um Daten anzuzeigen. Wenn Sie das Steuerelement manuell auffüllen möchten, müssen Sie die Spalten selbst hinzufügen. Alternativ können Sie das Steuerelement an eine Datenquelle binden generiert und füllt die Spalten automatisch. Wenn die Datenquelle mehr Spalten enthält als angezeigt werden soll, können Sie die gewünschten Spalten entfernen.  
  
 Benötigen Sie die folgenden Verfahren eine **Windows-Anwendung** Projekt ein Formular mit einer <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-column-using-the-designer"></a>Hinzufügen eine Spalte mithilfe des Designers  
  
1.  Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) auf der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Add Column**.  
  
2.  In der **Spalte hinzufügen** Dialogfeld auf die **datengebundene Spalte** option aus, und wählen Sie eine Spalte aus der Datenquelle, oder wählen die **ungebundenen Spalte** aus, und definieren Sie die Spalte verwenden die angezeigten Felder ein.  
  
3.  Klicken Sie auf die **hinzufügen** , um die Spalte im Designer angezeigt werden, wenn die vorhandenen Spalten den Anzeigebereich des Steuerelements nicht bereits ausfüllen hinzuzufügen.  
  
    > [!NOTE]
    >  Sie können Spalteneigenschaften im Ändern der **Spalten bearbeiten** Dialogfeld, das Sie von smart Tag des Steuerelements zugreifen können.  
  
### <a name="to-remove-a-column-using-the-designer"></a>So entfernen Sie eine Spalte, die mithilfe des Designers  
  
1.  Wählen Sie **Spalten bearbeiten** von smart Tag des Steuerelements.  
  
2.  Wählen Sie eine Spalte aus der **Selected Columns** Liste.  
  
3.  Klicken Sie auf die **entfernen** Schaltfläche, um die Spalte, und vom Designer zu löschen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 [Vorgehensweise: Erstellen eines Windows-Anwendungsprojekts](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
