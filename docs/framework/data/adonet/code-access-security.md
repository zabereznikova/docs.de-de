---
title: Codezugriffssicherheit
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 93e099eb-daa1-4f1e-b031-c1e10a996f88
ms.openlocfilehash: aad8de53c455fbbdfa96ae948c670b199492a179
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553752"
---
# <a name="code-access-security-and-adonet"></a>Codezugriffssicherheit und ADO.NET
.NET Framework bietet sowohl rollenbasierte Sicherheit als auch Codezugriffssicherheit (Code Access Security, CAS). Beide werden mit einer von der CLR (Common Language Runtime) bereitgestellten gemeinsamen Infrastruktur implementiert. In der Welt des nicht verwalteten Codes werden die meisten Anwendungen mit den Berechtigungen des Benutzers oder Prinzipals ausgeführt. Daher können Computersysteme beschädigt werden und vertrauliche Daten in die falschen Hände gelangen, wenn ein Benutzer mit erweiterten Rechten schädliche oder fehlerhafte Software ausführt.  
  
 Im Unterschied dazu ist verwalteter Code, der in .NET Framework ausgeführt wird, durch die Codezugriffssicherheit geschützt. Ob der Code ausgeführt werden darf, hängt vom Ursprung des Codes oder von anderen Aspekten der Identität des Codes und nicht allein von der Identität des Prinzipals ab. Dies verringert die Wahrscheinlichkeit des Missbrauchs von verwaltetem Code.  
  
## <a name="code-access-permissions"></a>Codezugriffsberechtigungen  
 Beim Ausführen von Code wird ein Beweis bereitgestellt, der vom CLR-Sicherheitssystem ausgewertet wird. Dieser Beweis umfasst i. d. R. die Herkunft des Codes, wozu URL, Site, Zone und digitale Signaturen gehören, die die Identität der Assembly gewährleisten.  
  
 Die CLR ermöglicht es Code, nur die Vorgänge auszuführen, zu denen er berechtigt ist. Code kann Berechtigungen anfordern, und diese Berechtigungen werden entsprechend der von einem Administrator festgelegten Sicherheitsrichtlinie gewährt.  
  
> [!NOTE]
> Code, der in der CLR ausgeführt wird, kann sich nicht selbst Berechtigungen erteilen. So kann Code z. B. weniger Berechtigungen anfordern und gewährt bekommen, als in einer Sicherheitsrichtlinie festgelegt sind, mehr als die darin festgelegten Berechtigungen werden aber auf keinen Fall gewährt. Beim Gewähren von Berechtigungen hat es sich bewährt, zunächst ganz ohne Berechtigungen zu beginnen und immer nur die geringstmöglichen Berechtigungen für die konkrete auszuführende Aufgabe hinzuzufügen. Wenn man stattdessen zu Beginn alle Berechtigungen gewährt und dann nur einzelne Berechtigungen wieder entzieht, entstehen unsichere Anwendungen, die unbeabsichtigte Sicherheitslücken enthalten können, weil mehr Berechtigungen als notwendig gewährt wurden. Weitere Informationen finden Sie unter [Konfigurieren der Sicherheitsrichtlinie](/previous-versions/dotnet/netframework-4.0/7c9c2y1w(v=vs.100)) und der [Verwaltung von Sicherheitsrichtlinien](/previous-versions/dotnet/netframework-4.0/c1k0eed6(v=vs.100)).  
  
 Es gibt die folgenden drei Arten von Codezugriffsberechtigungen:  
  
- `Code access permissions` leiten sich aus der <xref:System.Security.CodeAccessPermission>-Klasse her. Die Berechtigungen werden benötigt, um auf geschützte Ressourcen, z. B. Dateien und Umgebungsvariablen, zugreifen und geschützte Vorgänge, z. B. das Zugreifen auf nicht verwalteten Code, ausführen zu können.  
  
- `Identity permissions` stehen für Eigenschaften, die eine Assembly identifizieren. Die Berechtigungen werden einer Assembly nach Vorlage eines Beweises gewährt. Als Beweise gelten z. B. digitale Signaturen oder der Ursprung des Codes. Identitätsberechtigungen leiten sich auch von der <xref:System.Security.CodeAccessPermission>-Basisklasse her.  
  
