---
title: 'Gewusst wie: Erstellen von Master-/Detaillisten mit dem DataGrid-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: aec02e38fbe80302108397543144b1cc9c3ea346
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837141"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>Gewusst wie: Erstellen von Master-/Detaillisten mit dem DataGrid-Steuerelement in Windows Forms mithilfe des Designers

> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Wenn Ihre <xref:System.Data.DataSet> enthält eine Reihe verknüpfter Tabellen, können Sie mithilfe von zwei <xref:System.Windows.Forms.DataGrid> Steuerelemente zum Anzeigen der Daten in einem Master / Detail-Format. Eine <xref:System.Windows.Forms.DataGrid> als master-Raster, festgelegt und die Sekunde als das Raster festgelegt. Wenn Sie einen Eintrag in der master-Liste auswählen, werden alle zugehörigen untergeordneten Einträge in der Liste angezeigt. Beispielsweise wenn Ihre <xref:System.Data.DataSet> enthält eine Kundentabelle und einer verknüpften Tabelle Orders würden Sie angeben, der Customers-Tabelle der master-Raster sein und die Tabelle Orders, das Detailraster sein. Wenn ein Kunde aus der master-Raster ausgewählt ist, würden alle Bestellungen dieses Kunden in der Orders-Tabelle zugeordnet im Raster angezeigt werden.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms Anwendung**).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>Zum Erstellen einer Master / Detail-Liste im designer  
  
1.  Hinzufügen von zwei <xref:System.Windows.Forms.DataGrid> Steuerelemente im Formular. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). In Visual Studio 2005 die <xref:System.Windows.Forms.DataGrid> Steuerelement befindet sich nicht in der **Toolbox** standardmäßig. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Elementen zur Toolbox](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
    > [!NOTE]
    >  Die folgenden Schritte gelten nicht für Visual Studio 2005 verwendet die **Datenquellen** Fenster für die Datenbindung zur Entwurfszeit. Weitere Informationen finden Sie unter [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) und [Vorgehensweise: Anzeigen von verknüpften Daten in einer Windows Forms-Anwendung](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
2.  Ziehen Sie zwei oder mehr Tabellen aus **Server-Explorer** auf das Formular.  
  
3.  Von der **Daten** , wählen Sie im Menü **DataSet generieren**.  
  
4.  Legen Sie die Beziehungen zwischen den Tabellen, die mit dem XML-Designer. Weitere Informationen finden Sie unter "Vorgehensweise: Erstellen von 1: N Beziehungen in XML-Schemas und Datasets" auf MSDN.  
  
5.  Speichern Sie die Beziehungen durch Auswählen von **Alles speichern** aus der **Datei** Menü.  
  
6.  Konfigurieren der <xref:System.Windows.Forms.DataGrid> -Steuerelement, das Sie die master-Raster, wie folgt festlegen möchten:  
  
    1.  Wählen Sie die <xref:System.Data.DataSet> aus der Dropdown-Liste in der <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft.  
  
    2.  Wählen Sie die master-Tabelle (z. B. "Customers") aus der Dropdown-Liste in der <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaft.  
  
7.  Konfigurieren der <xref:System.Windows.Forms.DataGrid> -Steuerelement, das Sie im Detailraster wie folgt festlegen möchten:  
  
    1.  Wählen Sie die <xref:System.Data.DataSet> aus der Dropdown-Liste in der <xref:System.Windows.Forms.DataGrid.DataSource%2A> Eigenschaft.  
  
    2.  Wählen Sie die Beziehung (z. B. "Customers.CustOrd") zwischen den Master- und Tabellen aus der Dropdown-Liste in der <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaft. Um die Beziehung anzuzeigen, erweitern Sie den Knoten durch Klicken auf das Pluszeichen (**+**) neben der master-Tabelle in der Dropdown-Liste.  
  
## <a name="see-also"></a>Siehe auch  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Übersicht über das DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [Binden von Steuerelementen an Daten in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
