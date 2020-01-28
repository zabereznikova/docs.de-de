---
title: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: 2db2e38c326cbcd78c58ee4fe00cd9ed20ae0e8a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747205"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="d81bf-102">Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d81bf-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="d81bf-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d81bf-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="d81bf-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="d81bf-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="d81bf-105">Sie können Daten in der Windows Forms <xref:System.Windows.Forms.DataGrid>-Steuerelement in Tabellen und Spalten anzeigen, indem Sie **DataGridTableStyle** -Objekte erstellen und Sie dem **GridTableStylesCollection** -Objekt hinzufügen, auf das über die **TableStyles** -Eigenschaft des <xref:System.Windows.Forms.DataGrid>-Steuer Elements zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="d81bf-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="d81bf-106">Jedes Tabellenformat zeigt den Inhalt einer beliebigen Datentabelle an, die in der **MappingName** -Eigenschaft des **DataGridTableStyle** -Objekts angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d81bf-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="d81bf-107">Standardmäßig werden in einem Tabellenformat ohne Angabe von Spalten Formaten alle Spalten in der Datentabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d81bf-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="d81bf-108">Sie können einschränken, welche Spalten aus der Tabelle angezeigt werden, indem Sie dem **GridColumnStylesCollection** -Objekt **DataGridColumnStyle** -Objekte hinzufügen, auf das über die **GridColumnStyles** -Eigenschaft der einzelnen **DataGridTableStyle** -Objekte zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="d81bf-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="d81bf-109">So fügen Sie einem DataGrid eine Tabelle und eine Spalte Programm gesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="d81bf-109">To add a table and column to a DataGrid programmatically</span></span>

1. <span data-ttu-id="d81bf-110">Um Daten in der Tabelle anzuzeigen, müssen Sie zuerst das <xref:System.Windows.Forms.DataGrid>-Steuerelement an ein DataSet binden.</span><span class="sxs-lookup"><span data-stu-id="d81bf-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="d81bf-111">Weitere Informationen finden Sie unter Gewusst [wie: Binden des Windows Forms DataGrid-Steuer Elements an eine Datenquelle](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="d81bf-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="d81bf-112">Erstellen Sie beim programmgesteuerten Angeben von Spalten **Formaten immer DataGridColumnStyle** -Objekte, und fügen Sie Sie dem **GridColumnStylesCollection** -Objekt hinzu, bevor Sie dem **GridTableStylesCollection** -Objekt **DataGridTableStyle** -Objekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d81bf-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="d81bf-113">Wenn Sie der Auflistung ein leeres **DataGridTableStyle** -Objekt hinzufügen, werden automatisch **DataGridColumnStyle** -Objekte für Sie generiert.</span><span class="sxs-lookup"><span data-stu-id="d81bf-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="d81bf-114">Folglich wird eine Ausnahme ausgelöst, wenn Sie versuchen, dem **GridColumnStylesCollection** -Objekt neue **DataGridColumnStyle** -Objekte mit doppelten **MappingName** -Werten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d81bf-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>

2. <span data-ttu-id="d81bf-115">Deklarieren Sie einen neuen Tabellen Stil, und legen Sie seinen Zuordnungsnamen</span><span class="sxs-lookup"><span data-stu-id="d81bf-115">Declare a new table style and set its mapping name.</span></span>

    ```vb
    Dim ts1 As New DataGridTableStyle()
    ts1.MappingName = "Customers"
    ```

    ```csharp
    DataGridTableStyle ts1 = new DataGridTableStyle();
    ts1.MappingName = "Customers";
    ```

    ```cpp
    DataGridTableStyle* ts1 = new DataGridTableStyle();
    ts1->MappingName = S"Customers";
    ```

3. <span data-ttu-id="d81bf-116">Deklarieren Sie einen neuen Spalten Stil, und legen Sie seinen Zuordnungsnamen und andere Eigenschaften fest</span><span class="sxs-lookup"><span data-stu-id="d81bf-116">Declare a new column style and set its mapping name and other properties.</span></span>

    ```vb
    Dim myDataCol As New DataGridBoolColumn()
    myDataCol.HeaderText = "My New Column"
    myDataCol.MappingName = "Current"
    ```

    ```csharp
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();
    myDataCol.HeaderText = "My New Column";
    myDataCol.MappingName = "Current";
    ```

    ```cpp
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();
    myDataCol->HeaderText = "My New Column";
    myDataCol->MappingName = "Current";
    ```

4. <span data-ttu-id="d81bf-117">Ruft die **Add** -Methode des **GridColumnStylesCollection** -Objekts auf, um die Spalte dem Tabellenformat hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d81bf-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. <span data-ttu-id="d81bf-118">Greifen Sie auf die **Add** -Methode des **GridTableStylesCollection** -Objekts zu, um dem Datenraster den Tabellen Stil hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d81bf-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a><span data-ttu-id="d81bf-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d81bf-119">See also</span></span>

- [<span data-ttu-id="d81bf-120">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d81bf-120">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="d81bf-121">Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d81bf-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
