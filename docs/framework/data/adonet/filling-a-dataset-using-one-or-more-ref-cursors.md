---
title: Auffüllen eines "DataSets" mit einem oder mehreren REF CURSORs
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 99863e79-5b00-467e-a105-4ffa42de3ff7
ms.openlocfilehash: 30e50ae171ec9733e222c55e98d1cfcfa535d4e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201480"
---
# <a name="filling-a-dataset-using-one-or-more-ref-cursors"></a><span data-ttu-id="a5063-102">Auffüllen eines "DataSets" mit einem oder mehreren REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="a5063-102">Filling a DataSet Using One or More REF CURSORs</span></span>
<span data-ttu-id="a5063-103">In diesem Microsoft Visual Basic-Beispiel wird eine gespeicherte PL/SQL-Prozedur ausgeführt, die zwei REF CURSOR-Parameter zurückgibt und ein <xref:System.Data.DataSet> mit den zurückgegebenen Zeilen füllt.</span><span class="sxs-lookup"><span data-stu-id="a5063-103">This Microsoft Visual Basic example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
```vb  
Private Sub Button1_Click(ByVal sender As Object, _  
  ByVal e As System.EventArgs) Handles Button1.Click  
  
  Dim connString As New String(_  
    "Data Source=Oracle9i;User ID=scott;Password=tiger;")  
  Dim ds As New DataSet()  
    Using conn As New OracleConnection(connString)  
    Dim cmd As New OracleCommand()  
  
    cmd.Connection = conn  
    cmd.CommandText = "CURSPKG.OPEN_TWO_CURSORS"  
    cmd.CommandType = CommandType.StoredProcedure  
    cmd.Parameters.Add(New OracleParameter( _  
      "EMPCURSOR", OracleType.Cursor)).Direction = _  
      ParameterDirection.Output  
    cmd.Parameters.Add(New OracleParameter( _  
      "DEPTCURSOR", OracleType.Cursor)).Direction = _  
       ParameterDirection.Output  
  
    Dim da As New OracleDataAdapter(cmd)  
    da.TableMappings.Add("Table", "Emp")  
    da.TableMappings.Add("Table1", "Dept")  
    da.Fill(ds)  
  
    ds.Relations.Add("EmpDept", ds.Tables("Dept").Columns("Deptno"), _  
      ds.Tables("Emp").Columns("Deptno"), False)  
  
    DataGrid1.DataSource = ds.Tables("Dept")  
  End Using  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5063-104">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5063-104">See also</span></span>

- [<span data-ttu-id="a5063-105">Oracle-REF CURSORs</span><span class="sxs-lookup"><span data-stu-id="a5063-105">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)
- [<span data-ttu-id="a5063-106">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a5063-106">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