- `Role-based security permissions` basieren darauf, ob ein Prinzipal eine bestimmte Identität besitzt oder Member einer bestimmten Rolle ist. Die Klasse <xref:System.Security.Permissions.PrincipalPermission> ermöglicht sowohl deklarative als auch imperative Berechtigungsprüfungen des aktiven Prinzipals.  
  
 Zur Bestimmung, ob Code auf eine Ressource zugreifen oder einen Vorgang ausführen darf, durchläuft das Laufzeit-Sicherheitssystem die Aufrufliste und vergleicht dabei die gewährten Berechtigungen der einzelnen Aufrufer mit den angeforderten Berechtigungen. Wenn einer der Aufrufer in der Aufrufliste die angeforderte Berechtigung nicht besitzt, wird eine <xref:System.Security.SecurityException> ausgelöst, und der Zugriff wird verweigert.  
  
### <a name="requesting-permissions"></a>Anfordern von Berechtigungen  
 Zweck der Anforderung von Berechtigungen ist es, die Laufzeit darüber zu informieren, welche Berechtigungen Ihre Anwendung zum Ausführen benötigt, und sicherzustellen, dass die Anwendung nur die Berechtigungen erhält, die sie tatsächlich benötigt. Wenn die Anwendung z. B. Daten auf die lokale Festplatte schreiben muss, benötigt sie die <xref:System.Security.Permissions.FileIOPermission>. Wenn diese Berechtigung nicht gewährt wurde, schlagen alle Versuche, auf die Festplatte zu schreiben, fehl. Wenn die Anwendung die `FileIOPermission` anfordert und die Berechtigung nicht gewährt wurde, generiert die Anwendung aber von vornherein die Ausnahme und wird nicht geladen.  
  
 In einem Szenario, in dem die Anwendung nur Daten vom Datenträger lesen muss, können Sie festlegen, dass der Anwendung niemals Schreibberechtigungen gewährt werden. Auf diese Weise kann Ihr Code im Falle eines Fehlers im Programm oder eines bösartigen Angriffs die Daten, mit denen er arbeitet, nicht beschädigen. Weitere Informationen finden Sie unter [anfordern von Berechtigungen](/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100)).  
  
## <a name="role-based-security-and-cas"></a>Rollenbasierte Sicherheit und CAS  
 Durch Implementieren der rollenbasierten Sicherheit und der Codezugriffssicherheit (CAS) lässt sich die Gesamtsicherheit Ihrer Anwendung verbessern. Als Grundlage für die rollenbasierte Sicherheit kann ein Windows-Konto oder eine benutzerdefinierte Identität verwendet werden, wodurch die Informationen zum Sicherheitsprinzipal für den aktuellen Thread verfügbar werden. Anwendungen müssen darüber hinaus oft anhand der vom Benutzer bereitgestellten Anmeldeinformationen Daten- oder Ressourcenzugriff gewähren. In der Regel überprüfen diese Anwendungen zunächst die Rolle des Benutzers und stellen dann auf Grundlage dieser Rolle den Zugriff auf Ressourcen bereit.  
  
 Die rollenbasierte Sicherheit ermöglicht es einer Komponente, zur Laufzeit aktuelle Benutzer und die ihnen zugeordneten Rollen zu identifizieren. Diese Informationen werden dann mithilfe einer CAS-Richtlinie zugeordnet, um die zur Laufzeit gewährten Berechtigungen zu bestimmen. Für eine bestimmte Anwendungsdomäne kann der Host die Standardrichtlinie der rollenbasierten Sicherheit ändern und einen Standardsicherheitsprinzipal festlegen, der für einen Benutzer und die mit diesem Benutzer verknüpften Rollen steht.  
  
 Die CLR verwendet Berechtigungen zum Implementieren ihres Mechanismus zur Durchsetzung von Beschränkungen für verwalteten Code. Rollenbasierte Sicherheitsberechtigungen bieten die Möglichkeit aufzudecken, ob ein Benutzer (oder der Agent, der im Auftrag des Benutzers agiert) eine bestimmte Identität besitzt oder Member einer bestimmten Rolle ist. Weitere Informationen finden Sie unter [Sicherheits Berechtigungen](/previous-versions/dotnet/netframework-4.0/5ba4k1c5(v=vs.100)).  
  
 Je nach Art der Anwendung, die Sie erstellen, sollten Sie in Erwägung ziehen, rollenbasierte Berechtigungen in der Datenbank zu implementieren. Weitere Informationen zur rollenbasierten Sicherheit in SQL Server finden Sie unter [SQL Server Sicherheit](./sql/sql-server-security.md).  
  
