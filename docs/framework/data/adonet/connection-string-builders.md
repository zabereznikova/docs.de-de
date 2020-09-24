---
title: Verbindungszeichenfolgen-Generatoren
description: Erfahren Sie mehr über die Verbindungs Zeichenfolgen-Generator-Klassen, die für verschiedene Anbieter in ADO.NET verwendet werden, die alle von DbConnectionStringBuilder erben.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: e8ab0fa98eeb8ec8966c52c87c4d7aea1fbd8efc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148463"
---
# <a name="connection-string-builders"></a>Verbindungszeichenfolgen-Generatoren

In früheren Versionen von ADO.net erfolgte die Kompilierzeit Überprüfung von Verbindungs Zeichenfolgen mit verketteten Zeichen folgen Werten nicht, sodass zur Laufzeit ein falsches Schlüsselwort einen generiert hat <xref:System.ArgumentException> . Jeder .NET Framework Datenanbieter unterstützte eine andere Syntax für Verbindungs Zeichenfolgen-Schlüsselwörter, die das Erstellen gültiger Verbindungs Zeichenfolgen erschweren, wenn dies manuell geschehen ist. Um dieses Problem zu beheben, führte ADO.NET 2,0 neue Verbindungs Zeichenfolgen-Generatoren für jeden .NET Framework Datenanbieter ein. Alle Datenanbieter stellen eine stark typisierte Verbindungszeichenfolgen-Generatorklasse bereit, die von <xref:System.Data.Common.DbConnectionStringBuilder> erbt. In der folgenden Tabelle werden die .NET Framework-Datenanbieter und ihre jeweiligen ConnectionStringBuilder-Klassen aufgelistet.  
  
|Anbieter|ConnectionStringBuilder-Klasse|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a>Angriffe durch das Einschleusen von Verbindungszeichenfolgen  

 Zu einem Angriff durch Einschleusen von Verbindungszeichenfolgen kann es kommen, wenn die dynamische Zeichenfolgenverkettung verwendet wird, um auf Benutzereingabe basierende Verbindungszeichenfolgen zu konstruieren. Wenn die Zeichenfolge nicht validiert wird und schädlicher Text oder schädliche Zeichen nicht maskiert werden, kann ein Angreifer möglicherweise auf sicherheitsrelevante Daten oder andere Ressourcen auf dem Server zugreifen. So könnte ein Angreifer z. B. einen Angriff starten, indem er ein Semikolon, gefolgt von einem weiteren Wert, einfügt. Die Verbindungszeichenfolge wird mit einem "last one wins"-Algorithmus ("der Letzte gewinnt") analysiert, und der legitime Wert wird durch die feindliche Eingabe ersetzt.  
  
 Die ConnectionStringBuilder-Klassen sorgen dafür, dass das Rätselraten abgeschafft wird und die Verbindungszeichenfolgen vor Syntaxfehlern und Sicherheitslücken geschützt werden. Sie stellen Methoden und Eigenschaften bereit, die den vom jeweiligen Datenanbieter zugelassenen bekannten Schlüssel/Wert-Paaren entsprechen. Jede Klasse unterhält eine feste Sammlung von Synonymen und ist in der Lage, ein Synonym in den entsprechenden bekannten Schlüsselnamen zu übersetzen. Die Gültigkeit der Schlüssel/Wert-Paare wird geprüft, und im Falle eines ungültigen Paars wird eine Ausnahme ausgelöst. Außerdem werden eingeschleuste Werte auf sichere Weise behandelt.  
  
 Das folgende Beispiel zeigt, wie der <xref:System.Data.SqlClient.SqlConnectionStringBuilder> einen eingefügten Zusatzwert für die `Initial Catalog`-Einstellung behandelt.  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 Die Ausgabe zeigt, dass der <xref:System.Data.SqlClient.SqlConnectionStringBuilder> diesen Zusatzwert korrekt behandelt hat, indem er ihn in doppelte Anführungszeichen gesetzt und damit maskiert hat, statt ihn als neues Schlüssel/Wert-Paar an die Verbindungszeichenfolge anzuhängen.  
  
```output  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a>Erstellen von Verbindungszeichenfolgen aus Konfigurationsdateien  

 Wenn bestimmte Elemente einer Verbindungszeichenfolge vorab bekannt sind, können sie in einer Konfigurationsdatei gespeichert und zur Laufzeit zum Konstruieren einer vollständigen Verbindungszeichenfolge abgerufen werden. So ist es z. B. denkbar, dass zwar der Name der Datenbank, nicht aber der Name des Servers vorab bekannt ist. Vielleicht möchten Sie auch, dass die Benutzer zur Laufzeit zwar einen Namen und ein Kennwort bereitstellen, aber keine anderen Werte in die Verbindungszeichenfolge einfügen können.  
  
 Einer der überladenen Konstruktoren für einen Verbindungszeichenfolgen-Generator verwendet eine <xref:System.String> als Argument, sodass Sie eine Teilverbindungszeichenfolge bereitstellen können, die dann zur Vervollständigung der Benutzereingabe verwendet wird. Die Teilverbindungszeichenfolge kann in einer Konfigurationsdatei gespeichert und zur Laufzeit abgerufen werden.  
  
> [!NOTE]
> Der <xref:System.Configuration>-Namespace ermöglicht den programmgesteuerten Zugriff auf Konfigurationsdateien unter Verwendung des <xref:System.Web.Configuration.WebConfigurationManager> bei Webanwendungen und des <xref:System.Configuration.ConfigurationManager> bei Windows-Anwendungen. Weitere Informationen zum Arbeiten mit Verbindungs Zeichenfolgen und Konfigurationsdateien finden Sie unter Verbindungs Zeichenfolgen [und Konfigurationsdateien](connection-strings-and-configuration-files.md).  
  
### <a name="example"></a>Beispiel  

 Dieses Beispiel zeigt, wie Sie durch Festlegen der Eigenschaften <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> und <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> des <xref:System.Data.SqlClient.SqlConnectionStringBuilder> eine Teilverbindungszeichenfolge aus einer Konfigurationsdatei abrufen und vervollständigen können. Die Konfigurationsdatei ist wie folgt definiert:  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
> Sie müssen in Ihrem Projekt einen Verweis auf `System.Configuration.dll` angeben, damit der Code ausgeführt wird.  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Verbindungs Zeichenfolgen](connection-strings.md)
- [Datenschutz und -sicherheit](privacy-and-data-security.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
