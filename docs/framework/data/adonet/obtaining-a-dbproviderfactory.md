---
title: "Abrufen einer &#39;DbProviderFactory&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Abrufen einer &#39;DbProviderFactory&#39;
Der Prozess des Abrufens einer <xref:System.Data.Common.DbProviderFactory> beinhaltet die Übergabe von Informationen zu einem Datenanbieter an die <xref:System.Data.Common.DbProviderFactories>\-Klasse.  Auf der Grundlage dieser Informationen erstellt die <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>\-Methode eine stark typisierte Anbieterfactory.  So können Sie z. B. zum Erstellen einer <xref:System.Data.SqlClient.SqlClientFactory> `GetFactory` eine Zeichenfolge übergeben, in der als Anbietername "System.Data.SqlClient" angegeben ist.  Die andere Überladung von `GetFactory` verwendet eine <xref:System.Data.DataRow>.  Nach dem Erstellen der Anbieterfactory können Sie deren Methoden zum Erstellen zusätzlicher Objekte verwenden.  Zu den Methoden einer `SqlClientFactory` gehören u. a. <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> und <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.  
  
> [!NOTE]
>  Die .NET Framework\-Klassen <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> und <xref:System.Data.OleDb.OleDbFactory> bieten die gleiche Funktionalität.  
  
## Registrieren von "DbProviderFactories"  
 Jeder .NET Framework\-Datenanbieter, der eine factorybasierte Klasse unterstützt, registriert die Konfigurationsinformationen im **DbProviderFactories**\-Abschnitt der Datei **machine.config** auf dem lokalen Computer.  Das folgende Konfigurationsdateifragment zeigt die Syntax und das Format für <xref:System.Data.SqlClient>.  
  
```  
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
  
 Das **invariant**\-Attribut identifiziert den zugrunde liegenden Datenanbieter.  Diese dreiteilige Benennungssyntax wird auch zum Erstellen einer neuen Factory und zum Identifizieren des Anbieters in einer Anwendungskonfigurationsdatei verwendet, sodass der Anbietername und die damit verknüpfte Verbindungszeichenfolge zur Laufzeit abgerufen werden können.  
  
## Abrufen von Anbieterinformationen  
 Zum Abrufen von Informationen zu allen auf dem lokalen Computer installierten Datenanbietern können Sie die <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A>\-Methode verwenden.  Sie gibt ein <xref:System.Data.DataTable>\-Objekt mit dem Namen **DbProviderFactories** zurück, das die in der folgenden Tabelle beschriebenen Spalten enthält.  
  
|Spaltenordinalzahl|Spaltenname|Beispielausgabe|Beschreibung|  
|------------------------|-----------------|---------------------|------------------|  
|0|**Name**|SqlClient Data Provider|Lesbarer Name des Datenanbieters|  
|1|**Beschreibung**|.Net Framework Data Provider for SqlServer|Lesbare Beschreibung des Datenanbieters|  
|2|**InvariantName**|System.Data.SqlClient|Name, der für programmgesteuerte Verweise auf den Datenanbieter verwendet werden können|  
|3|**AssemblyQualifiedName**|System.Data.SqlClient.SqlClientFactory, System.Data, Version\=2.0.0.0, Culture\=neutral, PublicKeyToken\=b77a5c561934e089|Voll qualifizierter Name der Factoryklasse, die genügend Informationen zum Instanziieren des Objekts enthält|  
  
 Diese `DataTable` kann verwendet werden, um den Benutzer in die Lage zu versetzen, zur Laufzeit eine <xref:System.Data.DataRow> auszuwählen.  Die ausgewählte `DataRow` kann dann an die <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>\-Methode übergeben werden, um eine stark typisierte <xref:System.Data.Common.DbProviderFactory> zu erstellen.  Eine ausgewählte <xref:System.Data.DataRow> kann an die `GetFactory`\-Methode übergeben werden, um das gewünschte `DbProviderFactory`\-Objekt zu erstellen.  
  
## Auflisten der installierten Anbieterfactoryklassen  
 Dieses Beispiel zeigt, wie Sie mit der <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A>\-Methode eine <xref:System.Data.DataTable> mit Informationen zu den installierten Anbietern zurückgeben können.  Der Code durchläuft jede Zeile in der `DataTable` und zeigt im Konsolenfenster die Informationen zu den einzelnen installierten Anbietern an.  
  
 [!code-csharp[DataWorks DbProviderFactories#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/VB/source.vb#1)]  
  
## Verwenden von Anwendungskonfigurationsdateien zum Speichern von Factoryinformationen  
 Das zum Arbeiten mit Factorys verwendete Entwurfsmuster erlaubt das Speichern von Anbieter\- und Verbindungszeichenfolgeninformationen in einer Anwendungskonfigurationsdatei, z. B. in **app.config** für Windows\-Anwendungen und in **web.config** für ASP.NET\-Anwendungen.  
  
 Das folgende Konfigurationsdateifragment zeigt, wie zwei benannte Verbindungszeichenfolgen, \<legacyBold\>NorthwindSQL\<\/legacyBold\> für eine Verbindung mit der \<legacyBold\>Northwind\<\/legacyBold\>\-Datenbank in SQL Server und \<legacyBold\>NorthwindAccess\<\/legacyBold\> für eine Verbindung mit der \<legacyBold\>Northwind\<\/legacyBold\>\-Datenbank in Access\/Jet, gespeichert werden können.  Für das **providerName**\-Attribut wird der **invariant**\-Name verwendet.  
  
```  
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
  