## <a name="assemblies"></a>Assemblys  
 Assemblys bilden die Grundlage für die Bereitstellung, die Versionskontrolle, die Wiederverwendung, die Festlegung des Aktivierungsumfangs und die Sicherheitsberechtigungen für eine .NET Framework-Anwendung. Eine Assembly stellt eine Sammlung von Typen und Ressourcen bereit, die zusammenarbeiten und eine logische Funktionalitätseinheit bilden. Für die CLR existiert ein Typ niemals außerhalb des Kontexts einer Assembly. Weitere Informationen zum Erstellen und Bereitstellen von Assemblys finden Sie unter [Programming with](../../../standard/assembly/index.md)Assemblys.  
  
### <a name="strong-naming-assemblies"></a>Assemblys mit starkem Namen  
 Ein starker Name (oder eine digitale Signatur) setzt sich aus der Identität der Assembly mit einfachem Textnamen, Versionsnummer und (sofern vorhanden) Kulturinformationen sowie einem öffentlichen Schlüssel und einer digitalen Signatur zusammen. Die digitale Signatur wird mit dem entsprechenden privaten Schlüssel aus einer Assemblydatei generiert. Die Assemblydatei enthält das Assemblymanifest, das wiederum die Namen und Hashes aller Dateien enthält, die die Assembly bilden.  
  
 Wenn eine Assembly mit einem starken Namen versehen wird, erhalten Anwendungen oder Komponenten eine eindeutige Identität, über die andere Software explizit auf die Assembly verweisen können. Ein starker Name schützt Assemblys vor Angriffen durch andere Assemblys, die bösartigen Code enthalten. Außerdem wird durch starke Namen die Versionskonsistenz zwischen verschiedenen Versionen einer Komponente gewährleistet. Assemblys, die im globalen Assemblycache (GAC) bereitgestellt werden sollen, müssen einen starken Namen erhalten. Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md).  
  
## <a name="partial-trust-in-adonet-20"></a>Teilweise Vertrauenswürdigkeit in ADO.NET 2.0  
 In ADO.NET 2.0 können der .NET Framework-Datenanbieter für SQL Server, der .NET Framework-Datenanbieter für OLE DB, der .NET Framework-Datenanbieter für ODBC und der .NET Framework-Datenanbieter für Oracle jetzt alle in teilweise vertrauenswürdigen Umgebungen ausgeführt werden. In früheren Releases von .NET Framework wurde nur <xref:System.Data.SqlClient> in nicht vollständig vertrauenswürdigen Umgebungen unterstützt.  
  
 Eine teilweise vertrauenswürdige Anwendung, die den Datenanbieter für SQL Server verwendet, muss mindestens die Berechtigung zum Ausführen und die <xref:System.Data.SqlClient.SqlClientPermission>-Berechtigung besitzen.  
  
### <a name="permission-attribute-properties-for-partial-trust"></a>Eigenschaften von Berechtigungsattributen für teilweise Vertrauenswürdigkeit  
 In Szenarien für teilweise Vertrauenswürdigkeit können Sie <xref:System.Data.SqlClient.SqlClientPermissionAttribute>-Member zur weiteren Einschränkung der verfügbaren Funktionen des .NET Framework-Datenanbieters für SQL Server verwenden.  
  
 In der folgenden Tabelle werden die verfügbaren <xref:System.Data.SqlClient.SqlClientPermissionAttribute>-Eigenschaften mit ihren Beschreibungen aufgeführt:  
  
