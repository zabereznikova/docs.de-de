---
title: SQL-XML-Spaltenwerte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 087a0583c8655f28fcc308768bf75fcaa1d36ef9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="sql-xml-column-values"></a>SQL-XML-Spaltenwerte
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] unterstützt den `xml`-Datentyp. Daher können Entwickler Resultsets, die diesen Typ einschließen, mithilfe des Standardverhaltens der <xref:System.Data.SqlClient.SqlCommand>-Klasse abrufen. Eine `xml`-Spalte kann auf die gleiche Weise abgerufen werden wie jede andere Spalte auch (z. B. in einem <xref:System.Data.SqlClient.SqlDataReader>). Wenn Sie jedoch mit dem Inhalt der Spalte in Form von XML-Daten arbeiten möchten, müssen Sie einen <xref:System.Xml.XmlReader> verwenden.  
  
## <a name="example"></a>Beispiel  
 Die folgende Konsolenanwendung wählt zwei Zeilen mit jeweils einer `xml` Spalte aus der **Sales.Store** -Tabelle in der **AdventureWorks** -Datenbank auf eine <xref:System.Data.SqlClient.SqlDataReader> Instanz. Der Wert der `xml`-Spalte für jede Zeile wird mit der <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Methode des <xref:System.Data.SqlClient.SqlDataReader> gelesen. Der Wert wird in einem <xref:System.Xml.XmlReader> gespeichert. Wenn Sie den Inhalt als <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A>-Variable festlegen möchten, müssen Sie anstelle der <xref:System.Data.IDataRecord.GetValue%2A>-Methode die <xref:System.Data.SqlTypes.SqlXml>-Methode verwenden, denn <xref:System.Data.IDataRecord.GetValue%2A> gibt den Wert der `xml`-Spalte als Zeichenfolge zurück.  
  
> [!NOTE]
>  Die **AdventureWorks** -Beispieldatenbank ist nicht standardmäßig installiert, bei der Installation [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. Sie kann jedoch mithilfe von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Setup installiert werden.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Data.SqlTypes.SqlXml>  
 [XML-Daten in SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
