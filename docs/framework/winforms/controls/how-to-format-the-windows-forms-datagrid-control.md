---
title: 'Vorgehensweise: Formatieren des DataGrid-Steuerelements in Windows Forms'
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
ms.openlocfilehash: 696fdc09d285e0a04148e82b0cece6108b7d5a45
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705908"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="3ce01-102">Vorgehensweise: Formatieren des DataGrid-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3ce01-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="3ce01-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3ce01-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="3ce01-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="3ce01-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="3ce01-105">Verschiedene Farben zu verschiedenen Teilen der Anwendung eine <xref:System.Windows.Forms.DataGrid> steuern können, stellen die Informationen in der er leichter zu lesen und interpretieren.</span><span class="sxs-lookup"><span data-stu-id="3ce01-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="3ce01-106">Farbe kann in Zeilen und Spalten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3ce01-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="3ce01-107">Zeilen und Spalten können auch ausgeblendet oder angezeigt, die in Ihrem eigenen Ermessen.</span><span class="sxs-lookup"><span data-stu-id="3ce01-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="3ce01-108">Es gibt drei grundlegende Aspekte der Formatierung der <xref:System.Windows.Forms.DataGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3ce01-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="3ce01-109">Sie können festlegen, dass Eigenschaften zu, um einen Standardstil herzustellen, in dem Daten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3ce01-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="3ce01-110">Auf dieser Basis können Sie die Möglichkeit, die bestimmte Tabellen zur Laufzeit angezeigt werden, klicken Sie dann anpassen.</span><span class="sxs-lookup"><span data-stu-id="3ce01-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="3ce01-111">Abschließend können Sie ändern, welche Spalten im Raster als auch die Farben angezeigt werden, und andere, die Formatierung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3ce01-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="3ce01-112">Als ersten Schritt bei der Formatierung ein Datenraster, können Sie festlegen, der Eigenschaften der <xref:System.Windows.Forms.DataGrid> selbst.</span><span class="sxs-lookup"><span data-stu-id="3ce01-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="3ce01-113">Diese Farbe und Format-Auswahl bilden eine Basis, die aus der Sie dann abhängig von der Tabellen und Spalten angezeigt, können Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="3ce01-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="3ce01-114">Herstellen einen Standardstil für das DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3ce01-114">To establish a default style for the DataGrid control</span></span>  
  
