---
title: DataGrid-Steuerelement formatieren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 30342a89f3176255fa7217ccbbbd91c166ff7f35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732958"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="ef11f-102">Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef11f-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="ef11f-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ef11f-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="ef11f-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ef11f-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="ef11f-105">Das Anwenden verschiedener Farben auf verschiedene Teile eines <xref:System.Windows.Forms.DataGrid> Steuer Elements kann dazu beitragen, die Informationen leichter zu lesen und zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="ef11f-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="ef11f-106">Farbe kann auf Zeilen und Spalten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef11f-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="ef11f-107">Zeilen und Spalten können auch ausgeblendet oder nach eigenem Ermessen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef11f-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="ef11f-108">Es gibt drei grundlegende Aspekte beim Formatieren des <xref:System.Windows.Forms.DataGrid> Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="ef11f-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="ef11f-109">Sie können Eigenschaften festlegen, um einen Standardstil festzulegen, in dem Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef11f-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="ef11f-110">Aus dieser Basis können Sie dann die Art und Weise anpassen, in der bestimmte Tabellen zur Laufzeit angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef11f-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="ef11f-111">Schließlich können Sie ändern, welche Spalten im Datenraster angezeigt werden und welche Farben und andere Formatierung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef11f-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="ef11f-112">Als ersten Schritt beim Formatieren eines Datenrasters können Sie die Eigenschaften des <xref:System.Windows.Forms.DataGrid> selbst festlegen.</span><span class="sxs-lookup"><span data-stu-id="ef11f-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="ef11f-113">Diese Farben und Formatierungsoptionen bilden eine Basis, von der Sie abhängig von den angezeigten Datentabellen und Spalten Änderungen vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="ef11f-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="ef11f-114">So legen Sie einen Standardstil für das DataGrid-Steuerelement fest</span><span class="sxs-lookup"><span data-stu-id="ef11f-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="ef11f-115">Legen Sie nach Bedarf die folgenden Eigenschaften fest:</span><span class="sxs-lookup"><span data-stu-id="ef11f-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="ef11f-116">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ef11f-116">Property</span></span>|<span data-ttu-id="ef11f-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ef11f-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="ef11f-118">Die <xref:System.Windows.Forms.DataGrid.BackColor%2A>-Eigenschaft definiert die Farbe der gerade nummerierten Zeilen im Raster.</span><span class="sxs-lookup"><span data-stu-id="ef11f-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="ef11f-119">Wenn Sie die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>-Eigenschaft auf eine andere Farbe festlegen, wird jede andere Zeile auf diese neue Farbe festgelegt (Zeilen 1, 3, 5 usw.).</span><span class="sxs-lookup"><span data-stu-id="ef11f-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="ef11f-120">Die Hintergrundfarbe der gerade nummerierten Zeilen des Rasters (Zeilen 0, 2, 4, 6 usw.).</span><span class="sxs-lookup"><span data-stu-id="ef11f-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="ef11f-121">Während die Eigenschaften <xref:System.Windows.Forms.DataGrid.BackColor%2A> und <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> die Farbe der Zeilen im Raster bestimmen, bestimmt die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>-Eigenschaft die Farbe des nicht Zeilen Bereichs, der nur sichtbar ist, wenn ein Raster nach unten bewegt wird oder nur einige Zeilen im Raster enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ef11f-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="ef11f-122">Die Rahmenart des Rasters, einer der <xref:System.Windows.Forms.BorderStyle> Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="ef11f-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="ef11f-123">Die Hintergrundfarbe der Fenster Beschriftung des Rasters, die unmittelbar oberhalb des Rasters angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ef11f-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="ef11f-124">Die Schriftart der Beschriftung am oberen Rand des Rasters.</span><span class="sxs-lookup"><span data-stu-id="ef11f-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="ef11f-125">Die Hintergrundfarbe der Fenster Beschriftung des Datenblatts.</span><span class="sxs-lookup"><span data-stu-id="ef11f-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="ef11f-126">Die Schriftart, die verwendet wird, um den Text im Raster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ef11f-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="ef11f-127">Die Farbe der Schriftart, die von den Daten in den Zeilen des Datenrasters angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ef11f-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="ef11f-128">Die Farbe der Rasterlinien des Datenrasters.</span><span class="sxs-lookup"><span data-stu-id="ef11f-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="ef11f-129">Der Stil der Zeilen, die die Zellen des Rasters trennen, einer der <xref:System.Windows.Forms.DataGridLineStyle> Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="ef11f-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="ef11f-130">Die Hintergrundfarbe der Zeilen-und Spaltenheader.</span><span class="sxs-lookup"><span data-stu-id="ef11f-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="ef11f-131">Die Schriftart, die für die Spaltenheader verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef11f-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="ef11f-132">Die Vordergrundfarbe der Spaltenheader des Rasters, einschließlich des Spaltenheader Texts und der Plus/Minus-Symbole (zum Erweitern von Zeilen, wenn mehrere verknüpfte Tabellen angezeigt werden).</span><span class="sxs-lookup"><span data-stu-id="ef11f-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="ef11f-133">Die Textfarbe aller Links im Datenraster, einschließlich Links zu untergeordneten Tabellen, Beziehungs Name usw.</span><span class="sxs-lookup"><span data-stu-id="ef11f-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="ef11f-134">In einer untergeordneten Tabelle ist dies die Hintergrundfarbe der übergeordneten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="ef11f-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="ef11f-135">In einer untergeordneten Tabelle ist dies die Vordergrundfarbe der übergeordneten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="ef11f-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="ef11f-136">Bestimmt mithilfe der <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> Enumeration, ob die Tabellen-und Spaltennamen in der übergeordneten Zeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef11f-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="ef11f-137">Die Standardbreite der Spalten des Rasters in Pixel.</span><span class="sxs-lookup"><span data-stu-id="ef11f-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="ef11f-138">Legen Sie diese Eigenschaft fest, bevor Sie die Eigenschaften <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> zurücksetzen (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode), oder die Eigenschaft hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="ef11f-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="ef11f-139">Die-Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ef11f-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="ef11f-140">Die Zeilenhöhe (in Pixel) der Zeilen im Raster.</span><span class="sxs-lookup"><span data-stu-id="ef11f-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="ef11f-141">Legen Sie diese Eigenschaft fest, bevor Sie die Eigenschaften <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> zurücksetzen (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>-Methode), oder die Eigenschaft hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="ef11f-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="ef11f-142">Die-Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ef11f-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="ef11f-143">Die Breite der Zeilen Header des Rasters.</span><span class="sxs-lookup"><span data-stu-id="ef11f-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="ef11f-144">Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Hintergrundfarbe.</span><span class="sxs-lookup"><span data-stu-id="ef11f-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="ef11f-145">Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe.</span><span class="sxs-lookup"><span data-stu-id="ef11f-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="ef11f-146">Beachten Sie beim Anpassen der Farben von Steuerelementen, dass es möglich ist, das Steuerelement nicht zugänglich zu machen, aufgrund von schlechter Farbauswahl (z. b. rot und grün).</span><span class="sxs-lookup"><span data-stu-id="ef11f-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="ef11f-147">Verwenden Sie die Farben, die auf der Palette **System Farben** verfügbar sind, um dieses Problem zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="ef11f-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="ef11f-148">Bei den folgenden Prozeduren wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.DataGrid>-Steuerelement an eine Datentabelle</span><span class="sxs-lookup"><span data-stu-id="ef11f-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="ef11f-149">Weitere Informationen finden Sie unter [Binden des Windows Forms DataGrid-Steuer Elements an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="ef11f-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="ef11f-150">So legen Sie den Tabellen-und Spalten Stil einer Datentabelle Programm gesteuert fest</span><span class="sxs-lookup"><span data-stu-id="ef11f-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="ef11f-151">Erstellen Sie einen neuen Tabellen Stil, und legen Sie seine Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="ef11f-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="ef11f-152">Erstellen Sie einen Spalten Stil, und legen Sie seine Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="ef11f-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="ef11f-153">Fügen Sie den Spalten Stil der Auflistung der Spalten Stile des Tabellen Stils hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef11f-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="ef11f-154">Fügen Sie den Tabellen Stil der Auflistung der Tabellen Stile des Datenrasters hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef11f-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="ef11f-155">Erstellen Sie im folgenden Beispiel eine Instanz eines neuen <xref:System.Windows.Forms.DataGridTableStyle>, und legen Sie dessen <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="ef11f-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="ef11f-156">Erstellen Sie eine neue Instanz eines **GridColumnStyle** -Elements, und legen Sie seinen **MappingName** (und andere Layout-und Anzeigeeigenschaften) fest.</span><span class="sxs-lookup"><span data-stu-id="ef11f-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="ef11f-157">Wiederholen Sie die Schritte 2 bis 6 für jeden Spalten Stil, den Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ef11f-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="ef11f-158">Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.DataGridTextBoxColumn> erstellt wird, da ein Name in der-Spalte angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ef11f-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="ef11f-159">Außerdem fügen Sie dem <xref:System.Windows.Forms.GridColumnStylesCollection> des Tabellen Stils den Spalten Stil hinzu, und Sie fügen den Tabellen Stil der <xref:System.Windows.Forms.GridTableStylesCollection> des Datenrasters hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef11f-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ef11f-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef11f-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="ef11f-161">Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef11f-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="ef11f-162">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ef11f-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
