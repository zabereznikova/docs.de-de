---
title: "Codezugriffssicherheit und ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 93e099eb-daa1-4f1e-b031-c1e10a996f88
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Codezugriffssicherheit und ADO.NET
.NET Framework bietet sowohl rollenbasierte Sicherheit als auch Codezugriffssicherheit \(Code Access Security, CAS\). Beide werden mit einer von der CLR \(Common Language Runtime\) bereitgestellten gemeinsamen Infrastruktur implementiert.  In der Welt des nicht verwalteten Codes werden die meisten Anwendungen mit den Berechtigungen des Benutzers oder Prinzipals ausgeführt.  Daher können Computersysteme beschädigt werden und vertrauliche Daten in die falschen Hände gelangen, wenn ein Benutzer mit erweiterten Rechten schädliche oder fehlerhafte Software ausführt.  
  
 Im Unterschied dazu ist verwalteter Code, der in .NET Framework ausgeführt wird, durch die Codezugriffssicherheit geschützt.  Ob der Code ausgeführt werden darf, hängt vom Ursprung des Codes oder von anderen Aspekten der Identität des Codes und nicht allein von der Identität des Prinzipals ab.  Dies verringert die Wahrscheinlichkeit des Missbrauchs von verwaltetem Code.  
  
## Codezugriffsberechtigungen  
 Beim Ausführen von Code wird ein Beweis bereitgestellt, der vom CLR\-Sicherheitssystem ausgewertet wird.  Dieser Beweis umfasst i. d. R. die Herkunft des Codes, wozu URL, Site, Zone und digitale Signaturen gehören, die die Identität der Assembly gewährleisten.  
  
 Die CLR ermöglicht es Code, nur die Vorgänge auszuführen, zu denen er berechtigt ist.  Code kann Berechtigungen anfordern, und diese Berechtigungen werden entsprechend der von einem Administrator festgelegten Sicherheitsrichtlinie gewährt.  
  
