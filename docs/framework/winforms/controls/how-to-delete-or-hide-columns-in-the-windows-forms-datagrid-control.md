---
title: "Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms"
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
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d89f14d034c1050d364282c04424b1326bcff9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="8fa93-102">Gewusst wie: Löschen oder Ausblenden von Spalten aus dem DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fa93-102">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="8fa93-103">Obwohl das <xref:System.Windows.Forms.DataGridView>-Steuerelement das <xref:System.Windows.Forms.DataGrid>-Steuerelement ersetzt und funktionell erweitert, wird das <xref:System.Windows.Forms.DataGrid>-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="8fa93-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="8fa93-104">Weitere Informationen finden Sie unter [Unterschiede zwischen dem DataGridView-Steuerelement und dem DataGrid-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="8fa93-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="8fa93-105">Programmgesteuert löschen oder Ausblenden von Spalten in Windows Forms <xref:System.Windows.Forms.DataGrid> mithilfe der Eigenschaften und Methoden des Steuerelements die <xref:System.Windows.Forms.GridColumnStylesCollection> und <xref:System.Windows.Forms.DataGridColumnStyle> Objekte (Member der der <xref:System.Windows.Forms.DataGridTableStyle> Klasse).</span><span class="sxs-lookup"><span data-stu-id="8fa93-105">You can programmatically delete or hide columns in the Windows Forms <xref:System.Windows.Forms.DataGrid> control by using the properties and methods of the <xref:System.Windows.Forms.GridColumnStylesCollection> and <xref:System.Windows.Forms.DataGridColumnStyle> objects (which are members of the <xref:System.Windows.Forms.DataGridTableStyle> class).</span></span>  
  
 <span data-ttu-id="8fa93-106">Die gelöschten oder ausgeblendeten Spalten sind weiterhin vorhanden, in der Datenquelle, die dem Raster gebunden ist und weiterhin programmgesteuert aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="8fa93-106">The deleted or hidden columns still exist in the data source the grid is bound to, and can still be accessed programmatically.</span></span> <span data-ttu-id="8fa93-107">Sie sind gerade nicht mehr in das DataGrid-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8fa93-107">They are just no longer visible in the datagrid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fa93-108">Wenn Ihre Anwendung greift nicht auf bestimmte Spalten der Daten und nicht in das DataGrid-Steuerelement angezeigt werden möchten, ist es wahrscheinlich nicht erforderlich, um ursprünglich in der Datenquelle einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8fa93-108">If your application does not access certain columns of data, and you do not want them displayed in the datagrid, then it is probably not necessary to include them in the data source in the first place.</span></span>  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a><span data-ttu-id="8fa93-109">So löschen Sie eine Spalte programmgesteuert aus dem DataGrid</span><span class="sxs-lookup"><span data-stu-id="8fa93-109">To delete a column from the DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="8fa93-110">Deklarieren Sie eine neue Instanz der im Deklarationsbereich des Formulars die <xref:System.Windows.Forms.DataGridTableStyle> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fa93-110">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2.  <span data-ttu-id="8fa93-111">Legen Sie die <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> Eigenschaft, um die Tabelle in der Datenquelle, die der Stil angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8fa93-111">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> property to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="8fa93-112">Im folgenden Beispiel wird die <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft, die es wird vorausgesetzt, ist bereits festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8fa93-112">The following example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3.  <span data-ttu-id="8fa93-113">Fügen Sie der neuen <xref:System.Windows.Forms.DataGridTableStyle> -Objekt, das Datenraster Tabellenformate der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="8fa93-113">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4.  <span data-ttu-id="8fa93-114">Rufen Sie die <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> Methode der <xref:System.Windows.Forms.DataGrid>des <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> -Auflistung, den Spaltenindex der zu löschenden Spalte angeben.</span><span class="sxs-lookup"><span data-stu-id="8fa93-114">Call the <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> collection, specifying the column index of the column to delete.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a><span data-ttu-id="8fa93-115">So blenden Sie eine Spalte in das DataGrid-Steuerelement programmgesteuert aus</span><span class="sxs-lookup"><span data-stu-id="8fa93-115">To hide a column in the DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="8fa93-116">Deklarieren Sie eine neue Instanz der im Deklarationsbereich des Formulars die <xref:System.Windows.Forms.DataGridTableStyle> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fa93-116">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2.  <span data-ttu-id="8fa93-117">Festlegen der <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> Eigenschaft von der <xref:System.Windows.Forms.DataGridTableStyle> auf die Tabelle in der Datenquelle, die der Stil angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8fa93-117">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property of the <xref:System.Windows.Forms.DataGridTableStyle> to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="8fa93-118">Im folgenden Codebeispiel wird mit der <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> -Eigenschaft, die es wird vorausgesetzt, ist bereits festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8fa93-118">The following code example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3.  <span data-ttu-id="8fa93-119">Fügen Sie der neuen <xref:System.Windows.Forms.DataGridTableStyle> -Objekt, das Datenraster Tabellenformate der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="8fa93-119">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4.  <span data-ttu-id="8fa93-120">Ausblenden der Spalte durch Festlegen seiner `Width` -Eigenschaft auf 0 festlegen des Spaltenindexes der Spalte ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="8fa93-120">Hide the column by setting its `Width` property to 0, specifying the column index of the column to hide.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8fa93-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fa93-121">See Also</span></span>  
 [<span data-ttu-id="8fa93-122">Gewusst wie: Ändern der angezeigten Daten im DataGrid-Steuerelement in Windows Forms zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8fa93-122">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)  
 [<span data-ttu-id="8fa93-123">Gewusst wie: Hinzufügen von Tabellen und Spalten zum DataGrid-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8fa93-123">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
