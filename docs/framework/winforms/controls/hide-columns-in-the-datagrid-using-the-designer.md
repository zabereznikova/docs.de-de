---
title: Ausblenden von Spalten im DataGridView-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 3c9a6bdeacbeb5929488e6af0054403db73c4239
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738653"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Gewusst wie: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Manchmal möchten Sie nur einige der Spalten anzeigen, die in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement in Windows Forms verfügbar sind. Beispielsweise können Sie Benutzern mit Verwaltungs Anmelde Informationen eine Employee-Gehalts Spalte anzeigen, während Sie Sie von anderen Benutzern ausblenden. Alternativ können Sie das Steuerelement an eine Datenquelle binden, die viele Spalten enthält, von denen Sie nur einige Spalten anzeigen möchten. In diesem Fall werden Sie in der Regel die Spalten entfernen, die Sie nicht anzeigen möchten, anstatt Sie zu verbergen. Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen und Entfernen von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md).

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-hide-a-column-using-the-designer"></a>So blenden Sie eine Spalte mithilfe des Designers aus

1. Klicken Sie in der oberen rechten Ecke![](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")des Steuer Elements <xref:System.Windows.Forms.DataGridView> auf das Smarttagsymbol (Smarttagsymbol), und wählen Sie dann **Spalten bearbeiten**aus.

2. Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.

3. Legen Sie im Raster **Spalten Eigenschaften** die <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A>-Eigenschaft auf `false`fest.

    > [!NOTE]
    > Sie können eine Spalte auch beim Hinzufügen ausblenden, indem Sie im Dialogfeld **Spalte hinzufügen** das Kontrollkästchen **sichtbar** deaktivieren.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