|Berechtigungsattributeigenschaft|BESCHREIBUNG|  
|-----------------------------------|-----------------|  
|`Action`|Ruft eine Sicherheitsaktion ab oder legt diese fest. Wird von <xref:System.Security.Permissions.SecurityAttribute> geerbt.|  
|`AllowBlankPassword`|Aktiviert oder deaktiviert die Verwendung von leeren Kennwörtern in einer Verbindungszeichenfolge. Gültige Werte sind `true` (zum Aktivieren der Verwendung von leeren Kennwörtern) und `false` (zum Deaktivieren der Verwendung von leeren Kennwörtern). Wird von <xref:System.Data.Common.DBDataPermissionAttribute> geerbt.|  
|`ConnectionString`|Gibt eine zulässige Verbindungszeichenfolge an. Es können mehrere Verbindungszeichenfolgen angegeben werden. **Hinweis:**  Fügen Sie keine Benutzer-ID oder ein Kennwort in die Verbindungs Zeichenfolge ein. In diesem Release können Einschränken von Verbindungszeichenfolgen nicht mit dem .NET Framework-Konfigurationstool geändert werden. <br /><br /> Wird von <xref:System.Data.Common.DBDataPermissionAttribute> geerbt.|  
|`KeyRestrictions`|Gibt zulässige oder unzulässige Parameter für Verbindungszeichenfolgen an. Parameter für Verbindungs Zeichenfolgen werden im Formular identifiziert *\<parameter name>=* . Es können mehrere durch Semikolon (;) getrennte Parameter angegeben werden. **Hinweis:**  Wenn Sie nicht angeben `KeyRestrictions` , aber die- `KeyRestrictionBehavior` Eigenschaft auf oder festlegen `AllowOnly` `PreventUsage` , sind keine zusätzlichen Parameter für die Verbindungs Zeichenfolge zulässig. Wird von <xref:System.Data.Common.DBDataPermissionAttribute> geerbt.|  
|`KeyRestrictionBehavior`|Legt die Verbindungszeichenfolgenparameter als die einzigen zulässigen zusätzlichen Parameter fest (`AllowOnly`) oder gibt die nicht zulässigen zusätzlichen Parameter an (`PreventUsage`). `AllowOnly` ist die Standardoption. Wird von <xref:System.Data.Common.DBDataPermissionAttribute> geerbt.|  
|`TypeID`|Ruft bei Implementierung in einer abgeleiteten Klasse einen eindeutigen Bezeichner für dieses Attribut ab. Wird von <xref:System.Attribute> geerbt.|  
|`Unrestricted`|Gibt an, ob für die Ressource uneingeschränkte Berechtigungen deklariert wurden. Wird von <xref:System.Security.Permissions.SecurityAttribute> geerbt.|  
  
#### <a name="connectionstring-syntax"></a>Syntax von "ConnectionString"  
 Das folgende Beispiel zeigt, wie mithilfe des Elements `connectionStrings` einer Konfigurationsdatei nur eine bestimmte Verbindungszeichenfolge für die Verwendung zugelassen werden kann. Weitere Informationen zum Speichern und Abrufen von Verbindungs Zeichenfolgen aus Konfigurationsdateien finden Sie unter [Verbindungs](connection-strings.md) Zeichenfolgen.  
  
```xml  
<connectionStrings>  
  <add name="DatabaseConnection"
    connectionString="Data Source=(local);Initial
    Catalog=Northwind;Integrated Security=true;" />  
</connectionStrings>  
```  
  
#### <a name="keyrestrictions-syntax"></a>Syntax von "KeyRestrictions"  
 Im folgenden Beispiel wird dieselbe Verbindungs Zeichenfolge aktiviert, die Verwendung der `Encrypt` `Packet Size` Verbindungs Zeichen folgen Optionen und aktiviert, aber die Verwendung anderer Verbindungs Zeichen folgen Optionen wird eingeschränkt.  
  
