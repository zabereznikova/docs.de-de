---
title: Ausführen eines Befehls
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
ms.openlocfilehash: c3ed424aff3cd485a78d26a7f27bc5b1eac66448
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879410"
---
# <a name="executing-a-command"></a>Ausführen eines Befehls
Jeder in .NET Framework enthaltene .NET Framework-Datenanbieter besitzt ein eigenes Befehlsobjekt, das von <xref:System.Data.Common.DbCommand> erbt. Der .NET Framework-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbCommand>-Objekt, der .NET Framework-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlCommand>-Objekt, der .NET Framework-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcCommand>-Objekt, und der .NET Framework-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleCommand>-Objekt. Jedes dieser Objekte macht Methoden für das Ausführen von Befehlen auf der Grundlage des Befehlstyps und des gewünschten Rückgabewerts verfügbar. Die folgende Tabelle enthält eine Beschreibung der einzelnen Befehle.  
  
|Befehl|Rückgabewert|  
|-------------|------------------|  
|`ExecuteReader`|Gibt ein `DataReader`-Objekt zurück.|  
|`ExecuteScalar`|Gibt einen einzelnen Skalarwert zurück.|  
|`ExecuteNonQuery`|Führt einen Befehl aus, der keine Zeilen zurückgibt.|  
|`ExecuteXMLReader`|Gibt einen <xref:System.Xml.XmlReader> zurück. Nur für ein `SqlCommand`-Objekt verfügbar.|  
  
 Jedes stark typisierte Befehlsobjekt unterstützt auch eine <xref:System.Data.CommandType>-Enumeration, die angibt, wie eine Befehlszeichenfolge interpretiert wird. Nähere Informationen dazu finden Sie in der folgenden Tabelle.  
  
|CommandType|Beschreibung|  
|-----------------|-----------------|  
|`Text`|SQL-Befehl, der die an der Datenquelle auszuführenden Anweisungen definiert|  
|`StoredProcedure`|Der Name der gespeicherten Prozedur. Mit der `Parameters`-Befehlseigenschaft können Sie auf die Eingabe- und Ausgabeparameter sowie auf die Rückgabewerte zugreifen, und dies unabhängig davon, welche `Execute`-Methode aufgerufen wird. Wenn Sie die `ExecuteReader`-Methode aufrufen, stehen die Rückgabewerte und die Ausgabeparameter jedoch erst zur Verfügung, wenn das `DataReader`-Objekt geschlossen ist.|  
|`TableDirect`|Name der Tabelle|  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt, wie durch Festlegen seiner Eigenschaften ein <xref:System.Data.SqlClient.SqlCommand>-Objekt zum Ausführen einer gespeicherten Prozedur erstellt werden kann. Ein <xref:System.Data.SqlClient.SqlParameter>-Objekt wird zur Angabe des Eingabeparameters für die gespeicherte Prozedur verwendet. Der Befehl wird mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>-Methode ausgeführt, und die Ausgabe des <xref:System.Data.SqlClient.SqlDataReader> wird im Konsolenfenster angezeigt.  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a>Befehle für die Problembehandlung  
 Der .NET Framework-Datenanbieter für SQL Server enthält Leistungsindikatoren, mit denen Sie Probleme ermitteln können, die mit fehlgeschlagenen Befehlsausführungen im Zusammenhang stehen. Weitere Informationen finden Sie unter [Leistungsindikatoren](../../../../docs/framework/data/adonet/performance-counters.md).  
  
## <a name="see-also"></a>Siehe auch

- [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [DataAdapters und DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
