---
title: Ändern von Daten mit "DbDataAdapter"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e35c7f9e-648b-4fcc-9361-d365c3e42c9a
ms.openlocfilehash: 3038e35947cd8f97266d374a367a77380df440dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772176"
---
# <a name="modifying-data-with-a-dbdataadapter"></a>Ändern von Daten mit "DbDataAdapter"
Mit der <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A>-Methode eines <xref:System.Data.Common.DbProviderFactory>-Objekts erhalten Sie ein <xref:System.Data.Common.DbDataAdapter>-Objekt, das bezüglich des zugrunde liegenden Datenanbieters, der beim Erstellen der Factory angegeben wurde, stark typisiert ist. Sie können dann einen <xref:System.Data.Common.DbCommandBuilder> verwenden, um Einfüge-, Update- und Löschbefehle für Daten in einem <xref:System.Data.DataSet> zu erstellen und diese auf eine Datenquelle anzuwenden.  
  
## <a name="retrieving-data-with-a-dbdataadapter"></a>Abrufen von Daten mit einem "DbDataAdapter"  
 Das folgende Beispiel zeigt das Erstellen eines stark typisierten `DbDataAdapter` auf der Grundlage eines Anbieternamens und einer Verbindungszeichenfolge. Der Code verwendet die <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A>-Methode der <xref:System.Data.Common.DbProviderFactory>, um eine <xref:System.Data.Common.DbConnection> zu erstellen. Als Nächstes verwendet der Code die <xref:System.Data.Common.DbProviderFactory.CreateCommand%2A>-Methode, um einen <xref:System.Data.Common.DbCommand> zum Auswählen von Daten zu erstellen, wobei dessen Eigenschaften `CommandText` und `Connection` festgelegt werden. Zum Schluss erstellt der Code unter Verwendung der <xref:System.Data.Common.DbDataAdapter>-Methode ein <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A>-Objekt und legt deren `SelectCommand`-Eigenschaft fest. Die `Fill`-Methode des `DbDataAdapter` lädt die Daten in eine <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/VB/source.vb#1)]  
  
## <a name="modifying-data-with-a-dbdataadapter"></a>Ändern von Daten mit "DbDataAdapter"  
 Dieses Beispiel zeigt, wie die Daten in einer `DataTable` mit einem <xref:System.Data.Common.DbDataAdapter> geändert werden können, indem ein <xref:System.Data.Common.DbCommandBuilder> verwendet wird, um die für das Aktualisieren der Daten an der Datenquelle benötigten Befehle zu generieren. Mit dem <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> des `DbDataAdapter` werden die Kundennummer (CustomerID) und der Firmenname (CompanyName) aus der Customers-Tabelle abgerufen. Mit der <xref:System.Data.Common.DbCommandBuilder.GetInsertCommand%2A>-Methode wird die <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>-Eigenschaft festgelegt, mit der <xref:System.Data.Common.DbCommandBuilder.GetUpdateCommand%2A>-Methode wird die <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>-Eigenschaft festgelegt, und mit der <xref:System.Data.Common.DbCommandBuilder.GetDeleteCommand%2A>-Methode wird die <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A>-Eigenschaft festgelegt. Der Code fügt der &lt;legacyBold&gt;Customers&lt;/legacyBold&gt;-Tabelle eine neue Zeile hinzu und aktualisiert die Datenquelle. Der Code lokalisiert anschließend die hinzugefügte Zeile, indem er anhand der &lt;legacyBold&gt;CustomerID&lt;/legacyBold&gt; sucht. &lt;legacyBold&gt;CustomerID&lt;/legacyBold&gt; ist dabei der für die &lt;legacyBold&gt;Customers&lt;/legacyBold&gt;-Tabelle definierte Primärschlüssel. Er ändert den CompanyName-Wert und aktualisiert die Datenquelle. Zum Schluss löscht der Code die Zeile.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/VB/source.vb#1)]  
  
## <a name="handling-parameters"></a>Behandlung von Parametern  
 Die .NET Framework-Datenanbieter handhaben die Benennung und das Angeben von Parametern und Parameterplatzhaltern unterschiedlich. Der folgenden Tabelle können Sie die Syntax für die verschiedenen Datenquellen entnehmen:  
  
|Datenanbieter|Syntax für Parameterbenennung|  
|-------------------|-----------------------------|  
|`SqlClient`|Verwendet benannte Parameter im Format `@`*Parametername*.|  
|`OracleClient`|Verwendet benannte Parameter im Format `:`*Parametername* (oder *Parametername*).|  
|`OleDb`|Verwendet Positionsparametermarker, die durch ein Fragezeichen (`?`) gekennzeichnet sind.|  
|`Odbc`|Verwendet Positionsparametermarker, die durch ein Fragezeichen (`?`) gekennzeichnet sind.|  
  
 Das Factorymodell bietet keine Unterstützung beim Erstellen parametrisierter `DbCommand`- und `DbDataAdapter`-Objekte. Zum Erstellen von Parametern, die auf Ihren Datenanbieter zugeschnitten sind, müssen Sie in Ihrem Code mit Branches arbeiten.  
  
> [!IMPORTANT]
>  Aus Sicherheitsgründen wird davon abgeraten, anbieterspezifische Parameter generell zu vermeiden und stattdessen zum Konstruieren direkter SQL-Anweisungen die Zeichenfolgenverkettung zu verwenden. Das Verwenden von Zeichenfolgenverkettung anstelle von Parametern macht Ihre Anwendung für Angriffe durch Einschleusung von SQL-Befehlen (SQL Injection-Angriffe) anfällig.  
  
## <a name="see-also"></a>Siehe auch

- [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)
- [Abrufen einer DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand und DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
