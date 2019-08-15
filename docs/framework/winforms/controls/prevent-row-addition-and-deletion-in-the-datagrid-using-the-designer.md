---
title: 'Vorgehensweise: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: 20f9b85dc48ccd634468d0fed000120723f8ee5c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038188"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Gelegentlich möchten Sie Benutzer daran hindern, neue Zeilen von Daten einzugeben oder vorhandene Zeilen in Ihrem <xref:System.Windows.Forms.DataGridView>-Steuerelement zu löschen. Neue Zeilen werden in der speziellen Zeile für neue Datensätze am unteren Rand des Steuer Elements eingegeben. Wenn Sie die Zeilen Addition deaktivieren, wird die Zeile für neue Datensätze nicht angezeigt. Sie können das Steuerelement dann vollständig schreibgeschützt machen, indem Sie Zeilen Löschung und Zellen Bearbeitung deaktivieren.

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.DataGridView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

## <a name="to-prevent-row-addition-and-deletion"></a>So verhindern Sie das Hinzufügen und Löschen von Zeilen

- <xref:System.Windows.Forms.DataGridView> Klicken Sie in der oberen rechten Ecke des Steuer Elements auf das Smarttagsymbol (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und deaktivieren Sie dann die Kontrollkästchen **hinzufügen aktivieren** und **Löschen aktivieren** .

    > [!NOTE]
    >  Deaktivieren Sie das Kontrollkästchen **Bearbeitung aktivieren** , damit das Steuerelement vollständig schreibgeschützt ist.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
