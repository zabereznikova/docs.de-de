---
title: SQL-XML-Spaltenwerte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 803357f9ae97eee2cbbf5e777dbc1210ded26ab2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670130"
---
# <a name="sql-xml-column-values"></a>SQL-XML-Spaltenwerte
SQL Server unterstützt die `xml` -Datentyp, und Entwickler können Abrufen von Resultsets, die diesen Typ mithilfe des Standardverhaltens der einschließen, die <xref:System.Data.SqlClient.SqlCommand> Klasse. Eine `xml`-Spalte kann auf die gleiche Weise abgerufen werden wie jede andere Spalte auch (z. B. in einem <xref:System.Data.SqlClient.SqlDataReader>). Wenn Sie jedoch mit dem Inhalt der Spalte in Form von XML-Daten arbeiten möchten, müssen Sie einen <xref:System.Xml.XmlReader> verwenden.  
  
## <a name="example"></a>Beispiel  
 Die folgende Konsolenanwendung wählt zwei Zeilen mit jeweils einer `xml` Spalte aus der **Sales.Store** -Tabelle in der **AdventureWorks** -Datenbank in eine <xref:System.Data.SqlClient.SqlDataReader> Instanz. Der Wert der `xml`-Spalte für jede Zeile wird mit der <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Methode des <xref:System.Data.SqlClient.SqlDataReader> gelesen. Der Wert wird in einem <xref:System.Xml.XmlReader> gespeichert. Wenn Sie den Inhalt als <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Variable festlegen möchten, müssen Sie anstelle der <xref:System.Data.IDataRecord.GetValue%2A>-Methode die <xref:System.Data.SqlTypes.SqlXml>-Methode verwenden, denn <xref:System.Data.IDataRecord.GetValue%2A> gibt den Wert der `xml`-Spalte als Zeichenfolge zurück.  
  
> [!NOTE]
>  Die **AdventureWorks** Beispieldatenbank ist nicht standardmäßig installiert, bei der Installation von SQL Server. Sie kann jedoch durch Ausführen des Setups von SQL Server installiert werden.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.SqlTypes.SqlXml>
- [XML-Daten in SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
