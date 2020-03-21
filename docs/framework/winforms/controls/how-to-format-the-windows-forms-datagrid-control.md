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
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182139"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="5b8fd-102">Gewusst wie: Formatieren des DataGrid-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b8fd-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="5b8fd-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="5b8fd-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="5b8fd-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="5b8fd-105">Das Anwenden unterschiedlicher Farben <xref:System.Windows.Forms.DataGrid> auf verschiedene Teile eines Steuerelements kann dazu beitragen, die darin enthaltenen Informationen leichter lesbar und zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="5b8fd-106">Farbe kann auf Zeilen und Spalten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="5b8fd-107">Zeilen und Spalten können auch nach Eigenem Ermessen ausgeblendet oder angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="5b8fd-108">Es gibt drei grundlegende <xref:System.Windows.Forms.DataGrid> Aspekte der Formatierung des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="5b8fd-109">Sie können Eigenschaften festlegen, um einen Standardstil festzulegen, in dem Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="5b8fd-110">Von dieser Basis aus können Sie dann die Art und Weise anpassen, wie bestimmte Tabellen zur Laufzeit angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="5b8fd-111">Schließlich können Sie ändern, welche Spalten im Datenraster angezeigt werden, sowie die angezeigten Farben und andere Formatierungen.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="5b8fd-112">Als ersten Schritt beim Formatieren eines Datenrasters <xref:System.Windows.Forms.DataGrid> können Sie die Eigenschaften der selbst festlegen.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="5b8fd-113">Diese Farb- und Formatauswahlen bilden eine Basis, von der aus Sie dann Änderungen vornehmen können, abhängig von den angezeigten Datentabellen und Spalten.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="5b8fd-114">So legen Sie einen Standardstil für das DataGrid-Steuerelement fest</span><span class="sxs-lookup"><span data-stu-id="5b8fd-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="5b8fd-115">Legen Sie die folgenden Eigenschaften entsprechend fest:</span><span class="sxs-lookup"><span data-stu-id="5b8fd-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="5b8fd-116">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5b8fd-116">Property</span></span>|<span data-ttu-id="5b8fd-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b8fd-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="5b8fd-118">Die <xref:System.Windows.Forms.DataGrid.BackColor%2A> Eigenschaft definiert die Farbe der geraden Zeilen des Rasters.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="5b8fd-119">Wenn Sie <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> die Eigenschaft auf eine andere Farbe festlegen, wird jede zweite Zeile auf diese neue Farbe festgelegt (Zeilen 1, 3, 5 usw.).</span><span class="sxs-lookup"><span data-stu-id="5b8fd-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="5b8fd-120">Die Hintergrundfarbe der geraden Zeilen des Rasters (Zeilen 0, 2, 4, 6 usw.).</span><span class="sxs-lookup"><span data-stu-id="5b8fd-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="5b8fd-121">Während <xref:System.Windows.Forms.DataGrid.BackColor%2A> die <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> und Eigenschaften die Farbe von <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> Zeilen im Raster bestimmen, bestimmt die Eigenschaft die Farbe des Nicht-Zeilenbereichs, der nur sichtbar ist, wenn das Raster nach unten gescrollt wird oder wenn nur wenige Zeilen im Raster enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="5b8fd-122">Der Rahmenstil des Rasters, <xref:System.Windows.Forms.BorderStyle> einer der Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="5b8fd-123">Die Hintergrundfarbe der Fensterbeschriftung des Rasters, die direkt über dem Raster angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="5b8fd-124">Die Schriftart der Beschriftung am oberen Rand des Rasters.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="5b8fd-125">Die Hintergrundfarbe der Fensterbeschriftung des Rasters.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="5b8fd-126">Die Schriftart, die zum Anzeigen des Texts im Raster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="5b8fd-127">Die Farbe der Schriftart, die von den Daten in den Zeilen des Datenrasters angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="5b8fd-128">Die Farbe der Rasterlinien des Datenrasters.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="5b8fd-129">Der Stil der Linien, die die Zellen des <xref:System.Windows.Forms.DataGridLineStyle> Rasters trennen, einer der Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="5b8fd-130">Die Hintergrundfarbe von Zeilen- und Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="5b8fd-131">Die Schriftart, die für die Spaltenüberschriften verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="5b8fd-132">Die Vordergrundfarbe der Spaltenüberschriften des Rasters, einschließlich des Spaltenkopfzeilentexts und der Plus/Minus-Glyphen (zum Erweitern von Zeilen, wenn mehrere verknüpfte Tabellen angezeigt werden).</span><span class="sxs-lookup"><span data-stu-id="5b8fd-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="5b8fd-133">Die Farbe des Textes aller Verknüpfungen im Datenraster, einschließlich Verknüpfungen zu untergeordneten Tabellen, dem Beziehungsnamen usw.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="5b8fd-134">In einer untergeordneten Tabelle ist dies die Hintergrundfarbe der übergeordneten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="5b8fd-135">In einer untergeordneten Tabelle ist dies die Vordergrundfarbe der übergeordneten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="5b8fd-136">Bestimmt, ob die Tabellen- und Spaltennamen in der <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> übergeordneten Zeile anhand der Enumeration angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="5b8fd-137">Die Standardbreite der Spalten des Rasters in Pixel.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="5b8fd-138">Legen Sie diese Eigenschaft <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> und -eigenschaften (entweder separat oder über die Methode) fest, da die Eigenschaft keine Auswirkungen hat.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="5b8fd-139">Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="5b8fd-140">Die Zeilenhöhe (in Pixel) von Zeilen im Raster.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="5b8fd-141">Legen Sie diese Eigenschaft <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> und -eigenschaften (entweder separat oder über die Methode) fest, da die Eigenschaft keine Auswirkungen hat.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="5b8fd-142">Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="5b8fd-143">Die Breite der Zeilenüberschriften des Rasters.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="5b8fd-144">Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Hintergrundfarbe.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="5b8fd-145">Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="5b8fd-146">Beachten Sie beim Anpassen der Farben von Steuerelementen, dass es möglich ist, das Steuerelement aufgrund einer schlechten Farbauswahl (z. B. Rot und Grün) unzugänglich zu machen.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="5b8fd-147">Verwenden Sie die Farben, die in der Palette **"Systemfarben"** verfügbar sind, um dieses Problem zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="5b8fd-148">Die folgenden Verfahren gehen <xref:System.Windows.Forms.DataGrid> davon aus, dass das Formular über ein Steuerelement verfügt, das an eine Datentabelle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="5b8fd-149">Weitere Informationen finden Sie unter [Binden des Windows Forms DataGrid-Steuerelements an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="5b8fd-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="5b8fd-150">So legen Sie den Tabellen- und Spaltenstil einer Datentabelle programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="5b8fd-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="5b8fd-151">Erstellen Sie einen neuen Tabellenstil, und legen Sie dessen Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="5b8fd-152">Erstellen Sie einen Spaltenstil, und legen Sie dessen Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="5b8fd-153">Fügen Sie den Spaltenstil der Spaltenstilsammlung des Tabellenstils hinzu.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="5b8fd-154">Fügen Sie den Tabellenstil der Tabellenstilsammlung des Datenrasters hinzu.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="5b8fd-155">Erstellen Sie im folgenden Beispiel eine <xref:System.Windows.Forms.DataGridTableStyle> Instanz <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> einer neuen Instanz, und legen Sie ihre Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="5b8fd-156">Erstellen Sie eine neue Instanz eines **GridColumnStyle,** und legen Sie den **MappingName** (und einige andere Layout- und Anzeigeeigenschaften) fest.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="5b8fd-157">Wiederholen Sie die Schritte 2 bis 6 für jeden Spaltenstil, den Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="5b8fd-158">Das folgende Beispiel veranschaulicht, wie ein <xref:System.Windows.Forms.DataGridTextBoxColumn> erstellt wird, da ein Name in der Spalte angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="5b8fd-159">Darüber hinaus fügen Sie den <xref:System.Windows.Forms.GridColumnStylesCollection> Spaltenstil zum Tabellenformat und den <xref:System.Windows.Forms.GridTableStylesCollection> Tabellenstil zum Datenraster hinzu.</span><span class="sxs-lookup"><span data-stu-id="5b8fd-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5b8fd-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b8fd-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="5b8fd-161">Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b8fd-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="5b8fd-162">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5b8fd-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
