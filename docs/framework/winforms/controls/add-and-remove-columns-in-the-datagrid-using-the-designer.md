---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 7a3029192ab0da4a954dfd7d3d258a00b154924e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957114"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers
Das Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement muss Spalten enthalten, um Daten anzeigen zu können. Wenn Sie das Steuerelement manuell auffüllen möchten, müssen Sie die Spalten selbst hinzufügen. Alternativ können Sie das Steuerelement an eine Datenquelle binden, die die Spalten automatisch generiert und auffüllt. Wenn die Datenquelle mehr Spalten enthält, als Sie anzeigen möchten, können Sie die unerwünschten Spalten entfernen.

 Die folgenden Prozeduren erfordern ein **Windows-Anwendungs** Projekt mit einem <xref:System.Windows.Forms.DataGridView> Formular, das ein-Steuerelement enthält. Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.

## <a name="to-add-a-column-using-the-designer"></a>So fügen Sie eine Spalte mithilfe des Designers hinzu

1. Klicken Sie <xref:System.Windows.Forms.DataGridView> in der oberen rechten Ecke des Steuer Elements auf das Smarttagsymbol (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), und wählen Sie dann **Spalte hinzufügen**aus.

2. Wählen Sie im Dialogfeld **Spalte hinzufügen** die Option **Daten gebundene Spalte** aus, und wählen Sie eine Spalte aus der Datenquelle aus, oder wählen Sie die Option **ungebundene Spalte** aus, und definieren Sie die Spalte mithilfe der angegebenen Felder.

3. Klicken Sie auf die Schaltfläche **Hinzufügen** , um die Spalte hinzuzufügen. Dies bewirkt, dass Sie im Designer angezeigt wird, wenn die vorhandenen Spalten den Anzeigebereich des Steuer Elements nicht bereits ausfüllen.

    > [!NOTE]
    > Sie können Spalten Eigenschaften im Dialogfeld **Spalten bearbeiten** ändern, auf das Sie über das Smarttag des Steuer Elements zugreifen können.

## <a name="to-remove-a-column-using-the-designer"></a>So entfernen Sie eine Spalte mithilfe des Designers

1. Wählen Sie Spalten aus dem Smarttag des-Steuer Elements **Bearbeiten** aus.

2. Wählen Sie in der Liste **Ausgewählte Spalten** eine Spalte aus.

3. Klicken Sie auf die Schaltfläche **Entfernen** , um die Spalte zu löschen, sodass Sie nicht mehr im Designer angezeigt wird.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
