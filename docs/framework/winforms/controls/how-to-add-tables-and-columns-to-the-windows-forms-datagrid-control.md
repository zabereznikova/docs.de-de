---
title: "Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca34b5daff07b733ccf2bfb4269c11cff80c7549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="ed893-102">Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ed893-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="ed893-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ed893-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="ed893-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ed893-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="ed893-105">Sie können Daten anzeigen, in Windows Forms <xref:System.Windows.Forms.DataGrid> -Steuerelement in Tabellen und Spalten durch das Erstellen **DataGridTableStyle** Objekte und Hinzufügen der **GridTableStylesCollection** Objekt, das erfolgt über die <xref:System.Windows.Forms.DataGrid> des Steuerelements **TableStyles** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ed893-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="ed893-106">Jedes Tabellenformat zeigt den Inhalt der Datentabelle, in angegeben ist der **DataGridTableStyle** des Objekts **%MappingName** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ed893-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="ed893-107">Ein Tabellenformat ohne Spaltenformate angegeben werden in der Standardeinstellung alle Spalten in der Datentabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed893-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="ed893-108">Sie können einschränken, welche Spalten aus der Tabelle angezeigt werden, indem das Hinzufügen von **DataGridColumnStyle** -Objekte der **GridColumnStylesCollection** -Objekt, das über zugegriffen wird die  **Angezeigten** -Eigenschaft jedes **DataGridTableStyle** Objekt.</span><span class="sxs-lookup"><span data-stu-id="ed893-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="ed893-109">So fügen eine Tabelle und Spalte ein DataGrid-Steuerelement programmgesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="ed893-109">To add a table and column to a DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="ed893-110">Sie müssen zuerst binden, um die Daten in der Tabelle anzuzeigen, die <xref:System.Windows.Forms.DataGrid> Steuerelement zu einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="ed893-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="ed893-111">Weitere Informationen finden Sie unter [Vorgehensweise: Binden des DataGrid-Steuerelements in Windows Forms an eine Datenquelle](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="ed893-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="ed893-112">Wenn Sie Spaltenformate programmgesteuert angeben, erstellen Sie immer **DataGridColumnStyle** -Objekte und fügen sie der **GridColumnStylesCollection** Objekt vor dem Hinzufügen von  **DataGridTableStyle** -Objekte und die **GridTableStylesCollection** Objekt.</span><span class="sxs-lookup"><span data-stu-id="ed893-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="ed893-113">Wenn Sie eine leere hinzufügen **DataGridTableStyle** Objekt der Auflistung **DataGridColumnStyle** Objekte automatisch für Sie generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ed893-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="ed893-114">Daher eine Ausnahme wird ausgelöst, wenn Sie versuchen, das Hinzufügen neuer **DataGridColumnStyle** Objekte mit doppelten **%MappingName** -Werte in der **GridColumnStylesCollection**Objekt.</span><span class="sxs-lookup"><span data-stu-id="ed893-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>  
  
2.  <span data-ttu-id="ed893-115">Deklarieren Sie eine neue Tabellenformatvorlage, und legen Sie dessen Zuordnungsnamen.</span><span class="sxs-lookup"><span data-stu-id="ed893-115">Declare a new table style and set its mapping name.</span></span>  
  
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
  
3.  <span data-ttu-id="ed893-116">Deklarieren Sie eine neue Spalte Formatvorlage und festlegen Sie den Zuordnungsnamen und andere Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ed893-116">Declare a new column style and set its mapping name and other properties.</span></span>  
  
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
  
4.  <span data-ttu-id="ed893-117">Rufen Sie die **hinzufügen** Methode der **GridColumnStylesCollection** -Objekt, das Tabellenformat die Spalte hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="ed893-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  <span data-ttu-id="ed893-118">Rufen Sie die **hinzufügen** Methode der **GridTableStylesCollection** Objekt, das Tabellenformat das Datenraster hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ed893-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ed893-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed893-119">See Also</span></span>  
 [<span data-ttu-id="ed893-120">DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ed893-120">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="ed893-121">Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ed893-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
