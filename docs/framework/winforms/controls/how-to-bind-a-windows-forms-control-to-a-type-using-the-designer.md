---
title: 'Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 5069d7d3b5ef4c5b05159dac521d32f5be8abdd1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046046"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ mithilfe des Designers

Beim Erstellen von Steuerelementen, die mit Daten interagieren, ist es manchmal erforderlich, ein Steuerelement an einen Typ statt an ein Objekt zu binden. Sie müssen normalerweise ein Steuerelement zur Entwurfszeit an einen Typ binden, wenn Daten möglicherweise nicht verfügbar sind, aber die datengebundenen Steuerelemente dennoch Daten von der öffentlichen Schnittstelle eines Typs anzeigen sollen. Die folgenden Prozeduren veranschaulichen, wie ein <xref:System.Windows.Forms.BindingSource> neues erstellt wird, das an einen-Typ gebunden ist, und wie eine der-Eigenschaften des Typs <xref:System.Windows.Forms.TextBox.Text%2A> an die- <xref:System.Windows.Forms.TextBox>Eigenschaft eines gebunden wird.

### <a name="to-bind-the-bindingsource-to-a-type"></a>So binden Sie die BindingSource an einen Typen

1. Erstellen eines Windows Forms Projekts ( > Visual**New** > **Project** > **Visual C#**  oderVisual BasicClassic >  Desktop >   **Windows Forms Anwendung**).

2. Ziehen Sie eine <xref:System.Windows.Forms.BindingSource> Komponente in der Entwurfs Ansicht auf das Formular.

3. Klicken Sie im **Eigenschaften** Fenster auf den Pfeil für die <xref:System.Windows.Forms.BindingSource.DataSource%2A> -Eigenschaft.

4. Klicken Sie im **DataSource-UI-Typ-Editor** auf **Projektdatenquelle hinzufügen**.

5. Wählen Sie auf der Seite **Datenquellentyp auswählen** die Option **Objekt** aus, und klicken Sie dann auf **Weiter**.

6. Wählen Sie den Typ aus, an den gebunden werden soll:

    - Wenn sich der Typ, den Sie binden möchten, im aktuellen Projekt befindet oder die Assembly, die den Typ enthält, bereits als Verweis hinzugefügt ist, müssen Sie die Knoten erweitern, um den gewünschten Typ zu suchen. Wählen Sie ihn anschließend aus.

      \- oder -

    - Wenn sich der Typ, den Sie binden möchten, in einer anderen Assembly befindet, die derzeit nicht in der Liste der Verweise erscheint, klicken Sie auf **Verweis hinzufügen** und anschließend auf die Registerkarte **Projekte**. Wählen Sie das Projekt aus, das das gewünschte Geschäftsobjekt enthält, und klicken Sie auf **OK**. Dieses Projekt erscheint in der Liste der Assemblys. Dadurch können Sie die Knoten erweitern, um den gewünschten Typ zu suchen und ihn anschließend auszuwählen.

      > [!NOTE]
      > Deaktivieren Sie das Dialogfeld **Assemblys ausblenden, die mit „Microsoft“ oder „System“ beginnen**, wenn Sie an einen Typen in einem Framework oder einer Microsoft-Assembly binden möchten.

7. Klicken Sie auf **Weiter** und anschließend auf **Fertig stellen**.

### <a name="to-bind-the-control-to-the-bindingsource"></a>So binden Sie das Steuerelement an die BindingSource

1. Fügen Sie dem Formular eine <xref:System.Windows.Forms.TextBox> hinzu.

2. Erweitern Sie im Fenster **Eigenschaften** den Knoten **(DataBindings)** .

3. Klicken Sie auf den Pfeil neben <xref:System.Windows.Forms.TextBox.Text%2A> der-Eigenschaft.

4. Erweitern Sie **im DataSource-Typ-Editor**für die Benutzeroberfläche <xref:System.Windows.Forms.BindingSource> den Knoten für das zuvor hinzugefügte, und wählen Sie die Eigenschaft des gebundenen Typs <xref:System.Windows.Forms.TextBox.Text%2A> aus, die <xref:System.Windows.Forms.TextBox>Sie an die-Eigenschaft des binden möchten.

## <a name="see-also"></a>Siehe auch

- [BindingSource-Komponente](bindingsource-component.md)
- [Vorgehensweise: Binden eines Windows Forms-Steuer Elements an einen Typ](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
