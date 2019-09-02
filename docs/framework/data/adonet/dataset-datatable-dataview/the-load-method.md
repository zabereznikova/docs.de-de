---
title: Load-Methode
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: b704deeffcd06bca09b6c26d60a66218b46fc55c
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203171"
---
# <a name="the-load-method"></a><span data-ttu-id="aa1af-102">Load-Methode</span><span class="sxs-lookup"><span data-stu-id="aa1af-102">The Load Method</span></span>
<span data-ttu-id="aa1af-103">Mithilfe der <xref:System.Data.DataTable.Load%2A>-Methode kann eine <xref:System.Data.DataTable> mit Zeilen aus einer Datenquelle geladen werden.</span><span class="sxs-lookup"><span data-stu-id="aa1af-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="aa1af-104">Dabei handelt es sich um eine überladene Methode, die in ihrer einfachsten Form einen einzelnen Parameter ( **DataReader**) akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="aa1af-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="aa1af-105">In diesem Formular wird die **Daten** Tabelle einfach mit Zeilen geladen.</span><span class="sxs-lookup"><span data-stu-id="aa1af-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="aa1af-106">Optional können Sie den **LoadOption** -Parameter angeben, um zu steuern, wie Daten derDatentabelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="aa1af-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="aa1af-107">Der **LoadOption** -Parameter ist besonders nützlich in Fällen, in denen die Datentabelle bereits Daten Zeilen enthält, da Sie beschreibt, wie die eingehenden Daten aus der Datenquelle mit den bereits in der Tabelle enthaltenen Daten kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="aa1af-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="aa1af-108">Beispielsweise gibt " **Konservierungs-ecurrentvalues** " (Standardwert) an, dass in Fällen, in denen eine Zeilein der Datentabelle als **hinzugefügt** gekennzeichnet ist, der **ursprüngliche** Wert oder jede Spalte auf den Inhalt der übereinstimmenden Zeile aus der Datenquelle festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="aa1af-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="aa1af-109">Der **aktuelle** Wert behält die Werte bei, die beim Hinzufügen der Zeile zugewiesen wurden, und der **RowState** der Zeile wird auf " **geändert**" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aa1af-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="aa1af-110">Die folgende Tabelle enthält eine kurze Beschreibung der <xref:System.Data.LoadOption>-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="aa1af-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="aa1af-111">Der LoadOption-Wert</span><span class="sxs-lookup"><span data-stu-id="aa1af-111">LoadOption value</span></span>|<span data-ttu-id="aa1af-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa1af-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="aa1af-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="aa1af-113">**OverwriteRow**</span></span>|<span data-ttu-id="aa1af-114">Wenn eingehende Zeilen denselben **PrimaryKey** -Wert wie eine bereits in der **Daten**Tabelle geltende Zeile aufweisen, werden die **ursprünglichen** und **aktuellen** Werte jeder Spalte durch die Werte in der eingehenden Zeile ersetzt, und die **RowState** -Eigenschaft wird auf festgelegt. **Unverändert**.</span><span class="sxs-lookup"><span data-stu-id="aa1af-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="aa1af-115">Zeilen aus der Datenquelle, die nicht bereits in der Daten Tabelle vorhanden sind, werden mit dem **RowState** -Wert **unverändert**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="aa1af-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="aa1af-116">Mit dieser Option wird der Inhalt der Datentabelle aktualisiert , sodass Sie mit dem Inhalt der Datenquelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="aa1af-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="aa1af-117">**Konserviecurrentvalues (Standard)**</span><span class="sxs-lookup"><span data-stu-id="aa1af-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="aa1af-118">Wenn eingehende Zeilen denselben **PrimaryKey** -Wert wie eine bereits in der **Daten**Tabelle geltende Zeile aufweisen, wird der **ursprüngliche** Wert auf den Inhalt der eingehenden Zeile festgelegt, und der **aktuelle** Wert wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="aa1af-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="aa1af-119">Wenn der **RowState** **hinzugefügt** oder **geändert**wird, wird er auf **modified**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aa1af-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="aa1af-120">Wenn der **RowState** **gelöscht**wurde, bleibt er **gelöscht**.</span><span class="sxs-lookup"><span data-stu-id="aa1af-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="aa1af-121">Zeilen aus der Datenquelle, die nicht bereits in der Daten Tabelle vorhanden sind, werden hinzugefügt, und der **RowState** wird auf " **unverändert**" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aa1af-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="aa1af-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="aa1af-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="aa1af-123">Wenn eingehende Zeilen denselben **PrimaryKey** -Wert wie die bereits in der **Daten**Tabelle geltende Zeile aufweisen, wird der **aktuelle** Wert in den **ursprünglichen** Wert kopiert, und der **aktuelle** Wert wird dann auf den Inhalt der eingehenden Zeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aa1af-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="aa1af-124">Wenn der **RowState** in der **Daten** Tabelle **hinzugefügt**wurde, wird der **RowState** weiterhin **hinzugefügt**.</span><span class="sxs-lookup"><span data-stu-id="aa1af-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="aa1af-125">Für Zeilen, die als **geändert** oder **gelöscht**markiert sind, wird der **RowState** **geändert**.</span><span class="sxs-lookup"><span data-stu-id="aa1af-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="aa1af-126">Zeilen aus der Datenquelle, die nicht bereits in der Daten Tabelle vorhanden sind, werden hinzugefügt, und der **RowState** wird auf **Added**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aa1af-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="aa1af-127">Im folgenden Beispiel wird die **Load** -Methode verwendet, um eine Liste der Geburtstage für die Mitarbeiter in der **Northwind** -Datenbank anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="aa1af-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.   
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa1af-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa1af-128">See also</span></span>

- [<span data-ttu-id="aa1af-129">Bearbeiten von Daten in einer DataTable</span><span class="sxs-lookup"><span data-stu-id="aa1af-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="aa1af-130">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="aa1af-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
