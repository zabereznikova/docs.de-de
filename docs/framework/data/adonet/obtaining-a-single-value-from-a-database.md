---
title: Abrufen eines einzelnen Werts aus einer Datenbank
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: b7ad989dce39a8e9a0ed7b6cd988e06304e7b40f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="obtaining-a-single-value-from-a-database"></a>Abrufen eines einzelnen Werts aus einer Datenbank
Es kann vorkommen, dass Sie lediglich einzelne Werte anstelle von Tabellen oder Datenstreams aus einer Datenbank zurückgeben möchten. Sie möchten z. B. das Ergebnis einer Aggregatfunktion wie z. B. Anzahl zurückgeben (\*), SUM(Price) oder AVG(Quantity). Die **Befehl** Objekt bietet die Möglichkeit, einzelne Werte mit Zurückgeben der **ExecuteScalar** Methode. Die **ExecuteScalar** Methodenrückgabe als Skalarwert, der Wert der ersten Spalte der ersten Zeile des Resultsets.  
  
 Im folgenden Codebeispiel wird mit einem <xref:System.Data.SqlClient.SqlCommand> ein neuer Wert in der Datenbank eingefügt. Mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>-Methode wird der Wert der Identitätsspalte für den eingefügten Datensatz zurückgegeben.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Ausführen eines Befehls](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [DbConnection, DbCommand und DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
