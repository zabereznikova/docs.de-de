---
title: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 2dd3f8bfcad39ca3d530c79a6e6a8170585f7adf
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627954"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Gewusst wie: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Standardmäßig können Benutzer Text-und numerische Daten ändern, die im Windows Forms <xref:System.Windows.Forms.DataGridView>-Steuerelement angezeigt werden. Wenn Sie Daten anzeigen möchten, die nicht für Änderungen vorgesehen sind, müssen Sie die Spalten, die die Daten enthalten, als schreibgeschützt festlegen. Informationen dazu, wie das Steuerelement vollständig schreibgeschützt wird, finden Sie unter Gewusst [wie: verhindern des Hinzufügens und Löschens von Zeilen im Windows Forms DataGridView-Steuerelement mithilfe des Designers](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>So machen Sie eine Spalte mithilfe des Designers als schreibgeschützt

1. Klicken Sie in der oberen rechten Ecke des <xref:System.Windows.Forms.DataGridView>-Steuer Elements auf das Symbol für Designer Aktionen (![kleinen schwarzen Pfeil](./media/designer-actions-glyph.gif)), und wählen Sie dann **Spalten bearbeiten**aus.

2. Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.

3. Legen Sie im Raster **Spalten Eigenschaften** die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>-Eigenschaft auf `true`fest.

    > [!NOTE]
    > Sie können eine Spalte auch als schreibgeschützt festlegen, wenn Sie Sie hinzufügen, **indem Sie im** Dialogfeld **Spalte hinzufügen** das Kontrollkästchen Schreibgeschützt aktivieren.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Gewusst wie: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