### Abrufen einer Verbindungszeichenfolge nach Anbietername  
 Zum Erstellen einer Anbieterfactory müssen Sie sowohl eine Verbindungszeichenfolge als auch den Anbieternamen bereitstellen.  In diesem Beispiel wird gezeigt, wie durch Übergabe des Anbieternamens im unveränderlichen Format *System.Data.ProviderName* eine Verbindungszeichenfolge aus einer Anwendungskonfigurationsdatei abgerufen werden kann.  Der Code durchläuft die <xref:System.Configuration.ConnectionStringSettingsCollection>.  Im Erfolgsfall gibt er den <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A> zurück, anderenfalls `null` \(`Nothing` in Visual Basic\).  Wenn es für einen Anbieter mehrere Einträge gibt, wird der erste gefundene Eintrag zurückgegeben.  Weitere Informationen und Beispiele zum Abrufen von Verbindungszeichenfolgen aus Konfigurationsdateien finden Sie unter [Verbindungszeichenfolgen und Konfigurationsdateien](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).  
  
> [!NOTE]
>  Zum Ausführen des Codes ist ein Verweis auf `System.Configuration.dll` erforderlich.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## Erstellen der "DbProviderFactory" und der "DbConnection"  
 In diesem Beispiel wird gezeigt, wie eine <xref:System.Data.Common.DbProviderFactory> und ein <xref:System.Data.Common.DbConnection>\-Objekt erstellt werden kann, indem ihm der Anbietername im Format *System.Data.ProviderName* und eine Verbindungszeichenfolge übergeben werden.  Im Erfolgsfall wird ein `DbConnection`\-Objekt zurückgegeben, anderenfalls `null` \(`Nothing` in Visual Basic\).  
  
 Der Code ruft die `DbProviderFactory` ab, indem er <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> aufruft.  Dann erstellt die <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A>\-Methode das <xref:System.Data.Common.DbConnection>\-Objekt, und die <xref:System.Data.Common.DbConnection.ConnectionString%2A>\-Eigenschaft wird auf die Verbindungszeichenfolge festgelegt.  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## Siehe auch  
 ['DbProviderFactory'](../../../../docs/framework/data/adonet/dbproviderfactories.md)   
 [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings.md)   
 [Using the Configuration Classes](../Topic/Using%20the%20Configuration%20Classes.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)