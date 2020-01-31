---
title: Erstellen von Master/Detail-Listen mit dem DataGrid-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: 0dea3dd88a8c6c2aceb894789ace8ef3b5c83632
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743385"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Gewusst wie: Erstellen von Master-/Detaillisten mit dem DataGrid-Steuerelement in Windows Forms mithilfe des Designers

> [!NOTE]
> Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

 Wenn die <xref:System.Data.DataSet> eine Reihe verknüpfter Tabellen enthält, können Sie zwei <xref:System.Windows.Forms.DataGrid>-Steuerelemente verwenden, um die Daten in einem Master/Detail-Format anzuzeigen. Eine <xref:System.Windows.Forms.DataGrid> die als Haupt Raster festgelegt ist, und die zweite ist als das Detail Raster festgelegt. Wenn Sie in der Liste Master einen Eintrag auswählen, werden alle zugehörigen untergeordneten Einträge in der Detail Liste angezeigt. Wenn Ihr <xref:System.Data.DataSet> z. b. eine Customers-Tabelle und eine zugehörige Orders-Tabelle enthält, geben Sie die Customers-Tabelle als Haupt Raster und die Orders-Tabelle als Detail Raster an. Wenn ein Kunde aus dem Haupt Raster ausgewählt wird, werden alle Bestellungen, die diesem Kunden in der Tabelle Orders zugeordnet sind, im Detail Raster angezeigt.

 Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt **(Datei** > **Neues** > - **Projekt** >  **C# Visual** oder **Visual Basic** >  > **Anwendung**für den **klassischen Desktop** Windows Forms).

## <a name="to-create-a-master-details-list-in-the-designer"></a>So erstellen Sie eine Master/Details-Liste im Designer

1. Fügen Sie dem Formular zwei <xref:System.Windows.Forms.DataGrid>-Steuerelemente hinzu. Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md). In Visual Studio 2005 ist das <xref:System.Windows.Forms.DataGrid>-Steuerelement nicht standardmäßig in der **Toolbox** . Weitere Informationen finden Sie unter Gewusst [wie: Hinzufügen von Elementen zur Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

    > [!NOTE]
    > Die folgenden Schritte sind nicht auf Visual Studio 2005 anwendbar, das das **Datenquellen** Fenster für die Datenbindung zur Entwurfszeit verwendet. Weitere Informationen finden Sie unter [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) und Gewusst [wie: Anzeigen von verknüpften Daten in einer Windows Forms Anwendung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).

2. Ziehen Sie zwei oder mehr Tabellen aus **Server-Explorer** in das Formular.

3. Wählen Sie im Menü **Daten** die Option **DataSet generieren**aus.

4. Legen Sie die Beziehungen zwischen den Tabellen mit dem XML-Designer fest. Weitere Informationen finden Sie unter "Gewusst wie: Erstellen von 1: n-Beziehungen in XML-Schemas und Datasets" auf der MSDN-Website.

5. Speichern Sie die Beziehungen, indem Sie im Menü **Datei** die Option **Alle speichern** auswählen.

6. Konfigurieren Sie das <xref:System.Windows.Forms.DataGrid> Steuerelement, das Sie für das Master Raster festlegen möchten, wie folgt:

    1. Wählen Sie die <xref:System.Data.DataSet> aus der Dropdown Liste in der <xref:System.Windows.Forms.DataGrid.DataSource%2A>-Eigenschaft aus.

    2. Wählen Sie in der Dropdown Liste in der <xref:System.Windows.Forms.DataGrid.DataMember%2A>-Eigenschaft die Master Tabelle (z. b. "Customers") aus.

7. Konfigurieren Sie das <xref:System.Windows.Forms.DataGrid> Steuerelement, das Sie für das Detail Raster festlegen möchten, wie folgt:

    1. Wählen Sie die <xref:System.Data.DataSet> aus der Dropdown Liste in der <xref:System.Windows.Forms.DataGrid.DataSource%2A>-Eigenschaft aus.

    2. Wählen Sie die Beziehung (z. b. "Customers. CustOrd") zwischen den Master-und Detailtabellen aus der Dropdown Liste in der <xref:System.Windows.Forms.DataGrid.DataMember%2A>-Eigenschaft aus. Um die Beziehung anzuzeigen, erweitern Sie den Knoten, indem Sie auf das Pluszeichen ( **+** ) neben der Master Tabelle in der Dropdown Liste klicken.

## <a name="see-also"></a>Siehe auch

- [DataGrid-Steuerelement](datagrid-control-windows-forms.md)
- [Übersicht über das DataGrid-Steuerelement](datagrid-control-overview-windows-forms.md)
- [Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
