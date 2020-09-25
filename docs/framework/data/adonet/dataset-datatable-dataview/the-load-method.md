---
title: Load-Methode
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: ea437d1f8ed567934acafbd8db1f8dba8eb22bcc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177539"
---
# <a name="the-load-method"></a><span data-ttu-id="12b31-102">Load-Methode</span><span class="sxs-lookup"><span data-stu-id="12b31-102">The Load Method</span></span>

<span data-ttu-id="12b31-103">Mithilfe der <xref:System.Data.DataTable.Load%2A>-Methode kann eine <xref:System.Data.DataTable> mit Zeilen aus einer Datenquelle geladen werden.</span><span class="sxs-lookup"><span data-stu-id="12b31-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="12b31-104">Dabei handelt es sich um eine überladene Methode, die in ihrer einfachsten Form einen einzelnen Parameter ( **DataReader**) akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="12b31-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="12b31-105">In diesem Formular wird die **Daten** Tabelle einfach mit Zeilen geladen.</span><span class="sxs-lookup"><span data-stu-id="12b31-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="12b31-106">Optional können Sie den **LoadOption** -Parameter angeben, um zu steuern, wie **Daten der Daten**Tabelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="12b31-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="12b31-107">Der **LoadOption** -Parameter ist besonders nützlich in Fällen, in denen die Datentabelle bereits Daten Zeilen enthält, da Sie beschreibt, **wie die Eingeh** enden Daten aus der Datenquelle mit den bereits in der Tabelle enthaltenen Daten kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="12b31-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="12b31-108">Beispielsweise gibt " **Konservierungs-ecurrentvalues** " (Standardwert) an, dass in Fällen, in denen eine Zeile in der Datentabelle als **hinzugefügt** gekennzeichnet **ist, der** **ursprüngliche** Wert oder jede Spalte auf den Inhalt der übereinstimmenden Zeile aus der Datenquelle festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="12b31-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="12b31-109">Der **aktuelle** Wert behält die Werte bei, die beim Hinzufügen der Zeile zugewiesen wurden, und der **RowState** der Zeile wird auf " **geändert**" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="12b31-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="12b31-110">Die folgende Tabelle enthält eine kurze Beschreibung der <xref:System.Data.LoadOption>-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="12b31-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="12b31-111">Der LoadOption-Wert</span><span class="sxs-lookup"><span data-stu-id="12b31-111">LoadOption value</span></span>|<span data-ttu-id="12b31-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12b31-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="12b31-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="12b31-113">**OverwriteRow**</span></span>|<span data-ttu-id="12b31-114">Wenn eingehende Zeilen denselben **PrimaryKey** -Wert wie eine bereits in der Datentabelle bereits in der **Daten**Tabelle vorhanden sind, werden die **ursprünglichen** und **aktuellen** Werte jeder Spalte durch die Werte in der eingehenden Zeile ersetzt, und die **RowState** -Eigenschaft wird auf **unverändert**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="12b31-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="12b31-115">Zeilen aus der Datenquelle, die nicht bereits in der Datentabelle **vorhanden sind, werden mit dem** **RowState** -Wert **unverändert**hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="12b31-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="12b31-116">Mit dieser Option wird der Inhalt der Datentabelle aktualisiert **, sodass Sie** mit dem Inhalt der Datenquelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="12b31-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="12b31-117">**PreserveCurrentValues (Standard)**</span><span class="sxs-lookup"><span data-stu-id="12b31-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="12b31-118">Wenn eingehende Zeilen denselben **PrimaryKey** -Wert wie eine bereits in der **Daten**Tabelle geltende Zeile aufweisen, wird der **ursprüngliche** Wert auf den Inhalt der eingehenden Zeile festgelegt, und der **aktuelle** Wert wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="12b31-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="12b31-119">Wenn der **RowState** **hinzugefügt** oder **geändert**wird, wird er auf **modified**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="12b31-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="12b31-120">Wenn der **RowState** **gelöscht**wurde, bleibt er **gelöscht**.</span><span class="sxs-lookup"><span data-stu-id="12b31-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="12b31-121">Zeilen aus der Datenquelle **, die nicht** bereits in der Datentabelle vorhanden sind, werden hinzugefügt, und der **RowState** wird auf " **unverändert**" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="12b31-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="12b31-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="12b31-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="12b31-123">Wenn eingehende Zeilen denselben **PrimaryKey** -Wert wie die bereits in der **Daten**Tabelle geltende Zeile aufweisen, wird der **aktuelle** Wert in den **ursprünglichen** Wert kopiert, und der **aktuelle** Wert wird dann auf den Inhalt der eingehenden Zeile festgelegt.</span><span class="sxs-lookup"><span data-stu-id="12b31-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="12b31-124">Wenn der **RowState** in der **Daten** Tabelle **hinzugefügt**wurde, wird der **RowState** weiterhin **hinzugefügt**.</span><span class="sxs-lookup"><span data-stu-id="12b31-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="12b31-125">Für Zeilen, die als **geändert** oder **gelöscht**markiert sind, wird der **RowState** **geändert**.</span><span class="sxs-lookup"><span data-stu-id="12b31-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="12b31-126">Zeilen aus der Datenquelle **, die nicht** bereits in der Datentabelle vorhanden sind, werden hinzugefügt, und der **RowState** wird auf **Added**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="12b31-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="12b31-127">Im folgenden Beispiel wird die **Load** -Methode verwendet, um eine Liste der Geburtstage für die Mitarbeiter in der **Northwind** -Datenbank anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="12b31-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12b31-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12b31-128">See also</span></span>

- [<span data-ttu-id="12b31-129">Bearbeiten von Daten in einer "DataTable"</span><span class="sxs-lookup"><span data-stu-id="12b31-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="12b31-130">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12b31-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
