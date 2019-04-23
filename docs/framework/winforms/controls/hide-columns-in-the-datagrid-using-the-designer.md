---
title: 'Vorgehensweise: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: aa81eb7470b818fa2b65200503e5ce65b467c0f2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324447"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Manchmal möchten Sie nur einige der Spalten anzeigen, die in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement in Windows Forms verfügbar sind. Sie möchten z. B. einen Mitarbeiter anzeigen Gehalt-Spalte, die Benutzern mit Verwaltungsanmeldeinformationen, die sie andere Benutzer ausblenden. Klicken Sie Alternativ sollten Sie das Steuerelement an eine Datenquelle zu binden, die viele Spalten enthält, von denen nur einige angezeigt werden soll. In diesem Fall werden Sie in der Regel die Spalten entfernen, die Sie nicht anzeigen, anstatt sie verbergen möchten. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen und Entfernen von Spalten in der Windows Forms DataGridView-Steuerelement mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md).  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-hide-a-column-using-the-designer"></a>Zum Ausblenden einer Spalte mithilfe des Designers  
  
1. Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) auf der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Spalten bearbeiten**.  
  
2. Wählen Sie eine Spalte aus der **Selected Columns** Liste.  
  
3. In der **Spalteneigenschaften** Raster legen die <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> Eigenschaft `false`.  
  
    > [!NOTE]
    >  Sie können auch eine Spalte ausblenden, wenn Sie es deaktivieren Hinzufügen der **Visible** Kontrollkästchen in der **Spalte hinzufügen** Dialogfeld.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Vorgehensweise: Hinzufügen und Entfernen von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
