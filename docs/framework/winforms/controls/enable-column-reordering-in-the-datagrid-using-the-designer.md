---
title: 'Vorgehensweise: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 3864ce70f058259b597df904311bd4a48218b151
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040346"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Beim Anzeigen von Daten, die in <xref:System.Windows.Forms.DataGridView> einem Windows Forms-Steuerelement angezeigt werden, möchten Benutzer mitunter die Werte in bestimmten Spalten vergleichen. Dies kann unpraktisch sein, wenn die Spalten im Steuerelement weitgehend getrennt sind, insbesondere, wenn Benutzer einen Bildlauf nach oben und unten durchführen müssen, um alle gewünschten Spalten anzuzeigen. Sie können die Aufgabe des Vergleichs von Spaltenwerten vereinfachen, indem Sie Ihren Benutzern ermöglichen, die Spalten neu zu ordnen. Wenn Sie die Neuanordnung von Spalten aktivieren, können Benutzer eine Spalte an eine neue Position verschieben, indem Sie die Spalten Kopfzeile mit der Maus ziehen.

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.DataGridView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

## <a name="to-enable-column-reordering"></a>So aktivieren Sie die Neuanordnung von Spalten

- Klicken Sie <xref:System.Windows.Forms.DataGridView> in der oberen rechten Ecke des Steuer Elements auf das Smarttagsymbol (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Neuanordnung von Spalten aktivieren**aus.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [Vorgehensweise: Fixieren von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](freeze-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