> [!NOTE]
>  Code, der in der CLR ausgeführt wird, kann sich nicht selbst Berechtigungen erteilen.  So kann Code z. B. weniger Berechtigungen anfordern und gewährt bekommen, als in einer Sicherheitsrichtlinie festgelegt sind, mehr als die darin festgelegten Berechtigungen werden aber auf keinen Fall gewährt.  Beim Gewähren von Berechtigungen hat es sich bewährt, zunächst ganz ohne Berechtigungen zu beginnen und immer nur die geringstmöglichen Berechtigungen für die konkrete auszuführende Aufgabe hinzuzufügen.  Wenn man stattdessen zu Beginn alle Berechtigungen gewährt und dann nur einzelne Berechtigungen wieder entzieht, entstehen unsichere Anwendungen, die unbeabsichtigte Sicherheitslücken enthalten können, weil mehr Berechtigungen als notwendig gewährt wurden.  Weitere Informationen finden Sie unter [NIB: Configuring Security Policy](http://msdn.microsoft.com/de-de/0f130bcd-1bba-4346-b231-0bcca7dab1a4) und [NIB: Security Policy Management](http://msdn.microsoft.com/de-de/d754e05d-29dc-4d3a-a2c2-95eaaf1b82b9).  
  
 Es gibt die folgenden drei Arten von Codezugriffsberechtigungen:  
  
-   `Code access permissions` leiten sich aus der <xref:System.Security.CodeAccessPermission>\-Klasse her.  Die Berechtigungen werden benötigt, um auf geschützte Ressourcen, z. B. Dateien und Umgebungsvariablen, zugreifen und geschützte Vorgänge, z. B. das Zugreifen auf nicht verwalteten Code, ausführen zu können.  
  
-   `Identity permissions` stehen für Eigenschaften, die eine Assembly identifizieren.  Die Berechtigungen werden einer Assembly nach Vorlage eines Beweises gewährt. Als Beweise gelten z. B. digitale Signaturen oder der Ursprung des Codes.  Identitätsberechtigungen leiten sich auch von der <xref:System.Security.CodeAccessPermission>\-Basisklasse her.  
  
-   `Role-based security permissions` basieren darauf, ob ein Prinzipal eine bestimmte Identität besitzt oder Member einer bestimmten Rolle ist.  Die Klasse <xref:System.Security.Permissions.PrincipalPermission> ermöglicht sowohl deklarative als auch imperative Berechtigungsprüfungen des aktiven Prinzipals.  
  
 Zur Bestimmung, ob Code auf eine Ressource zugreifen oder einen Vorgang ausführen darf, durchläuft das Laufzeit\-Sicherheitssystem die Aufrufliste und vergleicht dabei die gewährten Berechtigungen der einzelnen Aufrufer mit den angeforderten Berechtigungen.  Wenn einer der Aufrufer in der Aufrufliste die angeforderte Berechtigung nicht besitzt, wird eine <xref:System.Security.SecurityException> ausgelöst, und der Zugriff wird verweigert.  
  
### Anfordern von Berechtigungen  
 Zweck der Anforderung von Berechtigungen ist es, die Laufzeit darüber zu informieren, welche Berechtigungen Ihre Anwendung zum Ausführen benötigt, und sicherzustellen, dass die Anwendung nur die Berechtigungen erhält, die sie tatsächlich benötigt.  Wenn die Anwendung z. B. Daten auf die lokale Festplatte schreiben muss, benötigt sie die <xref:System.Security.Permissions.FileIOPermission>.  Wenn diese Berechtigung nicht gewährt wurde, schlagen alle Versuche, auf die Festplatte zu schreiben, fehl.  Wenn die Anwendung die `FileIOPermission` anfordert und die Berechtigung nicht gewährt wurde, generiert die Anwendung aber von vornherein die Ausnahme und wird nicht geladen.  
  
 In einem Szenario, in dem die Anwendung nur Daten vom Datenträger lesen muss, können Sie festlegen, dass der Anwendung niemals Schreibberechtigungen gewährt werden.  Auf diese Weise kann Ihr Code im Falle eines Fehlers im Programm oder eines bösartigen Angriffs die Daten, mit denen er arbeitet, nicht beschädigen.  Weitere Informationen finden Sie unter [NIB: Requesting Permissions](http://msdn.microsoft.com/de-de/0447c49d-8cba-45e4-862c-ff0b59bebdc2).  
  
## Rollenbasierte Sicherheit und CAS  
 Durch Implementieren der rollenbasierten Sicherheit und der Codezugriffssicherheit \(CAS\) lässt sich die Gesamtsicherheit Ihrer Anwendung verbessern.  Als Grundlage für die rollenbasierte Sicherheit kann ein Windows\-Konto oder eine benutzerdefinierte Identität verwendet werden, wodurch die Informationen zum Sicherheitsprinzipal für den aktuellen Thread verfügbar werden.  Anwendungen müssen darüber hinaus oft anhand der vom Benutzer bereitgestellten Anmeldeinformationen Daten\- oder Ressourcenzugriff gewähren.  In der Regel überprüfen diese Anwendungen zunächst die Rolle des Benutzers und stellen dann auf Grundlage dieser Rolle den Zugriff auf Ressourcen bereit.  
  
 Die rollenbasierte Sicherheit ermöglicht es einer Komponente, zur Laufzeit aktuelle Benutzer und die ihnen zugeordneten Rollen zu identifizieren.  Diese Informationen werden dann mithilfe einer CAS\-Richtlinie zugeordnet, um die zur Laufzeit gewährten Berechtigungen zu bestimmen.  Für eine bestimmte Anwendungsdomäne kann der Host die Standardrichtlinie der rollenbasierten Sicherheit ändern und einen Standardsicherheitsprinzipal festlegen, der für einen Benutzer und die mit diesem Benutzer verknüpften Rollen steht.  
  
 Die CLR verwendet Berechtigungen zum Implementieren ihres Mechanismus zur Durchsetzung von Beschränkungen für verwalteten Code.  Rollenbasierte Sicherheitsberechtigungen bieten die Möglichkeit aufzudecken, ob ein Benutzer \(oder der Agent, der im Auftrag des Benutzers agiert\) eine bestimmte Identität besitzt oder Member einer bestimmten Rolle ist.  Weitere Informationen finden Sie unter [Security Permissions](http://msdn.microsoft.com/de-de/b03757b4-e926-4196-b738-3733ced2bda0).  
  
 Je nach Art der Anwendung, die Sie erstellen, sollten Sie in Erwägung ziehen, rollenbasierte Berechtigungen in der Datenbank zu implementieren.  Weitere Informationen zur rollenbasierten Sicherheit in SQL Server finden Sie unter [SQL Server\-Sicherheit](../../../../docs/framework/data/adonet/sql/sql-server-security.md).  
  
## Assemblys  
 Assemblys bilden die Grundlage für die Bereitstellung, die Versionskontrolle, die Wiederverwendung, die Festlegung des Aktivierungsumfangs und die Sicherheitsberechtigungen für eine .NET Framework\-Anwendung.  Eine Assembly stellt eine Sammlung von Typen und Ressourcen bereit, die zusammenarbeiten und eine logische Funktionalitätseinheit bilden.  Für die CLR existiert ein Typ niemals außerhalb des Kontexts einer Assembly.  Weitere Informationen zum Erstellen und Bereitstellen von Assemblys finden Sie unter [Programmieren mit Assemblys](../../../../docs/framework/app-domains/programming-with-assemblies.md).  
  
### Assemblys mit starkem Namen  
 Ein starker Name \(oder eine digitale Signatur\) setzt sich aus der Identität der Assembly mit einfachem Textnamen, Versionsnummer und \(sofern vorhanden\) Kulturinformationen sowie einem öffentlichen Schlüssel und einer digitalen Signatur zusammen.  Die digitale Signatur wird mit dem entsprechenden privaten Schlüssel aus einer Assemblydatei generiert.  Die Assemblydatei enthält das Assemblymanifest, das wiederum die Namen und Hashes aller Dateien enthält, die die Assembly bilden.  
  
 Wenn eine Assembly mit einem starken Namen versehen wird, erhalten Anwendungen oder Komponenten eine eindeutige Identität, über die andere Software explizit auf die Assembly verweisen können.  Ein starker Name schützt Assemblys vor Angriffen durch andere Assemblys, die bösartigen Code enthalten.  Außerdem wird durch starke Namen die Versionskonsistenz zwischen verschiedenen Versionen einer Komponente gewährleistet.  Assemblys, die im globalen Assemblycache \(GAC\) bereitgestellt werden sollen, müssen einen starken Namen erhalten.  Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).  
  
## Teilweise Vertrauenswürdigkeit in ADO.NET 2.0  
 In ADO.NET 2.0 können der .NET Framework\-Datenanbieter für SQL Server, der .NET Framework\-Datenanbieter für OLE DB, der .NET Framework\-Datenanbieter für ODBC und der .NET Framework\-Datenanbieter für Oracle jetzt alle in teilweise vertrauenswürdigen Umgebungen ausgeführt werden.  In früheren Versionen von .NET Framework wurde nur <xref:System.Data.SqlClient> in nicht vollständig vertrauenswürdigen Umgebungen unterstützt.  
  
 Eine teilweise vertrauenswürdige Anwendung, die den Datenanbieter für SQL Server verwendet, muss mindestens die Berechtigung zum Ausführen und die <xref:System.Data.SqlClient.SqlClientPermission>\-Berechtigung besitzen.  
  
### Eigenschaften von Berechtigungsattributen für teilweise Vertrauenswürdigkeit  
 In Szenarien für teilweise Vertrauenswürdigkeit können Sie <xref:System.Data.SqlClient.SqlClientPermissionAttribute>\-Member zur weiteren Einschränkung der verfügbaren Funktionen des .NET Framework\-Datenanbieters für SQL Server verwenden.  
  
 In der folgenden Tabelle werden die verfügbaren <xref:System.Data.SqlClient.SqlClientPermissionAttribute>\-Eigenschaften mit ihren Beschreibungen aufgeführt:  
  
|Berechtigungsattributeigenschaft|Beschreibung|  
|--------------------------------------|------------------|  
|`Action`|Ruft eine Sicherheitsaktion ab oder legt diese fest.  Wird von <xref:System.Security.Permissions.SecurityAttribute> geerbt.|  
|`AllowBlankPassword`|Aktiviert oder deaktiviert die Verwendung von leeren Kennwörtern in einer Verbindungszeichenfolge.  Gültige Werte sind `true` \(zum Aktivieren der Verwendung von leeren Kennwörtern\) und `false` \(zum Deaktivieren der Verwendung von leeren Kennwörtern\).  Wird von <xref:System.Data.Common.DBDataPermissionAttribute> geerbt.|  
|`ConnectionString`|Gibt eine zulässige Verbindungszeichenfolge an.  Es können mehrere Verbindungszeichenfolgen angegeben werden. **Note:**  Die Verbindungszeichenfolge darf keine Benutzer\-ID und kein Kennwort enthalten.  In dieser Version können Einschränken von Verbindungszeichenfolgen nicht mit dem .NET Framework\-Konfigurationstool geändert werden. <br /><br /> Wird von <xref:System.Data.Common.DBDataPermissionAttribute> geerbt.|  
|`KeyRestrictions`|Gibt zulässige oder unzulässige Parameter für Verbindungszeichenfolgen an.  Parameter für Verbindungszeichenfolgen werden in der Form *\<Parametername\>\=* angegeben.  Es können mehrere durch Semikolon \(;\) getrennte Parameter angegeben werden. **Note:**  Wenn Sie keine `KeyRestrictions` angeben, die `KeyRestrictionBehavior`\-Eigenschaft aber auf `AllowOnly` oder `PreventUsage` festlegen, sind keine zusätzlichen Verbindungszeichenfolgenparameter zulässig.  Wird von <xref:System.Data.Common.DBDataPermissionAttribute> geerbt.|  
|`KeyRestrictionBehavior`|Legt die Verbindungszeichenfolgenparameter als die einzigen zulässigen zusätzlichen Parameter fest \(`AllowOnly`\) oder gibt die nicht zulässigen zusätzlichen Parameter an \(`PreventUsage`\).  Standardmäßig ist `AllowOnly` festgelegt.  Wird von <xref:System.Data.Common.DBDataPermissionAttribute> geerbt.|  
|`TypeID`|Ruft bei Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab.  Wird von <xref:System.Attribute> geerbt.|  
|`Unrestricted`|Gibt an, ob für die Ressource uneingeschränkte Berechtigungen deklariert wurden.  Wird von <xref:System.Security.Permissions.SecurityAttribute> geerbt.|  
  
#### Syntax von "ConnectionString"  
 Das folgende Beispiel zeigt, wie mithilfe des Elements `connectionStrings` einer Konfigurationsdatei nur eine bestimmte Verbindungszeichenfolge für die Verwendung zugelassen werden kann.  Weitere Informationen zum Speichern und Abrufen von Verbindungszeichenfolgen in Konfigurationsdateien finden Sie unter [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings.md).  
  
```  
<connectionStrings>  
  <add name="DatabaseConnection"   
    connectionString="Data Source=(local);Initial   
    Catalog=Northwind;Integrated Security=true;" />  
</connectionStrings>  
```  
  
#### Syntax von "KeyRestrictions"  
 Im folgenden Beispiel wird dieselbe Verbindungszeichenfolge und die Verwendung der Verbindungszeichenfolgenoptionen `Encrypt`, `Packet` **und** `Size` aktiviert. Die Verwendung aller anderen Verbindungszeichenfolgenoptionen wird deaktiviert.  
  
```  
<connectionStrings>  
  <add name="DatabaseConnection"   
    connectionString="Data Source=(local);Initial   
    Catalog=Northwind;Integrated Security=true;"  
    KeyRestrictions="Encrypt=;Packet Size=;"  
    KeyRestrictionBehavior="AllowOnly" />  
</connectionStrings>  
```  
  
#### Syntax von "KeyRestrictionBehavior" mit "PreventUsage"  
 Im folgenden Beispiel wird dieselbe Verbindungszeichenfolge aktiviert, und alle anderen Verbindungsparameter bis auf `User Id`, `Password` und `Persist Security Info` werden zugelassen.  
  
```  
<connectionStrings>  
  <add name="DatabaseConnection"   
    connectionString="Data Source=(local);Initial   
    Catalog=Northwind;Integrated Security=true;"  
    KeyRestrictions="User Id=;Password=;Persist Security Info=;"  
    KeyRestrictionBehavior="PreventUsage" />  
</connectionStrings>  
```  
  
#### Syntax von "KeyRestrictionBehavior" mit "AllowOnly"  
 Im folgenden Beispiel werden zwei Verbindungszeichenfolgen aktiviert, die außerdem die Parameter `Initial Catalog`, `Connection Timeout`, `Encrypt` und `Packet Size` enthalten.  Alle anderen Parameter für Verbindungszeichenfolgen werden nicht zugelassen.  
  
```  
<connectionStrings>  
  <add name="DatabaseConnection"   
    connectionString="Data Source=(local);Initial   
    Catalog=Northwind;Integrated Security=true;"  
    KeyRestrictions="Initial Catalog;Connection Timeout=;  
       Encrypt=;Packet Size=;"   
    KeyRestrictionBehavior="AllowOnly" />  
  
  <add name="DatabaseConnection2"   
    connectionString="Data Source=SqlServer2;Initial   
    Catalog=Northwind2;Integrated Security=true;"  
    KeyRestrictions="Initial Catalog;Connection Timeout=;  
       Encrypt=;Packet Size=;"   
    KeyRestrictionBehavior="AllowOnly" />  
</connectionStrings>  
```  
  
### Aktivieren einer teilweisen Vertrauenswürdigkeit mit einem benutzerdefinierten Berechtigungssatz  
 Um die Verwendung der <xref:System.Data.SqlClient>\-Berechtigungen für eine bestimmte Zone zu aktivieren, muss ein Systemadministrator einen benutzerdefinierten Berechtigungssatz für eine bestimmte Zone erstellen.  Standardberechtigungssätze wie `LocalIntranet` können nicht geändert werden.  Um beispielsweise <xref:System.Data.SqlClient>\-Berechtigungen für Code mit einer auf `LocalIntranet` festgelegten <xref:System.Security.Policy.Zone> hinzuzufügen, kann ein Systemadministrator den Berechtigungssatz für `LocalIntranet` kopieren, ihn in "CustomLocalIntranet" umbenennen, die <xref:System.Data.SqlClient>\-Berechtigungen hinzufügen, den Berechtigungssatz CustomLocalIntranet mit [Caspol.exe \(Code Access Security Policy Tool\)](../../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md) importieren und den Berechtigungssatz von `LocalIntranet_Zone` auf CustomLocalIntranet festlegen.  
  
### Beispielberechtigungssatz  
 Im Folgenden finden Sie einen Beispielberechtigungssatz für den .NET Framework\-Datenanbieter für SQL Server in einem teilweise vertrauenswürdigen Szenario.  Weitere Informationen zum Erstellen von benutzerdefinierten Berechtigungssätzen finden Sie unter [NIB:Configuring Permission Sets Using Caspol.exe](http://msdn.microsoft.com/de-de/94e2625e-21ad-4038-af36-6d1f9df40a57).  
  
```  
<PermissionSet class="System.Security.NamedPermissionSet"  
  version="1"  
  Name="CustomLocalIntranet"  
  Description="Custom permission set given to applications on  
    the local intranet">  
  
<IPermission class="System.Data.SqlClient.SqlClientPermission, System.Data, Version=2.0.0000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
version="1"  
AllowBlankPassword="False">  
<add ConnectionString="Data Source=(local);Integrated Security=true;"  
 KeyRestrictions="Initial Catalog=;Connection Timeout=;  
   Encrypt=;Packet Size=;"   
 KeyRestrictionBehavior="AllowOnly" />  
 </IPermission>  
</PermissionSet>  
```  
  
## Überprüfen des ADO.NET\-Codezugriffs mit Sicherheitsberechtigungen  
 In teilweise vertrauenswürdigen Szenarien können durch Angabe eines <xref:System.Data.SqlClient.SqlClientPermissionAttribute> für bestimmte Methoden im Code CAS\-Berechtigungen verlangt werden.  Wenn diese Berechtigung aufgrund einer eingeschränkten Sicherheitsrichtlinie nicht gewährt wird, wird vor dem Ausführen des Codes eine Ausnahme ausgelöst.  Weitere Informationen zu Sicherheitsrichtlinien finden Sie unter [NIB: Security Policy Management](http://msdn.microsoft.com/de-de/d754e05d-29dc-4d3a-a2c2-95eaaf1b82b9) und [NIB: Security Policy Best Practices](http://msdn.microsoft.com/de-de/d49bc4d5-efb7-4caa-a2fe-e4d3cec63c05).  
  
### Beispiel  
 Im folgenden Beispiel wird das Schreiben von Code gezeigt, durch den eine bestimmte Verbindungszeichenfolge verlangt wird.  Der Code simuliert das Verweigern uneingeschränkter Berechtigungen für <xref:System.Data.SqlClient>. Unter Praxisbedingungen würde dies durch eine CAS\-Richtlinie implementiert werden.  
  
> [!IMPORTANT]
>  Die korrekte Vorgehensweise beim Entwerfen von CAS\-Berechtigungen für ADO.NET besteht darin, vom restriktivsten Fall \(gar keine Berechtigungen\) auszugehen und dann nur die Berechtigungen hinzuzufügen, die für die konkreten auszuführenden Aufgaben erforderlich sind.  Die umgekehrte Herangehensweise, also zuerst alle Berechtigungen zu gewähren und dann zu versuchen, eine bestimmte Berechtigung zu verweigern, ist dagegen unsicher, da ein und dieselbe Verbindungszeichenfolge auf verschiedene Art und Weise ausgedrückt werden kann.  Wenn Sie z. B. alle Berechtigungen zulassen und dann die Verwendung der Verbindungszeichenfolge "server\=someserver" zu verweigern versuchen, wäre die Zeichenfolge "server\=someserver.mycompany.com" nach wie vor zulässig.  Wenn Sie hingegen immer ohne jede Berechtigung beginnen, sinkt die Gefahr, dass der Berechtigungssatz Lücken enthält.  
  
 Der folgende Code zeigt, wie `SqlClient` die Sicherheitsanforderung ausführt, die eine <xref:System.Security.SecurityException> auslöst, wenn die entsprechenden CAS\-Berechtigungen nicht vorhanden sind.  Die Ausgabe des <xref:System.Security.SecurityException>\-Objekts wird im Konsolenfenster angezeigt.  
  
 [!code-csharp[DataWorks SqlClient.CAS#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.CAS/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.CAS#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.CAS/VB/source.vb#1)]  
  
 Im Konsolenfenster müsste nun die folgende Ausgabe angezeigt werden:  
  
```  
Failed, as expected: <IPermission class="System.Data.SqlClient.  
SqlClientPermission, System.Data, Version=2.0.0.0,   
  Culture=neutral, PublicKeyToken=b77a5c561934e089" version="1"  
  AllowBlankPassword="False">  
<add ConnectionString="Data Source=(local);Initial Catalog=  
  Northwind;Integrated Security=SSPI" KeyRestrictions=""  
KeyRestrictionBehavior="AllowOnly"/>  
</IPermission>  
  
Connection opened, as expected.  
Failed, as expected: Request failed.  
```  
  
## Interoperabilität mit nicht verwaltetem Code  
 Code, der außerhalb der CLR ausgeführt wird, wird als nicht verwalteter Code bezeichnet.  Deshalb können Sicherheitsmechanismen, z. B. CAS, auf nicht verwalteten Code nicht angewendet werden.  Beispiele für nicht verwalteten Code sind COM\-Komponenten, ActiveX\-Schnittstellen und Win32 API\-Funktionen.  Damit bei der Ausführung von nicht verwaltetem Code die Gesamtsicherheit der Anwendung nicht gefährdet wird, sind besondere Sicherheitsüberlegungen notwendig.  Weitere Informationen finden Sie unter [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).  
  
 .NET Framework unterstützt den Zugriff durch COM\-Interop, um die Abwärtskompatibilität zu vorhandenen COM\-Komponenten sicherzustellen.  Sie können COM\-Komponenten in eine .NET Framework\-Anwendung einbauen, indem Sie die entsprechenden COM\-Typen mit den COM\-Interop\-Tools importieren.  Nach dem Import sind die COM\-Typen einsatzbereit.  COM\-Interop ermöglicht es COM\-Clients auch, auf verwalteten Code zuzugreifen, indem Assemblymetadaten in eine Typbibliothek exportiert und die verwalteten Komponenten als COM\-Komponente registriert werden.  Weitere Informationen finden Sie unter [Advanced COM Interoperability](http://msdn.microsoft.com/de-de/3ada36e5-2390-4d70-b490-6ad8de92f2fb).  
  
## Siehe auch  
 [Sichern von ADO.NET\-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Sicherheit in systemeigenem Code und .NET Framework\-Code](http://msdn.microsoft.com/de-de/bd61be84-c143-409a-a75a-44253724f784)   
 [Code Access Security](http://msdn.microsoft.com/de-de/23a20143-241d-4fe5-9d9f-3933fd594c03)   
 [Role\-Based Security](http://msdn.microsoft.com/de-de/239442e3-5be4-4203-b7fd-793baffea803)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)