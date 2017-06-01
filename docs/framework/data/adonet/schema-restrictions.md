---
title: "Schemaeinschr&#228;nkungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Schemaeinschr&#228;nkungen
Bei dem zweiten optionalen Parameter der **GetSchema**\-Methode handelt es sich um Einschränkungen, mit denen die Menge der zurückgegebenen Schemainformationen beschränkt wird. Dieser Parameter wird als Zeichenfolgenarray an die **GetSchema**\-Methode übergeben.  Die Position im Array bestimmt die Werte, die zurückgegeben werden können. Dies entspricht der Anzahl der Einschränkungen.  
  
 In der folgenden Tabelle werden beispielsweise die Einschränkungen beschrieben, die von der Schemaauflistung "Tables" mithilfe des .NET Framework\-Datenanbieters für SQL Server unterstützt werden.  Zusätzliche Einschränkungen für SQL Server\-Schemaauflistungen werden am Ende dieses Themas aufgeführt.  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|Owner|@Owner|TABLE\_SCHEMA|2|  
|Tabelle|@Name|TABLE\_NAME|3|  
|TableType|@TableType|TABLE\_TYPE|4|  
  
## Angeben der Einschränkungswerte  
 Wenn Sie eine der Einschränkungen der **Tables**\-Schemaauflistung verwenden möchten, erstellen Sie ein Zeichenfolgenarray mit vier Elementen und fügen einen Wert in das Element ein, das mit der Einschränkungsnummer übereinstimmt.  Um beispielsweise die von der **GetSchema**\-Methode zurückgegebenen Tabellen nur auf Tabellen im "Sales"\-Schema zu beschränken, muss das zweite Element des Arrays vor der Übergabe an die **GetSchema**\-Methode auf "Sales" festgelegt werden.  
  
> [!NOTE]
>  Die Einschränkungsauflistungen für den `SqlClient` und den `OracleClient` verfügen über eine zusätzliche `ParameterName`\-Spalte.  Die Spalte für den Einschränkungsstandard ist zwar aus Gründen der Abwärtskompatibilität vorhanden, wird aber derzeit ignoriert.  Verwenden Sie Abfragen mit Parametern statt Zeichenfolgenersetzungen, um das Risiko eines SQL\-Injection\-Angriffs beim Angeben der Einschränkungswerte zu minimieren.  
  
> [!NOTE]
>  Die Anzahl der Elementen im Array muss kleiner oder gleich der Anzahl der Einschränkungen sein, die für die angegebene Schemaauflistung unterstützt werden, da sonst eine <xref:System.ArgumentException> ausgelöst wird.  Es können weniger Elemente als die maximale Anzahl der Einschränkungen vorhanden sein.  Es wird davon ausgegangen, dass die fehlenden Einschränkungen NULL \(uneingeschränkt\) sind.  
  
 Sie können einen verwalteten Anbieter für .NET Framework abfragen, um die Liste der unterstützten Einschränkungen durch Aufrufen der **GetSchema**\-Methode mit dem Namen der Schemaauflistung der Einschränkungen zu ermitteln, der "Restrictions" lautet.  Dabei wird eine <xref:System.Data.DataTable> mit einer Liste der Auflistungsnamen, Einschränkungsnamen, Standardeinschränkungswerte und der Anzahl der Einschränkungen zurückgegeben.  
  
### Beispiel  
 In den folgenden Beispielen wird veranschaulicht, wie die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>\-Methode des .NET Framework\-Datenanbieters für die SQL Server\-Klasse <xref:System.Data.SqlClient.SqlConnection> verwendet wird, um Schemainformationen zu allen in der Beispieldatenbank **AdventureWorks** enthaltenen Tabellen abzurufen und die zurückgegebenen Informationen auf die Tabellen im "Sales"\-Schema zu beschränken:  
  
 \[Visual Basic\]  
  
