---
title: "&#220;bersicht &#252;ber das DataGrid-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DataGrid"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Datasets [Windows Forms], binden an DataGrid-Steuerelement"
  - "die Datenbindung, DataGrid-Steuerelement"
  - "Spalten [Windows Forms], DataGrid-Steuerelement"
  - "Datenquellen, binden an DataGrid-Steuerelement"
  - "Tabellen [Windows Forms], binden an DataGrid-Steuerelement"
  - "DataGrid-Steuerelement [Windows Forms], Binden von Daten"
  - "DataGrid-Steuerelement [Windows Forms], Informationen über das DataGrid-Steuerelement"
  - "Übergeordnete Tabellen im DataGrid-Steuerelement"
  - "Tabellen [Windows Forms], anzeigen in DataGrid-Steuerelement"
  - "Datenblätter, Informationen über Datenblätter"
  - "Mehrere Tabellen in DataGrid-Steuerelement"
  - "neusortierung der Daten [Windows Forms]"
  - "Daten [Windows Forms] navigieren"
  - "gebundene Steuerelemente, DataGrid-Steuerelement"
  - "datengebundene Steuerelemente, DataGrid"
  - "Übergeordnete Tabelle – Navigation im DataGrid"
  - "untergeordnete Tabellen, DataGrid-Steuerelement"
