---
title: 'Vorgehensweise: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 6bdd561c863a461f43a5a7aac025fead1f971bb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039812"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Standardmäßig können Benutzer im Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement angezeigte Text-und numerische Daten ändern. Wenn Sie Daten anzeigen möchten, die nicht für Änderungen vorgesehen sind, müssen Sie die Spalten, die die Daten enthalten, als schreibgeschützt festlegen. Informationen dazu, wie das Steuerelement vollständig schreibgeschützt wird, finden [Sie unter Gewusst wie: Verhindern Sie das Hinzufügen und Löschen von Zeilen im Windows Forms DataGridView-](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)Steuerelement mithilfe des Designers.

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.DataGridView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

## <a name="to-make-a-column-read-only-by-using-the-designer"></a>So machen Sie eine Spalte mithilfe des Designers als schreibgeschützt

1. Klicken Sie in der <xref:System.Windows.Forms.DataGridView> oberen rechten Ecke des Steuer Elements auf das Smarttagsymbol (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Spalten bearbeiten**aus.

2. Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.

3. Legen Sie im Raster **Spalten Eigenschaften** die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> -Eigenschaft auf `true`fest.

    > [!NOTE]
    >  Sie können eine Spalte auch als schreibgeschützt festlegen, wenn Sie Sie hinzufügen, indem Sie im Dialogfeld **Spalte hinzufügen** das Kontrollkästchen Schreibgeschützt aktivieren.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Vorgehensweise: Hinzufügen und Entfernen von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Verhindern der Addition und Löschung von Zeilen im Windows Forms DataGridView-Steuerelement mithilfe des Designers](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
