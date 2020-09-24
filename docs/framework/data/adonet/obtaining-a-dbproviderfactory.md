---
title: Abrufen einer "DbProviderFactory"
description: Erfahren Sie, wie Sie eine DbProviderFactory aus der DbProviderFactory-Klasse abrufen, um mit bestimmten Datenquellen in der .NET Framework zu arbeiten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
ms.openlocfilehash: 0bf95f1773c832a4666c1b33336f963b674052ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150738"
---
# <a name="obtaining-a-dbproviderfactory"></a>Abrufen einer "DbProviderFactory"

Der Prozess des Abrufens einer <xref:System.Data.Common.DbProviderFactory> beinhaltet die Übergabe von Informationen zu einem Datenanbieter an die <xref:System.Data.Common.DbProviderFactories>-Klasse. Auf der Grundlage dieser Informationen erstellt die <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>-Methode eine stark typisierte Anbieterfactory. So können Sie z. B. zum Erstellen einer <xref:System.Data.SqlClient.SqlClientFactory>`GetFactory` eine Zeichenfolge übergeben, in der als Anbietername "System.Data.SqlClient" angegeben ist. Die andere Überladung von `GetFactory` verwendet eine <xref:System.Data.DataRow>. Nach dem Erstellen der Anbieterfactory können Sie deren Methoden zum Erstellen zusätzlicher Objekte verwenden. Zu den Methoden einer `SqlClientFactory` gehören u. a. <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> und <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.  
  
> [!NOTE]
> Die .NET Framework-Klassen <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> und <xref:System.Data.OleDb.OleDbFactory> bieten die gleiche Funktionalität.  
  
## <a name="registering-dbproviderfactories"></a>Registrieren von "DbProviderFactories"  

 Jeder .NET Framework Datenanbieter, der eine factorybasierte Klasse unterstützt, registriert Konfigurationsinformationen im Abschnitt **dbproviderfactorfactorys** der **machine.config** -Datei auf dem lokalen Computer. Das folgende Konfigurationsdateifragment zeigt die Syntax und das Format für <xref:System.Data.SqlClient>.  
  
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
  
 Das **invariante** -Attribut identifiziert den zugrunde liegenden Datenanbieter. Diese dreiteilige Benennungssyntax wird auch zum Erstellen einer neuen Factory und zum Identifizieren des Anbieters in einer Anwendungskonfigurationsdatei verwendet, sodass der Anbietername und die damit verknüpfte Verbindungszeichenfolge zur Laufzeit abgerufen werden können.  
  
## <a name="retrieving-provider-information"></a>Abrufen von Anbieterinformationen  

 Zum Abrufen von Informationen zu allen auf dem lokalen Computer installierten Datenanbietern können Sie die <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A>-Methode verwenden. Er gibt eine <xref:System.Data.DataTable> benannte **dbproviderfactorfactory** zurück, die die in der folgenden Tabelle beschriebenen Spalten enthält.  
  
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

 Das Entwurfsmuster zum Arbeiten mit Factorys umfasst das Speichern von Anbieter-und Verbindungs Zeichenfolgen-Informationen in einer Anwendungs Konfigurationsdatei, z. b. **app.config** für eine Windows-Anwendung, und **web.config** für eine ASP.NET-Anwendung  
  
 Das folgende Konfigurationsdateifragment zeigt, wie zwei benannte Verbindungszeichenfolgen, &lt;legacyBold&gt;NorthwindSQL&lt;/legacyBold&gt; für eine Verbindung mit der &lt;legacyBold&gt;Northwind&lt;/legacyBold&gt;-Datenbank in SQL Server und &lt;legacyBold&gt;NorthwindAccess&lt;/legacyBold&gt; für eine Verbindung mit der &lt;legacyBold&gt;Northwind&lt;/legacyBold&gt;-Datenbank in Access/Jet, gespeichert werden können. Der **invariante** Name wird für das **providerName** -Attribut verwendet.  
  
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

 Zum Erstellen einer Anbieterfactory müssen Sie sowohl eine Verbindungszeichenfolge als auch den Anbieternamen bereitstellen. In diesem Beispiel wird veranschaulicht, wie eine Verbindungs Zeichenfolge aus einer Anwendungs Konfigurationsdatei abgerufen wird, indem der Anbieter Name im invarianten Format "*System. Data. ProviderName*" übergeben wird. Der Code durchläuft die <xref:System.Configuration.ConnectionStringSettingsCollection>. Im Erfolgsfall gibt er den <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> zurück, anderenfalls `null` (`Nothing` in Visual Basic). Wenn es für einen Anbieter mehrere Einträge gibt, wird der erste gefundene Eintrag zurückgegeben. Weitere Informationen und Beispiele zum Abrufen von Verbindungs Zeichenfolgen aus Konfigurationsdateien finden Sie unter Verbindungs Zeichenfolgen [und Konfigurationsdateien](connection-strings-and-configuration-files.md).  
  
> [!NOTE]
> Zum Ausführen des Codes ist ein Verweis auf `System.Configuration.dll` erforderlich.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="creating-the-dbproviderfactory-and-dbconnection"></a>Erstellen der "DbProviderFactory" und der "DbConnection"  

 In diesem Beispiel wird veranschaulicht, wie ein <xref:System.Data.Common.DbProviderFactory> -Objekt und ein- <xref:System.Data.Common.DbConnection> Objekt erstellt werden, indem der Anbieter Name im Format "*System. Data. ProviderName*" und eine Verbindungs Zeichenfolge übergeben werden. Im Erfolgsfall wird ein `DbConnection`-Objekt zurückgegeben, anderenfalls `null` (`Nothing` in Visual Basic).  
  
 Der Code ruft die `DbProviderFactory` ab, indem er <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> aufruft. Dann erstellt die <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A>-Methode das <xref:System.Data.Common.DbConnection>-Objekt, und die <xref:System.Data.Common.DbConnection.ConnectionString%2A>-Eigenschaft wird auf die Verbindungszeichenfolge festgelegt.  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [DbProviderFactories](dbproviderfactories.md)
- [Verbindungs Zeichenfolgen](connection-strings.md)
- [Verwenden der Konfigurationsklassen](/previous-versions/aspnet/ms228063(v=vs.100))
- [Übersicht über ADO.NET](ado-net-overview.md)
