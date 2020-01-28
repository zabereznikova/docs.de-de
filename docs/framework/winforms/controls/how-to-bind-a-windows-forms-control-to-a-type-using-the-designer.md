---
title: Binden des Steuer Elements an einen Typ mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 2257489e123ceeea819ad3538952db51b726c7e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742027"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ mithilfe des Designers

Beim Erstellen von Steuerelementen, die mit Daten interagieren, ist es manchmal erforderlich, ein Steuerelement an einen Typ statt an ein Objekt zu binden. Sie müssen normalerweise ein Steuerelement zur Entwurfszeit an einen Typ binden, wenn Daten möglicherweise nicht verfügbar sind, aber die datengebundenen Steuerelemente dennoch Daten von der öffentlichen Schnittstelle eines Typs anzeigen sollen. Die folgenden Prozeduren veranschaulichen, wie Sie eine neue <xref:System.Windows.Forms.BindingSource> erstellen, die an einen-Typ gebunden ist, und wie Sie dann eine der Eigenschaften des Typs an die <xref:System.Windows.Forms.TextBox.Text%2A>-Eigenschaft eines <xref:System.Windows.Forms.TextBox>binden.

### <a name="to-bind-the-bindingsource-to-a-type"></a>So binden Sie die BindingSource an einen Typen

1. Erstellen Sie ein Windows Forms Projekt **(Datei** > **neuen** > **Projekt** > **Visual C#**  oder **Visual Basic** >  > **Anwendung**für **klassische Desktops** ).

2. Ziehen Sie in der **Entwurfs** Ansicht eine <xref:System.Windows.Forms.BindingSource> Komponente auf das Formular.

3. Klicken Sie im **Eigenschaften** Fenster auf den Pfeil für die <xref:System.Windows.Forms.BindingSource.DataSource%2A>-Eigenschaft.

4. Klicken Sie im **DataSource-UI-Typ-Editor** auf **Projektdatenquelle hinzufügen**.

5. Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Objekt** aus, und klicken Sie dann auf **Weiter**.

6. Wählen Sie den Typ aus, an den gebunden werden soll:

    - Wenn sich der Typ, den Sie binden möchten, im aktuellen Projekt befindet oder die Assembly, die den Typ enthält, bereits als Verweis hinzugefügt ist, müssen Sie die Knoten erweitern, um den gewünschten Typ zu suchen. Wählen Sie ihn anschließend aus.

      \- oder -

    - Wenn sich der Typ, an den Sie binden möchten, in einer anderen Assembly befindet, die derzeit nicht in der Liste der Verweise enthalten ist, klicken Sie auf **Verweis hinzufügen**, **und klicken Sie**dann auf die Registerkarte **Projekte** . Wählen Sie das Projekt mit dem gewünschten Geschäftsobjekt aus, und klicken Sie Dieses Projekt erscheint in der Liste der Assemblys. Dadurch können Sie die Knoten erweitern, um den gewünschten Typ zu suchen und ihn anschließend auszuwählen.

      > [!NOTE]
      > Deaktivieren Sie das Dialogfeld **Assemblys ausblenden, die mit „Microsoft“ oder „System“ beginnen**, wenn Sie an einen Typen in einem Framework oder einer Microsoft-Assembly binden möchten.

7. Klicken Sie auf **Weiter** und anschließend auf **Fertig stellen**.

### <a name="to-bind-the-control-to-the-bindingsource"></a>So binden Sie das Steuerelement an die BindingSource

1. Fügen Sie dem Formular eine <xref:System.Windows.Forms.TextBox> hinzu.

2. Erweitern Sie im Fenster **Eigenschaften** den Knoten **(DataBindings)** .

3. Klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A>-Eigenschaft.

4. Erweitern Sie im **DataSource-Typ-Editor für die Benutzeroberfläche**den Knoten für die <xref:System.Windows.Forms.BindingSource>, die Sie zuvor hinzugefügt haben, und wählen Sie die Eigenschaft des gebundenen Typs aus, die Sie an die <xref:System.Windows.Forms.TextBox.Text%2A>-Eigenschaft der <xref:System.Windows.Forms.TextBox>binden möchten.

## <a name="see-also"></a>Siehe auch

- [BindingSource-Komponente](bindingsource-component.md)
- [Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
