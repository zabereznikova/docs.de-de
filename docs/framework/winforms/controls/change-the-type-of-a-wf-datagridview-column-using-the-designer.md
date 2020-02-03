---
title: Ändern des Typs einer DataGridView-Spalte mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 976f257d38dc7be5c904e63da47c61486bd3301c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737136"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Gewusst wie: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers
Manchmal möchten Sie den Typ einer Spalte ändern, die bereits zu einem Windows Forms <xref:System.Windows.Forms.DataGridView>-Steuerelement hinzugefügt wurde. Beispielsweise möchten Sie möglicherweise die Typen einiger Spalten ändern, die automatisch generiert werden, wenn Sie das Steuerelement an eine Datenquelle binden. Dies ist nützlich, wenn in der angezeigten Tabelle Spalten mit Fremdschlüsseln für Zeilen in einer verknüpften Tabelle enthalten sind. In diesem Fall möchten Sie möglicherweise die Text Feld Spalten, in denen diese Fremdschlüssel angezeigt werden, durch Kombinations Feld-Spalten ersetzen, die aussagekräftige Werte aus der verknüpften Tabelle anzeigen.

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein <xref:System.Windows.Forms.DataGridView>-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>So ändern Sie den Typ einer Spalte mithilfe des Designers

1. Klicken Sie in der oberen rechten Ecke![](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")des Steuer Elements <xref:System.Windows.Forms.DataGridView> auf das Smarttagsymbol (Smarttagsymbol), und wählen Sie dann **Spalten bearbeiten**aus.

2. Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.

3. Legen Sie im Raster **Spalten Eigenschaften** die `ColumnType`-Eigenschaft auf den neuen Spaltentyp fest.

    > [!NOTE]
    > Die `ColumnType`-Eigenschaft ist eine reine Entwurfszeit Eigenschaft, die die Klasse angibt, die den Spaltentyp darstellt. Es handelt sich nicht um eine tatsächliche Eigenschaft, die in einer Spalten Klasse definiert ist.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
