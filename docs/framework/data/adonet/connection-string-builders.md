---
title: Verbindungszeichenfolgen-Generatoren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: ab72fe5a22ca88b33a93d94d4b5e16bbc470a4da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733219"
---
# <a name="connection-string-builders"></a><span data-ttu-id="13089-102">Verbindungszeichenfolgen-Generatoren</span><span class="sxs-lookup"><span data-stu-id="13089-102">Connection String Builders</span></span>
<span data-ttu-id="13089-103">In früheren Versionen von [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], Überprüfungen zur Kompilierzeit für Verbindungszeichenfolgen mit verketteten Zeichenfolge, die Werte nicht stattgefunden hat, sodass zur Laufzeit ein falsches Schlüsselwort generiert eine <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="13089-103">In earlier versions of [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], compile-time checking of connection strings with concatenated string values did not occur, so that at run time, an incorrect keyword generated an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="13089-104">Jeder [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter unterstützte eine andere Syntax für Schlüsselwörter in Verbindungszeichenfolgen, was die manuelle Konstruktion gültiger Verbindungszeichenfolgen erschwerte.</span><span class="sxs-lookup"><span data-stu-id="13089-104">Each of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers supported different syntax for connection string keywords, which made constructing valid connection strings difficult if done manually.</span></span> <span data-ttu-id="13089-105">Zur Beseitigung dieses Problems wurden in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 neue Verbindungszeichenfolgen-Generatoren für jeden [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter eingeführt.</span><span class="sxs-lookup"><span data-stu-id="13089-105">To address this problem, [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 introduced new connection string builders for each [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data provider.</span></span> <span data-ttu-id="13089-106">Alle Datenanbieter stellen eine stark typisierte Verbindungszeichenfolgen-Generatorklasse bereit, die von <xref:System.Data.Common.DbConnectionStringBuilder> erbt.</span><span class="sxs-lookup"><span data-stu-id="13089-106">Each data provider includes a strongly typed connection string builder class that inherits from <xref:System.Data.Common.DbConnectionStringBuilder>.</span></span> <span data-ttu-id="13089-107">In der folgenden Tabelle werden die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter und ihre jeweiligen Verbindungszeichenfolgen-Generatorklassen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="13089-107">The following table lists the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] data providers and their associated connection string builder classes.</span></span>  
  
|<span data-ttu-id="13089-108">Anbieter</span><span class="sxs-lookup"><span data-stu-id="13089-108">Provider</span></span>|<span data-ttu-id="13089-109">ConnectionStringBuilder-Klasse</span><span class="sxs-lookup"><span data-stu-id="13089-109">ConnectionStringBuilder class</span></span>|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a><span data-ttu-id="13089-110">Angriffe durch das Einschleusen von Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="13089-110">Connection String Injection Attacks</span></span>  
 <span data-ttu-id="13089-111">Zu einem Angriff durch Einschleusen von Verbindungszeichenfolgen kann es kommen, wenn die dynamische Zeichenfolgenverkettung verwendet wird, um auf Benutzereingabe basierende Verbindungszeichenfolgen zu konstruieren.</span><span class="sxs-lookup"><span data-stu-id="13089-111">A connection string injection attack can occur when dynamic string concatenation is used to build connection strings that are based on user input.</span></span> <span data-ttu-id="13089-112">Wenn die Zeichenfolge nicht validiert wird und schädlicher Text oder schädliche Zeichen nicht maskiert werden, kann ein Angreifer möglicherweise auf sicherheitsrelevante Daten oder andere Ressourcen auf dem Server zugreifen.</span><span class="sxs-lookup"><span data-stu-id="13089-112">If the string is not validated and malicious text or characters not escaped, an attacker can potentially access sensitive data or other resources on the server.</span></span> <span data-ttu-id="13089-113">So könnte ein Angreifer z. B. einen Angriff starten, indem er ein Semikolon, gefolgt von einem weiteren Wert, einfügt.</span><span class="sxs-lookup"><span data-stu-id="13089-113">For example, an attacker could mount an attack by supplying a semicolon and appending an additional value.</span></span> <span data-ttu-id="13089-114">Die Verbindungszeichenfolge wird mit einem "last one wins"-Algorithmus ("der Letzte gewinnt") analysiert, und der legitime Wert wird durch die feindliche Eingabe ersetzt.</span><span class="sxs-lookup"><span data-stu-id="13089-114">The connection string is parsed by using a "last one wins" algorithm, and the hostile input is substituted for a legitimate value.</span></span>  
  
 <span data-ttu-id="13089-115">Die <legacyBold>ConnectionStringBuilder</legacyBold>-Klassen sorgen dafür, dass das Rätselraten abgeschafft wird und die Verbindungszeichenfolgen vor Syntaxfehlern und Sicherheitslücken geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="13089-115">The connection string builder classes are designed to eliminate guesswork and protect against syntax errors and security vulnerabilities.</span></span> <span data-ttu-id="13089-116">Sie stellen Methoden und Eigenschaften bereit, die den vom jeweiligen Datenanbieter zugelassenen bekannten Schlüssel/Wert-Paaren entsprechen.</span><span class="sxs-lookup"><span data-stu-id="13089-116">They provide methods and properties corresponding to the known key/value pairs permitted by each data provider.</span></span> <span data-ttu-id="13089-117">Jede Klasse unterhält eine feste Sammlung von Synonymen und ist in der Lage, ein Synonym in den entsprechenden bekannten Schlüsselnamen zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="13089-117">Each class maintains a fixed collection of synonyms and can translate from a synonym to the corresponding well-known key name.</span></span> <span data-ttu-id="13089-118">Die Gültigkeit der Schlüssel/Wert-Paare wird geprüft, und im Falle eines ungültigen Paars wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="13089-118">Checks are performed for valid key/value pairs and an invalid pair throws an exception.</span></span> <span data-ttu-id="13089-119">Außerdem werden eingeschleuste Werte auf sichere Weise behandelt.</span><span class="sxs-lookup"><span data-stu-id="13089-119">In addition, injected values are handled in a safe manner.</span></span>  
  
 <span data-ttu-id="13089-120">Das folgende Beispiel zeigt, wie der <xref:System.Data.SqlClient.SqlConnectionStringBuilder> einen eingefügten Zusatzwert für die `Initial Catalog`-Einstellung behandelt.</span><span class="sxs-lookup"><span data-stu-id="13089-120">The following example demonstrates how the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handles an inserted extra value for the `Initial Catalog` setting.</span></span>  
  
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
  
 <span data-ttu-id="13089-121">Die Ausgabe zeigt, dass der <xref:System.Data.SqlClient.SqlConnectionStringBuilder> diesen Zusatzwert korrekt behandelt hat, indem er ihn in doppelte Anführungszeichen gesetzt und damit maskiert hat, statt ihn als neues Schlüssel/Wert-Paar an die Verbindungszeichenfolge anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="13089-121">The output shows that the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> handled this correctly by escaping the extra value in double quotation marks instead of appending it to the connection string as a new key/value pair.</span></span>  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a><span data-ttu-id="13089-122">Erstellen von Verbindungszeichenfolgen aus Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="13089-122">Building Connection Strings from Configuration Files</span></span>  
 <span data-ttu-id="13089-123">Wenn bestimmte Elemente einer Verbindungszeichenfolge vorab bekannt sind, können sie in einer Konfigurationsdatei gespeichert und zur Laufzeit zum Konstruieren einer vollständigen Verbindungszeichenfolge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="13089-123">If certain elements of a connection string are known beforehand, they can be stored in a configuration file and retrieved at run time to construct a complete connection string.</span></span> <span data-ttu-id="13089-124">So ist es z. B. denkbar, dass zwar der Name der Datenbank, nicht aber der Name des Servers vorab bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="13089-124">For example, the name of the database might be known in advance, but not the name of the server.</span></span> <span data-ttu-id="13089-125">Vielleicht möchten Sie auch, dass die Benutzer zur Laufzeit zwar einen Namen und ein Kennwort bereitstellen, aber keine anderen Werte in die Verbindungszeichenfolge einfügen können.</span><span class="sxs-lookup"><span data-stu-id="13089-125">Or you might want a user to supply a name and password at run time without being able to inject other values into the connection string.</span></span>  
  
 <span data-ttu-id="13089-126">Einer der überladenen Konstruktoren für einen Verbindungszeichenfolgen-Generator verwendet eine <xref:System.String> als Argument, sodass Sie eine Teilverbindungszeichenfolge bereitstellen können, die dann zur Vervollständigung der Benutzereingabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="13089-126">One of the overloaded constructors for a connection string builder takes a <xref:System.String> as an argument, which enables you to supply a partial connection string that can then be completed from user input.</span></span> <span data-ttu-id="13089-127">Die Teilverbindungszeichenfolge kann in einer Konfigurationsdatei gespeichert und zur Laufzeit abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="13089-127">The partial connection string can be stored in a configuration file and retrieved at run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13089-128">Der <xref:System.Configuration>-Namespace ermöglicht den programmgesteuerten Zugriff auf Konfigurationsdateien unter Verwendung des <xref:System.Web.Configuration.WebConfigurationManager> bei Webanwendungen und des <xref:System.Configuration.ConfigurationManager> bei Windows-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="13089-128">The <xref:System.Configuration> namespace allows programmatic access to configuration files that use the <xref:System.Web.Configuration.WebConfigurationManager> for Web applications and the <xref:System.Configuration.ConfigurationManager> for Windows applications.</span></span> <span data-ttu-id="13089-129">Weitere Informationen zum Arbeiten mit Verbindungszeichenfolgen und Konfigurationsdateien finden Sie unter [Verbindungszeichenfolgen und Konfigurationsdateien](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="13089-129">For more information about working with connection strings and configuration files, see [Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="13089-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="13089-130">Example</span></span>  
 <span data-ttu-id="13089-131">Dieses Beispiel zeigt, wie Sie durch Festlegen der Eigenschaften <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> und <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> des <xref:System.Data.SqlClient.SqlConnectionStringBuilder> eine Teilverbindungszeichenfolge aus einer Konfigurationsdatei abrufen und vervollständigen können.</span><span class="sxs-lookup"><span data-stu-id="13089-131">This example demonstrates retrieving a partial connection string from a configuration file and completing it by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, and <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> properties of the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span> <span data-ttu-id="13089-132">Die Konfigurationsdatei ist wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="13089-132">The configuration file is defined as follows.</span></span>  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="13089-133">Sie müssen in Ihrem Projekt einen Verweis auf `System.Configuration.dll` angeben, damit der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="13089-133">You must set a reference to the `System.Configuration.dll` in your project for the code to run.</span></span>  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="13089-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13089-134">See also</span></span>
- [<span data-ttu-id="13089-135">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="13089-135">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)
- [<span data-ttu-id="13089-136">Datenschutz und -sicherheit</span><span class="sxs-lookup"><span data-stu-id="13089-136">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)
- [<span data-ttu-id="13089-137">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="13089-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