```xml  
<connectionStrings>  
  <add name="DatabaseConnection"
    connectionString="Data Source=(local);Initial
    Catalog=Northwind;Integrated Security=true;"  
    KeyRestrictions="Encrypt=;Packet Size=;"  
    KeyRestrictionBehavior="AllowOnly" />  
</connectionStrings>  
```  
  
#### <a name="keyrestrictionbehavior-with-preventusage-syntax"></a>Syntax von "KeyRestrictionBehavior" mit "PreventUsage"  
 Im folgenden Beispiel wird dieselbe Verbindungszeichenfolge aktiviert, und alle anderen Verbindungsparameter bis auf `User Id`, `Password` und `Persist Security Info` werden zugelassen.  
  
```xml  
<connectionStrings>  
  <add name="DatabaseConnection"
    connectionString="Data Source=(local);Initial
    Catalog=Northwind;Integrated Security=true;"  
    KeyRestrictions="User Id=;Password=;Persist Security Info=;"  
    KeyRestrictionBehavior="PreventUsage" />  
</connectionStrings>  
```  
  
#### <a name="keyrestrictionbehavior-with-allowonly-syntax"></a>Syntax von "KeyRestrictionBehavior" mit "AllowOnly"  
 Im folgenden Beispiel werden zwei Verbindungszeichenfolgen aktiviert, die außerdem die Parameter `Initial Catalog`, `Connection Timeout`, `Encrypt` und `Packet Size` enthalten. Alle anderen Parameter für Verbindungszeichenfolgen werden nicht zugelassen.  
  
```xml  
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
  
### <a name="enabling-partial-trust-with-a-custom-permission-set"></a>Aktivieren einer teilweisen Vertrauenswürdigkeit mit einem benutzerdefinierten Berechtigungssatz  
 Um die Verwendung der <xref:System.Data.SqlClient>-Berechtigungen für eine bestimmte Zone zu aktivieren, muss ein Systemadministrator einen benutzerdefinierten Berechtigungssatz für eine bestimmte Zone erstellen. Standardberechtigungssätze wie `LocalIntranet` können nicht geändert werden. Wenn Sie z. b. <xref:System.Data.SqlClient> Berechtigungen für Code mit einem von einschließen möchten, <xref:System.Security.Policy.Zone> `LocalIntranet` kann ein Systemadministrator den Berechtigungs Satz für kopieren, `LocalIntranet` ihn in "CustomLocalIntranet" umbenennen, die Berechtigungen hinzufügen <xref:System.Data.SqlClient> , den CustomLocalIntranet-Berechtigungs Satz mithilfe des [Caspol.exe (Code Zugriffs-Sicherheitsrichtlinien Tool)](../../tools/caspol-exe-code-access-security-policy-tool.md)importieren und den Berechtigungs Satz `LocalIntranet_Zone` auf "CustomLocalIntranet" festlegen.  
  
### <a name="sample-permission-set"></a>Beispielberechtigungssatz  
 Im Folgenden finden Sie einen Beispielberechtigungssatz für den .NET Framework-Datenanbieter für SQL Server in einem teilweise vertrauenswürdigen Szenario. Weitere Informationen zum Erstellen von benutzerdefinierten Berechtigungs Sätzen finden [Sie unter Konfigurieren von Berechtigungs Sätzen mithilfe von Caspol.exe](/previous-versions/dotnet/netframework-4.0/4ybs46y6(v=vs.100)).  
  
```xml  
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
  