```  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
 \[C\#\]  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## SQL Server\-Schemabeschränkungen  
 In den folgenden Tabellen sind die Beschränkungen für SQL Server\-Schemaauflistungen aufgeführt.  
  
### Benutzer  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|User\_Name|@Name|Name|1|  
  
### Databases  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Name|@Name|Name|1|  
  
### Tabellen  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|Owner|@Owner|TABLE\_SCHEMA|2|  
|Tabelle|@Name|TABLE\_NAME|3|  
|TableType|@TableType|TABLE\_TYPE|4|  
  
### Columns  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|Owner|@Owner|TABLE\_SCHEMA|2|  
|Tabelle|@Table|TABLE\_NAME|3|  
|Spalte|@Column|COLUMN\_NAME|4|  
  
### StructuredTypeMembers  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|Owner|@Owner|TABLE\_SCHEMA|2|  
|Tabelle|@Table|TABLE\_NAME|3|  
|Spalte|@Column|COLUMN\_NAME|4|  
  
### Ansichten  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|Owner|@Owner|TABLE\_SCHEMA|2|  
|Tabelle|@Table|TABLE\_NAME|3|  
  
### ViewColumns  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|VIEW\_CATALOG|1|  
|Owner|@Owner|VIEW\_SCHEMA|2|  
|Tabelle|@Table|VIEW\_NAME|3|  
|Spalte|@Column|COLUMN\_NAME|4|  
  
### ProcedureParameters  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|SPECIFIC\_CATALOG|1|  
|Owner|@Owner|SPECIFIC\_SCHEMA|2|  
|Name|@Name|SPECIFIC\_NAME|3|  
|Parameter|@Parameter|PARAMETER\_NAME|4|  
  
### Verfahren  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|SPECIFIC\_CATALOG|1|  
|Owner|@Owner|SPECIFIC\_SCHEMA|2|  
|Name|@Name|SPECIFIC\_NAME|3|  
|Typ|@Type|ROUTINE\_TYPE|4|  
  
### IndexColumns  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|db\_name\(\)|1|  
|Owner|@Owner|user\_name\(\)|2|  
|Tabelle|@Table|o.  Name|3|  
|ConstraintName|@ConstraintName|x.  Name|4|  
|Spalte|@Column|c.  Name|5|  
  
### Indexes  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|db\_name\(\)|1|  
|Owner|@Owner|user\_name\(\)|2|  
|Tabelle|@Table|o.  Name|3|  
  
### UserDefinedTypes  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|assembly\_name|@AssemblyName|assemblies.  Name|1|  
|udt\_name|@UDTName|types.assembly\_class|2|  
  
### ForeignKeys  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|CONSTRAINT\_CATALOG|1|  
|Owner|@Owner|CONSTRAINT\_SCHEMA|2|  
|Tabelle|@Table|TABLE\_NAME|3|  
|Name|@Name|CONSTRAINT\_NAME|4|  
  
## SQL Server 2008\-Schemabeschränkungen  
 In den folgenden Tabellen sind die Beschränkungen für SQL Server 2008\-Schemaauflistungen aufgeführt.  Diese Beschränkungen gelten ab Version 3.5 SP1 von .NET Framework und SQL Server 2008.  Sie werden in früheren Versionen von .NET Framework und SQL Server nicht unterstützt.  
  
### ColumnSetColumns  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|Owner|@Owner|TABLE\_SCHEMA|2|  
|Tabelle|@Table|TABLE\_NAME|3|  
  
### AllColumns  
  
|Einschränkungsname|Parametername|Einschränkungsstandard|Einschränkungsnummer|  
|------------------------|-------------------|----------------------------|--------------------------|  
|Catalog|@Catalog|TABLE\_CATALOG|1|  
|Owner|@Owner|TABLE\_SCHEMA|2|  
|Tabelle|@Table|TABLE\_NAME|3|  
|Spalte|@Column|COLUMN\_NAME|4|  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)