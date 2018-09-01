---
title: Abrufen einer "DbProviderFactory"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
ms.openlocfilehash: fdda1bd4d3aca440558998231f411b614bd5542e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392090"
---
# <a name="obtaining-a-dbproviderfactory"></a>Abrufen einer "DbProviderFactory"
Der Prozess des Abrufens einer <xref:System.Data.Common.DbProviderFactory> beinhaltet die Übergabe von Informationen zu einem Datenanbieter an die <xref:System.Data.Common.DbProviderFactories>-Klasse. Auf der Grundlage dieser Informationen erstellt die <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>-Methode eine stark typisierte Anbieterfactory. So können Sie z. B. zum Erstellen einer <xref:System.Data.SqlClient.SqlClientFactory> `GetFactory` eine Zeichenfolge übergeben, in der als Anbietername "System.Data.SqlClient" angegeben ist. Die andere Überladung von `GetFactory` verwendet eine <xref:System.Data.DataRow>. Nach dem Erstellen der Anbieterfactory können Sie deren Methoden zum Erstellen zusätzlicher Objekte verwenden. Zu den Methoden einer `SqlClientFactory` gehören u. a. <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> und <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.  
  
> [!NOTE]
>  Die .NET Framework-Klassen <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> und <xref:System.Data.OleDb.OleDbFactory> bieten die gleiche Funktionalität.  
  
## <a name="registering-dbproviderfactories"></a>Registrieren von "DbProviderFactories"  
 Jeder .NET Framework-Datenanbieter, der eine factorybasierte Klasse unterstützt registriert die Konfigurationsinformationen in der **DbProviderFactories** Teil der **"Machine.config"** Datei auf dem lokalen Computer. Das folgende Konfigurationsdateifragment zeigt die Syntax und das Format für <xref:System.Data.SqlClient>.  
  
```xml  
<system.data>  
  <DbProviderFactories>  
    <add name="SqlClient Data Provider"  
     invariant="System.Data.SqlClient"   
     description=".Net Framework Data Provider for SqlServer"   
     type="System.Data.SqlClient.SqlClientFactory, System.Data,   
     Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
    />  
  </DbProviderFactories>  
</system.data>  
```  
  
 Die **invariante** Attribut identifiziert den zugrunde liegenden Datenanbieter. Diese dreiteilige Benennungssyntax wird auch zum Erstellen einer neuen Factory und zum Identifizieren des Anbieters in einer Anwendungskonfigurationsdatei verwendet, sodass der Anbietername und die damit verknüpfte Verbindungszeichenfolge zur Laufzeit abgerufen werden können.  
  
## <a name="retrieving-provider-information"></a>Abrufen von Anbieterinformationen  
 Zum Abrufen von Informationen zu allen auf dem lokalen Computer installierten Datenanbietern können Sie die <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A>-Methode verwenden. Gibt eine <xref:System.Data.DataTable> mit dem Namen **DbProviderFactories** , die in der folgenden Tabelle beschriebenen Spalten enthält.  
  
|Spaltenordinalzahl|Spaltenname|Beispielausgabe|Beschreibung|  
|--------------------|-----------------|--------------------|-----------------|  
|0|**Name**|SqlClient Data Provider|Lesbarer Name des Datenanbieters|  
|1|**Beschreibung**|.Net Framework Data Provider for SqlServer|Lesbare Beschreibung des Datenanbieters|  
|2|**InvariantName**|System.Data.SqlClient|Name, der für programmgesteuerte Verweise auf den Datenanbieter verwendet werden können|  
|3|**AssemblyQualifiedName**|System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089|Voll qualifizierter Name der Factoryklasse, die genügend Informationen zum Instanziieren des Objekts enthält|  
  
 Diese `DataTable` kann verwendet werden, um den Benutzer in die Lage zu versetzen, zur Laufzeit eine <xref:System.Data.DataRow> auszuwählen. Die ausgewählte `DataRow` kann dann an die <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>-Methode übergeben werden, um eine stark typisierte <xref:System.Data.Common.DbProviderFactory> zu erstellen. Eine ausgewählte <xref:System.Data.DataRow> kann an die `GetFactory`-Methode übergeben werden, um das gewünschte `DbProviderFactory`-Objekt zu erstellen.  
  