## <a name="verifying-adonet-code-access-using-security-permissions"></a>Überprüfen des ADO.NET-Codezugriffs mit Sicherheitsberechtigungen  
 In teilweise vertrauenswürdigen Szenarien können durch Angabe eines <xref:System.Data.SqlClient.SqlClientPermissionAttribute> für bestimmte Methoden im Code CAS-Berechtigungen verlangt werden. Wenn diese Berechtigung aufgrund einer eingeschränkten Sicherheitsrichtlinie nicht gewährt wird, wird vor dem Ausführen des Codes eine Ausnahme ausgelöst. Weitere Informationen zu Sicherheitsrichtlinien finden Sie unter Bewährte Methoden für die [Verwaltung von Sicherheitsrichtlinien](/previous-versions/dotnet/netframework-4.0/c1k0eed6(v=vs.100)) und [Sicherheitsrichtlinien](/previous-versions/dotnet/netframework-4.0/sa4se9bc(v=vs.100)).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Schreiben von Code gezeigt, durch den eine bestimmte Verbindungszeichenfolge verlangt wird. Der Code simuliert das Verweigern uneingeschränkter Berechtigungen für <xref:System.Data.SqlClient>. Unter Praxisbedingungen würde dies durch eine CAS-Richtlinie implementiert werden.  
  
> [!IMPORTANT]
> Die korrekte Vorgehensweise beim Entwerfen von CAS-Berechtigungen für ADO.NET besteht darin, vom restriktivsten Fall (gar keine Berechtigungen) auszugehen und dann nur die Berechtigungen hinzuzufügen, die für die konkreten auszuführenden Aufgaben erforderlich sind. Die umgekehrte Herangehensweise, also zuerst alle Berechtigungen zu gewähren und dann zu versuchen, eine bestimmte Berechtigung zu verweigern, ist dagegen unsicher, da ein und dieselbe Verbindungszeichenfolge auf verschiedene Art und Weise ausgedrückt werden kann. Wenn Sie z. B. alle Berechtigungen zulassen und dann die Verwendung der Verbindungszeichenfolge "server=someserver" zu verweigern versuchen, wäre die Zeichenfolge "server=someserver.mycompany.com" nach wie vor zulässig. Wenn Sie hingegen immer ohne jede Berechtigung beginnen, sinkt die Gefahr, dass der Berechtigungssatz Lücken enthält.  
  
 Der folgende Code zeigt, wie `SqlClient` die Sicherheitsanforderung ausführt, die eine <xref:System.Security.SecurityException> auslöst, wenn die entsprechenden CAS-Berechtigungen nicht vorhanden sind. Die Ausgabe des <xref:System.Security.SecurityException>-Objekts wird im Konsolenfenster angezeigt.  
  
 [!code-csharp[DataWorks SqlClient.CAS#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.CAS/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.CAS#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.CAS/VB/source.vb#1)]  
  
 Im Konsolenfenster müsste nun die folgende Ausgabe angezeigt werden:  
  
```output  
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
  
## <a name="interoperability-with-unmanaged-code"></a>Interoperabilität mit nicht verwaltetem Code  
 Code, der außerhalb der CLR ausgeführt wird, wird als nicht verwalteter Code bezeichnet. Deshalb können Sicherheitsmechanismen, z. B. CAS, auf nicht verwalteten Code nicht angewendet werden. Beispiele für nicht verwalteten Code sind COM-Komponenten, ActiveX-Schnittstellen und Windows API-Funktionen. Damit bei der Ausführung von nicht verwaltetem Code die Gesamtsicherheit der Anwendung nicht gefährdet wird, sind besondere Sicherheitsüberlegungen notwendig. Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../interop/index.md).  
  
 .NET Framework unterstützt den Zugriff durch COM-Interop, um die Abwärtskompatibilität zu vorhandenen COM-Komponenten sicherzustellen. Sie können COM-Komponenten in eine .NET Framework-Anwendung einbauen, indem Sie die entsprechenden COM-Typen mit den COM-Interop-Tools importieren. Nach dem Import sind die COM-Typen einsatzbereit. COM-Interop ermöglicht es COM-Clients auch, auf verwalteten Code zuzugreifen, indem Assemblymetadaten in eine Typbibliothek exportiert und die verwalteten Komponenten als COM-Komponente registriert werden. Weitere Informationen finden Sie unter [Advanced COM Interoperabilität](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100)).  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](securing-ado-net-applications.md)
- [Sicherheit in systemeigenem Code und .NET Framework-Code](/previous-versions/visualstudio/visual-studio-2010/1787tk12(v=vs.100))
- [Rollenbasierte Sicherheit](../../../standard/security/role-based-security.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
