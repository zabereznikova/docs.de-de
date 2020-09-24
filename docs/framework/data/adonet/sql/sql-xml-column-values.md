---
title: SQL-XML-Spaltenwerte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: cd55e2263d4b71fe62910ac918e331ebe37833eb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177279"
---
# <a name="sql-xml-column-values"></a>SQL-XML-Spaltenwerte

SQL Server unterstützt den `xml`-Datentyp. Daher können Entwickler Resultsets, die diesen Typ einschließen, mithilfe des Standardverhaltens der <xref:System.Data.SqlClient.SqlCommand>-Klasse abrufen. Eine `xml`-Spalte kann wie jede andere Spalte abgerufen werden (beispielsweise in eine <xref:System.Data.SqlClient.SqlDataReader>-Instanz), wenn Sie den Inhalt der Spalte jedoch als XML verwenden möchten, müssen Sie <xref:System.Xml.XmlReader> verwenden.  
  
## <a name="example"></a>Beispiel  

 Die folgende Konsolenanwendung ruft zwei Zeilen mit jeweils einer `xml`-Spalte aus der **Sales.Store**-Tabelle in der **AdventureWorks**-Datenbank ab und übermittelt sie an eine <xref:System.Data.SqlClient.SqlDataReader>-Instanz. Für jede Zeile wird der Wert der `xml`-Spalte mithilfe der <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Methode von <xref:System.Data.SqlClient.SqlDataReader> gelesen. Der Wert wird in einer <xref:System.Xml.XmlReader>-Instanz gespeichert. Beachten Sie, dass Sie <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> anstelle der <xref:System.Data.IDataRecord.GetValue%2A>-Methode verwenden müssen, wenn Sie eine <xref:System.Data.SqlTypes.SqlXml>-Variable als Inhalt festlegen möchten. <xref:System.Data.IDataRecord.GetValue%2A> gibt den Wert der `xml`-Spalte als Zeichenfolge zurück.  
  
> [!NOTE]
> Beim Installieren von SQL Server wird die Beispieldatenbank **AdventureWorks** in der Standardeinstellung nicht installiert. Sie kann jedoch über das SQL Server-Setup installiert werden.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Data.SqlTypes.SqlXml>
- [XML-Daten in SQL Server](xml-data-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