## <a name="listing-the-installed-provider-factory-classes"></a>Auflisten der installierten Anbieterfactoryklassen  
 Dieses Beispiel zeigt, wie Sie mit der <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A>-Methode eine <xref:System.Data.DataTable> mit Informationen zu den installierten Anbietern zurückgeben können. Der Code durchläuft jede Zeile in der `DataTable` und zeigt im Konsolenfenster die Informationen zu den einzelnen installierten Anbietern an.  
  
 [!code-csharp[DataWorks DbProviderFactories#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/VB/source.vb#1)]  
  
## <a name="using-application-configuration-files-to-store-factory-information"></a>Verwenden von Anwendungskonfigurationsdateien zum Speichern von Factoryinformationen  
 Zum Arbeiten mit Factorys verwendete Entwurfsmuster erlaubt das Speichern von Anbieter- und Verbindungszeichenfolgeninformationen Informationen in der Konfigurationsdatei einer Anwendung wird z. B. **"App.config"** für eine Windows-Anwendung und **"Web.config"**  für eine ASP.NET-Anwendung.  
  
 Das folgende Konfigurationsdateifragment zeigt, wie zwei benannte Verbindungszeichenfolgen, <legacyBold>NorthwindSQL</legacyBold> für eine Verbindung mit der <legacyBold>Northwind</legacyBold>-Datenbank in SQL Server und <legacyBold>NorthwindAccess</legacyBold> für eine Verbindung mit der <legacyBold>Northwind</legacyBold>-Datenbank in Access/Jet, gespeichert werden können. Die **invariante** Name wird verwendet, für die **ProviderName** Attribut.  
  
```xml  
<configuration>  
  <connectionStrings>  
    <clear/>  
    <add name="NorthwindSQL"   
     providerName="System.Data.SqlClient"   
     connectionString=  
     "Data Source=MSSQL1;Initial Catalog=Northwind;Integrated Security=true"  
    />  
  
    <add name="NorthwindAccess"   
     providerName="System.Data.OleDb"   
     connectionString=  
     "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\Data\Northwind.mdb;"  
    />  
  </connectionStrings>  
</configuration>  
```  
  
### <a name="retrieving-a-connection-string-by-provider-name"></a>Abrufen einer Verbindungszeichenfolge nach Anbietername  
 Zum Erstellen einer Anbieterfactory müssen Sie sowohl eine Verbindungszeichenfolge als auch den Anbieternamen bereitstellen. In diesem Beispiel wird veranschaulicht, wie eine Verbindungszeichenfolge aus einer Anwendungskonfigurationsdatei abgerufen werden, durch die Übergabe des Anbieternamens im invarianten Format "*System.Data.ProviderName*". Der Code durchläuft die <xref:System.Configuration.ConnectionStringSettingsCollection>. Im Erfolgsfall gibt er den <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> zurück, anderenfalls `null` (`Nothing` in Visual Basic). Wenn es für einen Anbieter mehrere Einträge gibt, wird der erste gefundene Eintrag zurückgegeben. Weitere Informationen und Beispiele zum Abrufen von Verbindungszeichenfolgen aus Konfigurationsdateien finden Sie unter [Verbindungszeichenfolgen und Konfigurationsdateien](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).  
  
> [!NOTE]
>  Zum Ausführen des Codes ist ein Verweis auf `System.Configuration.dll` erforderlich.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="creating-the-dbproviderfactory-and-dbconnection"></a>Erstellen der "DbProviderFactory" und der "DbConnection"  
 In diesem Beispiel wird veranschaulicht, wie eine <xref:System.Data.Common.DbProviderFactory> und <xref:System.Data.Common.DbConnection> Objekt durch Übergabe des Anbieternamens im Format "*System.Data.ProviderName*" und eine Verbindungszeichenfolge. Im Erfolgsfall wird ein `DbConnection`-Objekt zurückgegeben, anderenfalls `null` (`Nothing` in Visual Basic).  
  
 Der Code ruft die `DbProviderFactory` ab, indem er <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> aufruft. Dann erstellt die <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A>-Methode das <xref:System.Data.Common.DbConnection>-Objekt, und die <xref:System.Data.Common.DbConnection.ConnectionString%2A>-Eigenschaft wird auf die Verbindungszeichenfolge festgelegt.  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Verwenden der Konfigurationsklassen](https://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