ms.assetid: 85604bce-bc03-49d9-9030-dda8896c44b1
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# &#220;bersicht &#252;ber das DataGrid-Steuerelement (Windows&#160;Forms)
> [!NOTE]
>  Die <xref:System.Windows.Forms.DataGridView> -Steuerelement ersetzt und funktionell erweitert die <xref:System.Windows.Forms.DataGrid> steuern; allerdings die <xref:System.Windows.Forms.DataGrid> -Steuerelement auf Wunsch für Abwärtskompatibilität und zur künftigen Verwendung beibehalten. Weitere Informationen finden Sie unter [Unterschiede zwischen dem Windows Forms DataGridView-Steuerelement und dem DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> Steuerelement Daten in einer Reihe von Zeilen und Spalten angezeigt. Der einfachste Fall liegt vor, wenn das Raster an eine Datenquelle gebunden ist, die aus einer einzigen Tabelle ohne Beziehungen besteht. In diesem Fall werden die Daten wie in einer Kalkulationstabelle in einfachen Zeilen und Spalten angezeigt. Weitere Informationen zum Binden von Daten an andere Steuerelemente finden Sie unter [Data Binding and Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
 Wenn die <xref:System.Windows.Forms.DataGrid> gebunden ist, um Daten mit mehreren verknüpften Tabellen und Navigation für das Raster aktiviert ist, wird das Raster in jeder Zeile Erweiterungsschaltflächen angezeigt. Mit einer Erweiterung kann der Benutzer von einer übergeordneten Tabelle zu einer untergeordneten Tabelle navigieren. Durch Klicken auf einen Knoten wird die untergeordnete Tabelle angezeigt, und durch Klicken auf die Schaltfläche "Zurück" wird die ursprüngliche übergeordnete Tabelle angezeigt. Auf diese Weise zeigt das Raster die hierarchischen Beziehungen zwischen Tabellen an.  
  
 Im folgenden Screenshot ist ein an Daten mit mehreren Tabellen gebundenes DataGrid-Steuerelement dargestellt.  
  
 ![Ein DataGrid-Steuerelement gebunden wird, um Daten in mehreren Tabellen](../../../../docs/framework/winforms/controls/media/vbcontrol1.gif "vbControl1")  
Ein DataGrid-Steuerelement mit einer Bindung an Daten in mehreren Tabellen  
  
 Die <xref:System.Windows.Forms.DataGrid> eine Benutzeroberfläche für ein Dataset, die Navigation zwischen verknüpften Tabellen sowie umfangreiche formatierungs- und Bearbeitungsfunktionen bereitstellen können.  
  
 Das Anzeigen und das Bearbeiten von Daten sind verschiedene Funktionen: Das Steuerelement ist für die Benutzeroberfläche zuständig, während die Datenbindungsarchitektur von Windows Forms und [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter für Datenaktualisierungen zuständig sind. Aus diesem Grund werden mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, immer synchronisiert.  
  
> [!NOTE]
>  Wenn Sie mit dem DataGrid-Steuerelement in Visual Basic 6.0 vertraut sind, finden Sie in Windows Forms wesentliche Unterschiede auffallen <xref:System.Windows.Forms.DataGrid> Steuerelement.  
  
 Wenn das Raster gebunden ist, auf eine <xref:System.Data.DataSet>, Spalten und Zeilen werden automatisch erstellt, formatiert und gefüllt. Weitere Informationen finden Sie unter [Data Binding and Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md). Nach dem Generieren des der <xref:System.Windows.Forms.DataGrid> Steuerelement, Sie können hinzufügen, löschen, neu anordnen und Formatieren von Spalten und Zeilen, die je nach Ihren Anforderungen.  
  
## <a name="binding-data-to-the-control"></a>Binden von Daten an das Steuerelement  
 Für die <xref:System.Windows.Forms.DataGrid> -Steuerelement funktioniert, das es gebunden werden soll, eine Datenquelle mithilfe der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften zur Entwurfszeit oder der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode zur Laufzeit. Diese Bindung verweist das <xref:System.Windows.Forms.DataGrid> auf ein instanziiertes Datenquellenobjekt, wie z. B. ein <xref:System.Data.DataSet> oder <xref:System.Data.DataTable>). Die <xref:System.Windows.Forms.DataGrid> -Steuerelement zeigt die Ergebnisse der Aktionen, die für die Daten ausgeführt werden. Die meisten datenspezifischen Aktionen werden nicht ausgeführt, bis die <xref:System.Windows.Forms.DataGrid> , sondern von der Datenquelle.  
  
 Wenn die Daten im gebundenen Dataset auf beliebige Weise aktualisiert werden die <xref:System.Windows.Forms.DataGrid> -Steuerelement die Änderungen wider. Ist das Datenraster und dessen Tabellen- und Spaltenformate die `ReadOnly` Eigenschaft festgelegt, um `false`, die Daten im Dataset aktualisiert werden können, über die <xref:System.Windows.Forms.DataGrid> Steuerelement.  
  
 Nur eine Tabelle angezeigt werden kann, der <xref:System.Windows.Forms.DataGrid> gleichzeitig. Wenn eine Parent-Child-Beziehung zwischen Tabellen definiert ist, kann der Benutzer zwischen den verknüpften Tabellen auswählen die Tabelle im angezeigt werden wechseln die <xref:System.Windows.Forms.DataGrid> Steuerelement. Informationen zum Binden einer <xref:System.Windows.Forms.DataGrid> die Steuerung an eine [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] -Datenquelle zur Entwurfszeit oder zur Laufzeit finden Sie unter [wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
 Gültige Datenquellen für die <xref:System.Windows.Forms.DataGrid> umfassen:  
  
-   <xref:System.Data.DataTable> Klasse  
  
-   <xref:System.Data.DataView> Klasse  
  
-   <xref:System.Data.DataSet> Klasse  
  
-   <xref:System.Data.DataViewManager> Klasse  
  
 Wenn es sich bei der Quelle um ein DataSet handelt, kann das DataSet ein Objekt im Formular oder ein Objekt sein, das von einem XML-Webdienst an das Formular übergeben wurde. Sie können das Steuerelement an typisierte oder nicht typisierte DataSets binden.  
  
 Sie können auch Binden einer <xref:System.Windows.Forms.DataGrid> -Steuerelement an zusätzliche Strukturen, wenn die Objekte in der Struktur, beispielsweise die Elemente in einem Array, öffentliche Eigenschaften verfügbar gemacht. Im Raster werden alle öffentlichen Eigenschaften der Elemente in der Struktur angezeigt. Wenn Sie binden, z. B. die <xref:System.Windows.Forms.DataGrid> -Steuerelement an ein Array von Customer-Objekten, im Raster alle öffentlichen Eigenschaften dieser Kundenobjekte angezeigt wird. In einigen Fällen bedeutet dies, dass zwar eine Bindung an die Struktur möglich ist, aber die resultierende gebundene Struktur keine praktische Anwendung findet. So ist beispielsweise die Bindung an ein Array von Ganzzahlen möglich, aber weil der Datentyp `Integer` keine öffentlichen Eigenschaften unterstützt, kann das Raster keine Daten anzeigen.  
  
 Sie können an die folgenden Strukturen binden, wenn die zugehörigen Elemente öffentliche Eigenschaften anzeigen:  
  
-   Jede Komponente, die implementiert die <xref:System.Collections.IList> Schnittstelle. Dazu gehören eindimensionale Arrays.  
  
-   Jede Komponente, die implementiert die <xref:System.ComponentModel.IListSource> Schnittstelle.  
  
-   Jede Komponente, die implementiert die <xref:System.ComponentModel.IBindingList> Schnittstelle.  
  
 Weitere Informationen zu möglichen Datenquellen finden Sie unter [von Windows Forms unterstützte Datenquellen](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).  
  
## <a name="grid-display"></a>Rasteranzeige  
 Eine häufige Verwendung der <xref:System.Windows.Forms.DataGrid> Steuerelement ist eine einzelne Tabelle mit Daten aus einem Dataset angezeigt. Das Steuerelement kann jedoch auch zum Anzeigen mehrerer Tabellen (einschließlich verknüpfter Tabellen) verwendet werden. Die Anzeige des Rasters wird automatisch an die Datenquelle angepasst. Der folgenden Tabelle können Sie entnehmen, was für verschiedene Konfigurationen angezeigt wird.  
  
|Inhalt des DataSets|Anzeige|  
|--------------------------|-----------------------|  
|Einzelne Tabelle|Die Tabelle wird in einem Raster angezeigt.|  
|Mehrere Tabellen|Im Raster kann eine Strukturansicht angezeigt werden, in der Benutzer navigieren können, um nach der anzuzeigenden Tabelle zu suchen.|  
|Mehrere verknüpfte Tabellen|Im Raster kann eine Strukturansicht angezeigt werden, in der Tabellen ausgewählt werden können. Sie können aber auch angeben, dass im Raster die übergeordnete Tabelle angezeigt werden soll. Mithilfe von Datensätzen in der übergeordneten Tabelle können Benutzer zu den entsprechenden untergeordneten Zeilen navigieren.|  
  
> [!NOTE]
>  Tabellen in einem Dataset verknüpft sind, mithilfe einer <xref:System.Data.DataRelation>.  Siehe auch [HYPERLINK "http://msdn.microsoft.com/library/dbwcse3d (110)" Beziehungen in Datasets](http://msdn.microsoft.com/library/dbwcse3d\(v=vs.110\)) oder [Beziehungen in Datasets](http://msdn.microsoft.com/library/dbwcse3d\(v=vs.120\)).  
  
 Wenn die <xref:System.Windows.Forms.DataGrid> -Steuerelement eine Tabelle angezeigt wird und die <xref:System.Windows.Forms.DataGrid.AllowSorting%2A> -Eigenschaft auf festgelegt ist `true`, können die Daten durch Klicken auf den Spaltenheader sortiert werden. Der Benutzer kann auch Zeilen hinzufügen und Zellen bearbeiten.  
  
 Die Beziehungen zwischen mehreren Tabellen werden in einer hierarchischen Navigationsstruktur (mit über-und untergeordneten Elementen) angezeigt. Übergeordnete Tabellen befinden sich auf der obersten Datenebene, und untergeordnete Tabellen stellen Datentabellen dar, die von den jeweiligen Auflistungen in den übergeordneten Tabellen abgeleitet werden. In allen übergeordneten Zeilen, die eine untergeordnete Tabelle enthalten, werden Erweiterungen angezeigt. Durch Klicken auf eine Erweiterung wird eine Liste mit Links zu den untergeordneten Tabellen generiert, die mit einer Liste von Weblinks vergleichbar ist. Wenn der Benutzer auf einen Link klickt, wird die untergeordnete Tabelle angezeigt. Klicken auf das Symbol zum ein-/ausblenden übergeordneten Zeilen (![Symbol zum ein-/ausblenden übergeordneten Zeilen](../../../../docs/framework/winforms/controls/media/vbicon.png "VbIcon")) wird die Informationen zur übergeordneten Tabelle ausgeblendet bzw. wieder eingeblendet, wenn der Benutzer zuvor ausgeblendet wurden. Der Benutzer kann auf die Schaltfläche "Zurück" klicken, um zur vorherigen Tabelle zurückzukehren.  
  
## <a name="columns-and-rows"></a>Spalten und Zeilen  
 Die <xref:System.Windows.Forms.DataGrid> besteht aus einer Auflistung von <xref:System.Windows.Forms.DataGridTableStyle> Objekte, die in enthalten sind die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft. Ein Tabellenformat kann eine Auflistung von enthalten <xref:System.Windows.Forms.DataGridColumnStyle> Objekte, die in enthalten sind die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridTableStyle>... Können Sie bearbeiten die <xref:System.Windows.Forms.DataGrid.TableStyles%2A> und <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Eigenschaften mithilfe von auflistungs-Editoren, die über Zugriff auf die **Eigenschaften** Fenster.  
  
 Alle <xref:System.Windows.Forms.DataGridTableStyle> zugeordneten der <xref:System.Windows.Forms.DataGrid> Steuerelement durch zugegriffen werden kann die <xref:System.Windows.Forms.GridTableStylesCollection>. Die <xref:System.Windows.Forms.GridTableStylesCollection> bearbeitet werden können, im Designer mit der <xref:System.Windows.Forms.DataGridTableStyle> auflistungs-Editor oder programmgesteuert über die <xref:System.Windows.Forms.DataGrid> des Steuerelements <xref:System.Windows.Forms.DataGrid.TableStyles%2A> Eigenschaft.  
  
 ![Im DataGrid-Steuerelement enthaltenen Objekte](../../../../docs/framework/winforms/controls/media/vbcolumns1.png "vbColumns1")  
In der folgenden Abbildung sind die im DataGrid-Steuerelement enthaltenen Objekte dargestellt.  
  
 Tabellenformate und Spaltenformate werden mit synchronisiert <xref:System.Data.DataTable> Objekte und <xref:System.Data.DataColumn> Objekte, indem ihre `MappingName` -Eigenschaften auf die entsprechende <xref:System.Data.DataTable.TableName%2A> und <xref:System.Data.DataColumn.ColumnName%2A> Eigenschaften. Wenn ein <xref:System.Windows.Forms.DataGridTableStyle> ohne Stile hinzugefügt wird ein <xref:System.Windows.Forms.DataGrid> Steuerelement an eine gültige Datenquelle gebunden ist und die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> -Eigenschaft dieses Tabellenformats auf eine gültige festgelegt ist <xref:System.Data.DataTable.TableName%2A> -Eigenschaft, die eine Auflistung von <xref:System.Windows.Forms.DataGridColumnStyle> Objekte für das Tabellenformat erstellt wird. Für jede <xref:System.Data.DataColumn> finden Sie in der <xref:System.Data.DataTable.Columns%2A> Auflistung von der <xref:System.Data.DataTable>, eine entsprechende <xref:System.Windows.Forms.DataGridColumnStyle> wird hinzugefügt, die <xref:System.Windows.Forms.GridColumnStylesCollection>. <xref:System.Windows.Forms.GridColumnStylesCollection> erfolgt über die <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridTableStyle>. Spalten können hinzugefügt oder gelöscht werden, aus dem Raster mithilfe der <xref:System.Windows.Forms.GridColumnStylesCollection.Add%2A> oder <xref:System.Windows.Forms.GridColumnStylesCollection.Remove%2A> Methode für die <xref:System.Windows.Forms.GridColumnStylesCollection>. Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md) und [Gewusst wie: löschen oder Ausblenden von Spalten im DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md).  
  
 Eine Auflistung von Spaltentypen erweitert die <xref:System.Windows.Forms.DataGridColumnStyle> -Klasse umfangreiche Formatierung und Bearbeitungsfunktionen. Alle Spaltentypen erben von der <xref:System.Windows.Forms.DataGridColumnStyle> Basisklasse. -Klasse, die erstellt wird, hängt die <xref:System.Data.DataColumn.DataType%2A> Eigenschaft der <xref:System.Data.DataColumn> aus dem der <xref:System.Web.UI.WebControls.DataGridColumn> basiert. Z. B. eine <xref:System.Data.DataColumn> , bei dem die <xref:System.Data.DataColumn.DataType%2A> Eigenschaft festgelegt, um <xref:System.Boolean> zugeordnet wird die <xref:System.Windows.Forms.DataGridBoolColumn>. In der folgenden Tabelle werden die einzelnen Spaltentypen beschrieben.  
  
|Spaltentyp|Beschreibung|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.DataGridTextBoxColumn>|Akzeptiert Daten und zeigt sie als formatierte oder unformatierte Zeichenfolgen an. Bearbeitungsfunktionen sind die gleichen wie für die Bearbeitung von Daten in einem einfachen <xref:System.Windows.Forms.TextBox>. Erbt von <xref:System.Windows.Forms.DataGridColumnStyle>.|  
|<xref:System.Windows.Forms.DataGridBoolColumn>|Akzeptiert die Werte `true`, `false` und NULL und zeigt sie an. Erbt von <xref:System.Windows.Forms.DataGridColumnStyle>.|  
  
 Wenn Sie auf den rechten Rand einer Spalte doppelklicken, wird die Größe der Spalte so geändert, dass die vollständige Beschriftung und der längste Eintrag angezeigt werden.  
  
## <a name="table-styles-and-column-styles"></a>Tabellenformate und Spaltenformate  
 Sobald Sie das Standardformat des hergestellt haben die <xref:System.Windows.Forms.DataGrid> Steuerelement, Sie können die Farben anpassen, die verwendet wird, wenn bestimmte Tabellen innerhalb des Datenblatts angezeigt werden.  
  
 Dies erfolgt durch Erstellen von Instanzen von der <xref:System.Windows.Forms.DataGridTableStyle> Klasse. Die Formatierung bestimmter Tabellen, sich von der standardformatierung von Tabellenformaten der <xref:System.Windows.Forms.DataGrid> selbst. Für jede Tabelle kann jeweils nur ein Tabellenformat definiert werden.  
  
 In einigen Fällen kann es sich als sinnvoll erweisen, in einer bestimmten Datentabelle eine bestimmte Spalte in einem anderen Format anzuzeigen als die übrigen Spalten. Sie können einen benutzerdefinierten Satz von Spaltenformaten erstellen, mit der <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> Eigenschaft.  
  
 Spaltenformate werden mit Spalten in einem DataSet auf die gleiche Weise verknüpft wie Tabellenformate mit Datentabellen. So wie Sie für jede Tabelle jeweils nur ein Tabellenformat definieren können, kann auch in einem bestimmten Tabellenformat für jede Spalte nur ein Spaltenformat definiert werden. Diese Beziehung wird definiert, in der Spaltenwerts <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> Eigenschaft.  
  
 Wenn Sie ein Tabellenformat ohne Spaltenformate erstellen, fügt [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] Standardspaltenformate hinzu, wenn das Formular und das Raster zur Laufzeit erstellt werden. Wenn Sie jedoch ein Tabellenformat erstellen und diesem Spaltenformate hinzufügen, werden von [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] keine Spaltenformate erstellt. Außerdem müssen Sie Spaltenformate definieren und diesen den Zuordnungsnamen zuweisen, damit die gewünschten Spalten im Raster angezeigt werden.  
  
 Da Sie die im Raster enthaltenen Spalten angeben, indem Sie diesen ein Spaltenformat zuweisen, den Spalten jedoch kein Spaltenformat zugewiesen wurde, können Sie im DataSet Datenspalten einfügen, die nicht im Raster angezeigt werden. Da die Datenspalte jedoch im DataSet enthalten ist, können Sie die nicht angezeigten Daten programmgesteuert bearbeiten.  
  
> [!NOTE]
>  Im Allgemeinen sollten Sie Spaltenformate erstellen und der Auflistung der Spaltenformate hinzufügen, bevor Sie Tabellenformate zur Auflistung der Tabellenformate hinzufügen. Wenn Sie der Auflistung ein leeres Tabellenformat hinzufügen, werden die Spaltenformate automatisch generiert. Aus diesem Grund eine Ausnahme wird ausgelöst, wenn Sie versuchen, neue Spaltenformate mit doppelten hinzuzufügen <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> Werte in der Auflistung der Spaltenformate.  
>   
>  In einigen Fällen möchten Sie nur eine Spalte unter vielen Spalten optimieren. Beispielsweise möchten Sie in einem DataSet mit 50 Spalten nur 49 Spalten übernehmen. In diesem Fall es ist einfacher, alle 50 Spalten zu importieren und eine Spalte programmgesteuert zu entfernen, statt die gewünschten 49 Spalten einzeln programmgesteuert hinzuzufügen.  
  
## <a name="formatting"></a>Formatierung  
 Formatierung, die zugewiesen werden können, die <xref:System.Windows.Forms.DataGrid> -Steuerelement enthält Rahmenarten, rasterlinienstile, Schriftarten, Beschriftungseigenschaften, die Ausrichtung der Daten und abwechselnde Hintergrundfarben zwischen Zeilen. Weitere Informationen finden Sie unter [Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md).  
  
## <a name="events"></a>Ereignisse  
 Neben den allgemeinen Steuerelementereignissen wie <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.Enter>, und <xref:System.Windows.Forms.DataGrid.Scroll>, <xref:System.Windows.Forms.DataGrid> Steuerelement unterstützt Ereignisse im Zusammenhang mit der Bearbeitung und Navigation innerhalb des Rasters. Die <xref:System.Windows.Forms.DataGrid.CurrentCell%2A> -Eigenschaft bestimmt, welche Zelle ausgewählt ist. Die <xref:System.Windows.Forms.DataGrid.CurrentCellChanged> -Ereignis wird ausgelöst, wenn der Benutzer zu einer anderen Zelle navigiert. Wenn der Benutzer zu einer neuen Tabelle über Parent-Child-Beziehungen, die <xref:System.Windows.Forms.DataGrid.Navigate> -Ereignis wird ausgelöst. Die <xref:System.Windows.Forms.DataGrid.BackButtonClick> -Ereignis wird ausgelöst, wenn der Benutzer die zurück-Schaltfläche klickt, wenn der Benutzer eine untergeordneten Tabelle anzeigt und die <xref:System.Windows.Forms.DataGrid.ShowParentDetailsButtonClick> -Ereignis wird ausgelöst, wenn auf das Symbol zum ein-/ausblenden übergeordneten Zeilen geklickt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Gewusst wie: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)   
 [Gewusst wie: Hinzufügen von Tabellen und Spalten, auf dem Windows Forms-DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [Gewusst wie: löschen oder Ausblenden von Spalten in Windows Forms-DataGrid-Steuerelement](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-the-windows-forms-datagrid-control.md)