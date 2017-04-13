---
title: "Ausf&#252;hren eines Befehls | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Ausf&#252;hren eines Befehls
Jeder in .NET Framework enthaltene .NET Framework\-Datenanbieter besitzt ein eigenes Befehlsobjekt, das von <xref:System.Data.Common.DbCommand> erbt.  Der .NET Framework\-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbCommand>\-Objekt, der .NET Framework\-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlCommand>\-Objekt, der .NET Framework\-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcCommand>\-Objekt, und der .NET Framework\-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleCommand>\-Objekt.  Jedes dieser Objekte macht Methoden für das Ausführen von Befehlen auf der Grundlage des Befehlstyps und des gewünschten Rückgabewerts verfügbar. Die folgende Tabelle enthält eine Beschreibung der einzelnen Befehle.  
  
|Befehl|Rückgabewert|  
|------------|------------------|  
|`ExecuteReader`|Gibt ein `DataReader`\-Objekt zurück.|  
|`ExecuteScalar`|Gibt einen einzelnen Skalarwert zurück.|  
|`ExecuteNonQuery`|Führt einen Befehl aus, der keine Zeilen zurückgibt.|  
|`ExecuteXMLReader`|Gibt einen <xref:System.Xml.XmlReader> zurück.  Nur für ein `SqlCommand`\-Objekt verfügbar.|  
  
 Jedes stark typisierte Befehlsobjekt unterstützt auch eine <xref:System.Data.CommandType>\-Enumeration, die angibt, wie eine Befehlszeichenfolge interpretiert wird. Nähere Informationen dazu finden Sie in der folgenden Tabelle.  
  
|CommandType|Beschreibung|  
|-----------------|------------------|  
|`Text`|SQL\-Befehl, der die an der Datenquelle auszuführenden Anweisungen definiert|  
|`StoredProcedure`|Der Name der gespeicherten Prozedur.  Mit der `Parameters`\-Befehlseigenschaft können Sie auf die Eingabe\- und Ausgabeparameter sowie auf die Rückgabewerte zugreifen, und dies unabhängig davon, welche `Execute`\-Methode aufgerufen wird.  Wenn Sie die `ExecuteReader`\-Methode aufrufen, stehen die Rückgabewerte und die Ausgabeparameter jedoch erst zur Verfügung, wenn das `DataReader`\-Objekt geschlossen ist.|  
|`TableDirect`|Name der Tabelle|  
  
## Beispiel  
 Das folgende Codebeispiel zeigt, wie durch Festlegen seiner Eigenschaften ein <xref:System.Data.SqlClient.SqlCommand>\-Objekt zum Ausführen einer gespeicherten Prozedur erstellt werden kann.  Ein <xref:System.Data.SqlClient.SqlParameter>\-Objekt wird zur Angabe des Eingabeparameters für die gespeicherte Prozedur verwendet.  Der Befehl wird mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>\-Methode ausgeführt, und die Ausgabe des <xref:System.Data.SqlClient.SqlDataReader> wird im Konsolenfenster angezeigt.  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### Befehle für die Problembehandlung  
 Der .NET Framework\-Datenanbieter für SQL Server enthält Leistungsindikatoren, mit denen Sie Probleme ermitteln können, die mit fehlgeschlagenen Befehlsausführungen im Zusammenhang stehen.  Weitere Informationen finden Sie unter [Leistungsindikatoren](../../../../docs/framework/data/adonet/performance-counters.md).  
  
## Siehe auch  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [DataAdapter und DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Working with DataReaders](http://msdn.microsoft.com/de-de/126a966a-d08d-4d22-a19f-f432908b2b54)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)