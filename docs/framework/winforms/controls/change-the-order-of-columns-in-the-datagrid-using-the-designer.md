---
title: 'Vorgehensweise: Ändern der Reihenfolge von Spalten des DataGridView-Steuerelements in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: bf77cf3705a470bbe00be383f6a5cb2d28bda34d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039636"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Ändern der Reihenfolge von Spalten des DataGridView-Steuerelements in Windows Forms mithilfe des Designers

Wenn Sie ein Windows Forms <xref:System.Windows.Forms.DataGridView> -Steuerelement an eine Datenquelle binden, wird die Anzeigereihenfolge der automatisch generierten Spalten von der Datenquelle vorgegeben. Wenn Sie diese Reihenfolge nicht bevorzugen, können Sie die Reihenfolge der Spalten mithilfe des Designers ändern. Möglicherweise möchten Sie auch ungebundene Spalten zum Steuerelement hinzufügen und die Anzeigereihenfolge ändern. Informationen zum programmgesteuerten Ändern der Spaltenreihenfolge finden [Sie unter Gewusst wie: Ändern Sie die Reihenfolge der Spalten im Windows Forms DataGridView](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)-Steuerelement.

Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.DataGridView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

## <a name="to-change-the-column-order-using-the-designer"></a>So ändern Sie die Spaltenreihenfolge mithilfe des Designers

1. Klicken Sie in der <xref:System.Windows.Forms.DataGridView> oberen rechten Ecke des Steuer Elements auf das Smarttagsymbol (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Spalten bearbeiten**aus.

2. Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.

3. Klicken Sie auf den nach-oben-oder nach-unten-Pfeil rechts neben der Liste **Ausgewählte Spalten** , bis sich die ausgewählte Spalte an der gewünschten Position befindet.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [Vorgehensweise: Hinzufügen und Entfernen von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
