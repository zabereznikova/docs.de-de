---
title: 'Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: e0b0b01a3c6da0680a3ec5fcd591344e04658a37
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917618"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers
Manchmal möchten Sie den Typ einer Spalte ändern, die bereits zu einem Windows Forms <xref:System.Windows.Forms.DataGridView> -Steuerelement hinzugefügt wurde. Beispielsweise möchten Sie möglicherweise die Typen einiger Spalten ändern, die automatisch generiert werden, wenn Sie das Steuerelement an eine Datenquelle binden. Dies ist nützlich, wenn in der angezeigten Tabelle Spalten mit Fremdschlüsseln für Zeilen in einer verknüpften Tabelle enthalten sind. In diesem Fall möchten Sie möglicherweise die Text Feld Spalten, in denen diese Fremdschlüssel angezeigt werden, durch Kombinations Feld-Spalten ersetzen, die aussagekräftige Werte aus der verknüpften Tabelle anzeigen.

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.DataGridView> das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

### <a name="to-change-the-type-of-a-column-using-the-designer"></a>So ändern Sie den Typ einer Spalte mithilfe des Designers

1. Klicken Sie in der <xref:System.Windows.Forms.DataGridView> oberen rechten Ecke des Steuer Elements auf das Smarttagsymbol (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Spalten bearbeiten**aus.

2. Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.

3. Legen Sie im Raster **Spalten Eigenschaften** die `ColumnType` -Eigenschaft auf den neuen Spaltentyp fest.

    > [!NOTE]
    > Die `ColumnType` -Eigenschaft ist eine reine Entwurfszeit Eigenschaft, die die Klasse angibt, die den Spaltentyp darstellt. Es handelt sich nicht um eine tatsächliche Eigenschaft, die in einer Spalten Klasse definiert ist.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