1.  <span data-ttu-id="3ce01-115">Legen Sie die folgenden Eigenschaften nach Bedarf:</span><span class="sxs-lookup"><span data-stu-id="3ce01-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="3ce01-116">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3ce01-116">Property</span></span>|<span data-ttu-id="3ce01-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ce01-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="3ce01-118">Die <xref:System.Windows.Forms.DataGrid.BackColor%2A> Eigenschaft definiert die Farbe der geraden Zeilen des Rasters.</span><span class="sxs-lookup"><span data-stu-id="3ce01-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="3ce01-119">Beim Festlegen der <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> -Eigenschaft auf eine andere Farbe, jeder anderen Zeile in dieser neuen Farbe festgelegt ist (Zeilen, 1, 3, 5 und So weiter).</span><span class="sxs-lookup"><span data-stu-id="3ce01-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="3ce01-120">Die Hintergrundfarbe der geraden Zeilen des Rasters (Zeilen 0, 2, 4, 6 und So weiter).</span><span class="sxs-lookup"><span data-stu-id="3ce01-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="3ce01-121">Während der <xref:System.Windows.Forms.DataGrid.BackColor%2A> und <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> Eigenschaften bestimmt die Farbe der Zeilen im Raster die <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> Eigenschaft bestimmt die Farbe des der Datenblattzeilen, der nur sichtbar, wenn das Raster unten ein Bildlauf durchgeführt wird, oder wenn nur wenige Zeilen enthält das Raster.</span><span class="sxs-lookup"><span data-stu-id="3ce01-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="3ce01-122">Die Rahmenart des Datenblatts, eines der <xref:System.Windows.Forms.BorderStyle> -Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="3ce01-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="3ce01-123">Die Hintergrundfarbe des Datenblatts fensterbeschriftung unmittelbar oberhalb des Rasters angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3ce01-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="3ce01-124">Die Schriftart der Beschriftung am oberen Rand des Rasters.</span><span class="sxs-lookup"><span data-stu-id="3ce01-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="3ce01-125">Die Hintergrundfarbe der fensterbeschriftung des Datenblatts.</span><span class="sxs-lookup"><span data-stu-id="3ce01-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="3ce01-126">Die Schriftart verwendet, um den Text im Raster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3ce01-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="3ce01-127">Die Farbe der Schriftart, die von den Daten in den Zeilen im Datenraster angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ce01-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="3ce01-128">Die Farbe der Datenblattlinien im Datenraster.</span><span class="sxs-lookup"><span data-stu-id="3ce01-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="3ce01-129">Der Stil der Linien zwischen den Zellen des Rasters, eines der <xref:System.Windows.Forms.DataGridLineStyle> -Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="3ce01-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="3ce01-130">Die Hintergrundfarbe der Zeilen- und Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="3ce01-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="3ce01-131">Die Schriftart für Spaltenköpfe verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ce01-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="3ce01-132">Die Vordergrundfarbe der Spaltenköpfe des Datenblatts, einschließlich des Texts der Spaltenüberschrift, und die plus-/Minus-Symbole (zum Erweitern von Zeilen, wenn mehrere verknüpfte Tabellen angezeigt werden).</span><span class="sxs-lookup"><span data-stu-id="3ce01-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="3ce01-133">Die Farbe des Texts, der alle Links im Datenraster, einschließlich Links zu untergeordneten Tabellen, Name der Beziehung und So weiter.</span><span class="sxs-lookup"><span data-stu-id="3ce01-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="3ce01-134">In einer untergeordneten Tabelle ist dies die Hintergrundfarbe der übergeordneten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="3ce01-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="3ce01-135">In einer untergeordneten Tabelle ist dies die Vordergrundfarbe der übergeordneten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="3ce01-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="3ce01-136">Bestimmt, ob die Tabellen- und Spaltennamen in der übergeordneten Zeile, von angezeigt werden der <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="3ce01-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="3ce01-137">Die Standardbreite der Spalten des Rasters in Pixel.</span><span class="sxs-lookup"><span data-stu-id="3ce01-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="3ce01-138">Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="3ce01-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="3ce01-139">Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3ce01-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="3ce01-140">Die Zeilenhöhe (in Pixel) von Zeilen im Raster.</span><span class="sxs-lookup"><span data-stu-id="3ce01-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="3ce01-141">Legen Sie diese Eigenschaft vor dem Zurücksetzen der <xref:System.Windows.Forms.DataGrid.DataSource%2A> und <xref:System.Windows.Forms.DataGrid.DataMember%2A> Eigenschaften (entweder separat oder über die <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> Methode), oder die Eigenschaft hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="3ce01-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="3ce01-142">Die Eigenschaft kann nicht auf einen Wert kleiner als 0 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3ce01-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="3ce01-143">Die Breite der Zeilenheader des Rasters.</span><span class="sxs-lookup"><span data-stu-id="3ce01-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="3ce01-144">Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Farbe des Hintergrunds.</span><span class="sxs-lookup"><span data-stu-id="3ce01-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="3ce01-145">Wenn eine Zeile oder Zelle ausgewählt ist, ist dies die Vordergrundfarbe darstellt.</span><span class="sxs-lookup"><span data-stu-id="3ce01-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="3ce01-146">Beachten Sie, wenn die Farben der Steuerelemente anpassen, dass es möglich ist, die das Steuerelement aufgrund einer schlechten Farbauswahl (z. B. "Red" und "Grün") nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="3ce01-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="3ce01-147">Verwenden Sie die Farben, die auf die **Systemfarben** Palette, um dieses Problem zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="3ce01-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="3ce01-148">Die folgenden Verfahren wird davon ausgegangen, das Formular enthält ein <xref:System.Windows.Forms.DataGrid> -Steuerelement an eine Datentabelle gebunden.</span><span class="sxs-lookup"><span data-stu-id="3ce01-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="3ce01-149">Weitere Informationen finden Sie unter [Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="3ce01-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="3ce01-150">So legen Sie den Stil für Tabellen und Spalten einer Datentabelle programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="3ce01-150">To set the table and column style of a data table programmatically</span></span>  
  
1.  <span data-ttu-id="3ce01-151">Erstellen einer neuen Tabellenformatvorlage, und seine Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="3ce01-151">Create a new table style and set its properties.</span></span>  
  
2.  <span data-ttu-id="3ce01-152">Erstellen Sie ein Spaltenformat und festlegen Sie seine Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="3ce01-152">Create a column style and set its properties.</span></span>  
  
3.  <span data-ttu-id="3ce01-153">Fügen Sie das Spaltenformat Auflistung Spaltenformate das Tabellenformat an.</span><span class="sxs-lookup"><span data-stu-id="3ce01-153">Add the column style to the table style's column styles collection.</span></span>  
  
4.  <span data-ttu-id="3ce01-154">Fügen Sie das Format der zur Auflistung für das Datenraster Tabelle Stile hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ce01-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5.  <span data-ttu-id="3ce01-155">Erstellen Sie im folgenden Beispiel wird eine Instanz eines neuen <xref:System.Windows.Forms.DataGridTableStyle> und legen Sie dessen <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3ce01-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6.  <span data-ttu-id="3ce01-156">Erstellen Sie eine neue Instanz der ein **GridColumnStyle** und legen Sie dessen **%MappingName** (und einige andere Eigenschaften Layout und die Anzeige).</span><span class="sxs-lookup"><span data-stu-id="3ce01-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7.  <span data-ttu-id="3ce01-157">Wiederholen Sie die Schritte 2 bis 6 für jedes Spaltenformat, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ce01-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="3ce01-158">Im folgende Beispiel wird veranschaulicht, wie eine <xref:System.Windows.Forms.DataGridTextBoxColumn> wird erstellt, weil ein Name, der in der Spalte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3ce01-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="3ce01-159">Außerdem hinzugefügt werden, dem das Spaltenformat den <xref:System.Windows.Forms.GridColumnStylesCollection> des Tabellenformats, und Sie fügen das Tabellenformat an die <xref:System.Windows.Forms.GridTableStylesCollection> im Datenraster.</span><span class="sxs-lookup"><span data-stu-id="3ce01-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ce01-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ce01-160">See also</span></span>
- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="3ce01-161">Vorgehensweise: Löschen oder Ausblenden von Spalten im DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3ce01-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="3ce01-162">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3ce01-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
