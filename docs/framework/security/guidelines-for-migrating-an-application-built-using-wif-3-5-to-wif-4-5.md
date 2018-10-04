---
title: Richtlinien für die Migration einer mit WIF 3.5 bis WIF 4.5 erstellten Anwendung
ms.date: 03/30/2017
ms.assetid: 7a32fe6e-5f68-4693-9371-19411fa8063c
author: BrucePerlerMS
ms.openlocfilehash: ec66803edc21f186fa9a8c5bcb91b5181789893d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582514"
---
# <a name="guidelines-for-migrating-an-application-built-using-wif-35-to-wif-45"></a>Richtlinien für die Migration einer mit WIF 3.5 bis WIF 4.5 erstellten Anwendung
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF) 3.5 und 4.5.  
  
## <a name="overview"></a>Übersicht  
 Die Windows Identity Foundation (WIF) wurde ursprünglich innerhalb des .NET 3.5 SP1-Zeitrahmens freigegeben. Diese Version von WIF wird als WIF 3.5 bezeichnet. Sie wurde als separate Laufzeit und SDK freigegeben. Dadurch musste auf jedem Computer, auf dem eine WIF-fähige Anwendung ausgeführt wurde, die WIF-Laufzeit installiert sein, und Entwickler mussten für die Visual Studio-Vorlagen und -Tools zur Entwicklung von WIF-fähigen Anwendungen, das WIF SDK herunterladen und installieren. Ab .NET 4.5 wurde WIF vollständig in das .NET Framework integriert. Eine separate Laufzeit ist nicht mehr erforderlich, und die WIF-Tools können in Visual Studio 2012 mithilfe des Visual Studio-Erweiterungs-Managers installiert werden. Diese Version von WIF wird als WIF 4.5 bezeichnet.  
  
 Für die Integration von WIF in .NET waren mehrere Änderungen an der WIF-API-Oberfläche notwendig. WIF 4.5 beinhaltet neue Namespaces, einige Änderungen an Konfigurationselementen und neue Tools für Visual Studio. Dieses Thema bietet Anleitungen, die Ihnen beim Migrieren von Anwendungen helfen können, die mithilfe von WIF 3.5 bis WIF 4.5 erstellt wurden. Es gibt möglicherweise Szenarien, in denen ältere, mit WIF 3.5 erstellte, Anwendungen auf Computern ausgeführt werden müssen, auf denen Windows 8 oder Windows Server 2012 ausgeführt wird. Dieses Thema stellt auch Anleitungen dazu bereit, wie WIF 3.5 für diese Betriebssysteme aktiviert werden kann.  
  
## <a name="changes-required-for-wif-45"></a>Erforderliche Änderungen bei WIF 4.5  
 In diesem Abschnitt werden die Änderungen beschrieben, die zum Migrieren einer WIF 3.5-Anwendung zu WIF 4.5 erforderlich sind.  
  
### <a name="assembly-and-namespace-changes"></a>Assembly- und Namespaceänderungen  
 Bei WIF 3.5 waren alle WIF-Klassen in der `Microsoft.IdentityModel`-Assembly (microsoft.identitymicrosoft.identitymodel.dll) enthalten. Bei WIF 4.5 wurden die WIF-Klassen in folgende Assemblys unterteilt: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) und `System.ServiceModel` (System.ServiceModel.dll).  
  
 Alle Klassen bei WIF 3.5 waren in einem der `Microsoft.IdentityModel`-Namespaces enthalten, z. B. `Microsoft.IdentityModel`, `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Web` und so weiter. Bei WIF 4.5 werden die WIF-Klassen jetzt auf die [System.IdentityModel](https://go.microsoft.com/fwlink/?LinkId=272004)-Namespaces, den <xref:System.Security.Claims?displayProperty=nameWithType>-Namespace und den <xref:System.ServiceModel.Security?displayProperty=nameWithType>-Namespace aufgeteilt. Neben dieser Umstrukturierung sind einige der WIF 3.5-Klassen in WIF 4.5 nicht mehr vorhanden.  
  
 In der folgenden Tabelle werden einige der wichtigeren WIF 4.5-Namespaces und die Art der enthaltenen Klassen angegeben. Ausführlichere Informationen zur Zuordnung der Namespaces zwischen WIF 3.5 und 4.5 sowie über Namespaces und Klassen, die in WIF 4.5 abgelegt wurden, finden Sie unter [Namespace Mapping between WIF 3.5 and WIF 4.5 (Namespacezuordnung zwischen WIF 3.5 und WIF 4.5)](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).  
  
|WIF 4.5-Namespace|Beschreibung|  
|-----------------------|-----------------|  
|<xref:System.IdentityModel?displayProperty=nameWithType>|Enthält Klassen, die Cookietransformationen, Sicherheitstokendienste und spezielle XML-Wörterbuch-Reader darstellen. Enthält Klassen aus den folgenden WIF 3.5-Namespaces: `Microsoft.IdentityModel`, `Microsoft.IdentityModel.SecurityTokenService` und `Microsoft.IdentityModel.Threading`.|  
|<xref:System.Security.Claims?displayProperty=nameWithType>|Enthält Klassen, die Ansprüche, anspruchsbasierte Identitäten, anspruchsbasierte Prinzipale und andere anspruchsbasierte Identitätsmodellartefakte darstellen. Enthält Klassen aus dem `Microsoft.IdentityModel.Claims`-Namespace.|  
|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|Enthält Klassen, die Sicherheitstoken, Sicherheitstokenhandler und andere Sicherheitstokenartefakte darstellen. Enthält Klassen aus den folgenden WIF 3.5-Namespaces: `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Tokens.Saml11` und `Microsoft.IdentityModel.Tokens.Saml2`.|  
|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|Enthält Klassen, die in den passiven (WS-Verbund)-Szenarien verwendet werden. Enthält Klassen aus dem `Microsoft.IdentityModel.Web`-Namespace.|  
|<xref:System.ServiceModel.Security?displayProperty=nameWithType>|Klassen, die WCF-Verträge, Kanäle, Diensthosts und andere Artefakte darstellen, die in aktiven (WS-Trust-) Szenarien verwendet werden, sind jetzt in diesem Namespace enthalten. In WIF 3.5 waren diese Klassen im `Microsoft.IdentityModel.Protocols.WSTrust`-Namespace enthalten.|  
  
> [!IMPORTANT]
>  In den folgenden `System.IdentityModel`-Namespaces sind Klassen enthalten, die das anspruchsbasierte WCF-Identitätsmodell implementieren: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> und <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. Das anspruchsbasierte WCF-Identitätsmodell wird von WIF abgelöst. Sie sollten beim Erstellen von Projektmappen auf Grundlage von WIF in diesen drei Namespaces keine Klassen verwenden.  
  
### <a name="changes-due-to-net-integration"></a>Änderungen aufgrund von .NET-Integration  
 WIF ist jetzt in .NET Framework integriert. Die meisten .NET-Identitäts- und -Prinzipalklassen sind jetzt von <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> und <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType> abgeleitet. Die Auswirkungen der folgenden Änderungen bei WIF 4.5:  
  
-   WIF-Klassen, die Ansprüche, Identitäten und Prinzipale darstellen, sind jetzt im <xref:System.Security.Claims?displayProperty=nameWithType>-Namespace enthalten.  
  
    > [!IMPORTANT]
    >  Im <xref:System.IdentityModel.Claims?displayProperty=nameWithType>-Namespace sind Klassen enthalten, die Artefakte im anspruchbasierten WCF-Identitätsmodell darstellen. Viele dieser Klassen weisen Namen auf, die denen von WIF-Klassen gleichen, z. B. `Claims`. Verwenden Sie diese Klassen beim Erstellen von Projektmappen auf Grundlage von WIF nicht.  
  
-   Identitäts- und -Prinzipalklassen bei .NET werden jetzt direkt von <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> und <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType> abgeleitet, die anspruchsbasierte Identitäten und Prinzipale darstellen. Aus diesem Grund werden die WIF 3.5-Schnittstellen `IClaimsIdentity` und `IClaimsPrincipal` nicht mehr benötigt und sind in WIF 4.5 nicht verfügbar.  
  
-   Da .NET-Identitäts- und -Prinzipalklassen, wie <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> und <xref:System.Security.Principal.WindowsPrincipal?displayProperty=nameWithType>, jetzt von <xref:System.Security.Claims.ClaimsIdentity> und <xref:System.Security.Claims.ClaimsPrincipal> abgeleitet werden, ist die Anspruchsfunktionalität integriert. Aus diesem Grund werden anspruchspezifische Identitäts- und Prinzipalklassen, wie `WindowsClaimsIdentity` und `WindowsClaimsPrincipal`, die in WIF 3.5 vorhanden waren, nicht mehr benötigt und sind in WIF 4.5 nicht vorhanden.  
  
### <a name="other-changes-to-wif-functionality"></a>Andere Änderungen der WIF-Funktionalität  
 Neben den Namespaceänderungen und den Änderungen aufgrund der Integration in .NET, wurden in WIF 4.5 folgende allgemeine Änderungen der WIF-Funktionalität vorgenommen.  
  
-   Die `Microsoft.IdentityModel.ExceptionMapper`-Klasse, mit der die Funktionalität zur Zuordnung von Ausnahmen zu bestimmten SOAP-Fehlern ermöglicht wurde, ist entfernt worden.  
  
-   Die Ausnahmeoberfläche wurde drastisch reduziert.  
  
-   Viele der Klassen, mit denen bestimmte Protokoll- oder WS-*-spezifische Konstanten definiert wurden, sind entfernt worden; z. B. die `Microsoft.IdentityModel.WSAddressing10Constants`-Klasse, mit der die Konstanten definiert wurden, die sich auf WS-Adressierung 1.0 bezogen.  
  
-   Die Forderungen an den Windows-Tokendienst (c2wts) und die zugeordneten Klassen im `Microsoft.IdentityModel.WindowsTokenService`-Namespace wurden entfernt.  
  
### <a name="wif-configuration-changes"></a>WIF-Konfigurationsänderungen  
 Viele der Änderungen an der Konfigurationsdatei wurden in WIF 4.5 von Namespaceupdates verursacht. Betrachten Sie zum Beispiel den folgenden WIF 3.5-Eintrag im Abschnitt `<httpModules>`, um den Authentifizierungs-Manager des WS-Verbunds einer Anwendung hinzuzufügen:  
  
```xml  
<add name="WSFederationAuthenticationModule" type="Microsoft.IdentityModel.Web.WSFederationAuthenticationModule, Microsoft.IdentityModel, Version=3.5.0.0, Culture=neutral, PublicKeyToken=abcd … 5678" />  
```  
  
 Dieser Eintrag wurde in WIF 4.5 aktualisiert und enthält jetzt die neuen Namespaces und Assemblyversion:  
  
```xml  
<add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcd … 5678"/>  
```  
  
 In der folgenden Liste werden die wichtigsten Änderungen an der Konfigurationsdatei für WIF 4.5 aufgezählt.  
  
-   Der `<microsoft.identityModel>`-Abschnitt ist nun der [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)-Abschnitt.  
  
-   Das `<service>`-Element ist nun das [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)-Element.  
  
-   Ein neuer Abschnitt, [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md), wurde hinzugefügt, um Einstellungen anzugeben, mit denen das Verhalten in den passiven (WS-Verbund)-Szenarios gesteuert wird.  
  
-   Das [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)-Element und die untergeordneten Elemente aus dem `<service>`-Element wurden in WIF 3.5 zum neuen `<system.identityModel.services>`-Element verschoben.  
  
-   Einige Elemente, die in WIF 3.5 auf der Dienstebene direkt unter dem `<service>`-Element angegeben werden konnten, wurden zur Angabe unter dem [\<securityTokenHandlerConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)-Element eingeschränkt. (Sie können in WIF 4.5, zwecks Abwärtskompatibilität, trotzdem unter dem [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)-Element angegeben werden.)  
  
 Eine vollständige Liste der Konfigurationselemente in WIF 4.5 finden Sie unter [WIF Configuration Schema (WIF-Konfigurationsschema)](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md).  
  
### <a name="visual-studio-tooling-changes"></a>Änderungen an den Visual Studio-Tools  
 Das SDK WIF 3.5 bot ein eigenständiges Verbundhilfsprogramm, "FedUtil.exe" (FedUtil), das verwendet werden konnte, um die Identitätsverwaltung in WIF-fähigen Anwendungen auf einen Sicherheitstokendienst (STS) auszulagern. Mit diesem Tool wurden der Anwendungskonfigurationsdatei WIF-Einstellungen hinzugefügt, sodass mit der Anwendung Sicherheitstoken von einem oder mehreren Sicherheitstokendiensten abgerufen werden konnte. Es wurde in Visual Studio über die Schaltfläche **STS-Dienstverweis hinzufügen** aufgerufen. WIF 4.5 wird nicht mit FedUtil ausgeliefert. Stattdessen unterstützt WIF 4.5 eine neue Visual Studio-Erweiterung, das "Identitäts- und Zugriffs-Tool für Visual Studio 2012", mit dem Sie die Änderungen an der Konfigurationsdatei der Anwendung für die erforderlichen WIF-Einstellungen zum Auslagern der Identitätsverwaltung zu einem Sicherheitstokendienst vornehmen können. Mit dem Identitäts- und Zugriffs-Tool wird auch ein als "Local STS" bezeichneter Sicherheitstokendienst implementiert, das zum Testen der WIF-fähigen Anwendungen verwendet werden kann. In vielen Fällen wird durch diese Funktion die Notwendigkeit zum Erstellen von benutzerdefinierten Sicherheitstokendiensten vermieden, die in WIF 3.5 oft erforderlich waren, um Projektmappen in Entwicklung zu testen. Daher werden die Vorlagen für den Sicherheitstokendienst in Visual Studio 2012 nicht mehr unterstützt. Allerdings sind die Klassen, mit denen die Entwicklung von Sicherheitstokendiensten unterstützt wird, in WIF 4.5 weiterhin verfügbar.  
  
 Sie können das Identitäts- und Zugriffs-Tool über den Erweiterungs- und Aktualisierung-Manager in Visual Studio installieren, oder Sie können es von der folgenden Seite auf der Code Gallery herunterladen: [Identitäts- und Zugriffs-Tool für Visual Studio 2012 in der Code Gallery](https://go.microsoft.com/fwlink/?LinkID=245849). Die Änderungen an den Visual Studio-Tools werden in der folgenden Liste zusammengefasst:  
  
-   Die Funktionalität "STS-Dienstverweis hinzufügen" wurde entfernt. Sie wird durch das Identitäts- und Zugriffs-Tool ersetzt.  
  
-   Die Visual Studio-STS-Vorlagen wurden entfernt. Sie können den Local STS verwenden, der über das Identitäts- und Zugriffs-Tool verfügbar ist, um Identitätsprojektmappen zu testen, die Sie mit WIF entwickeln. Die Local STS-Konfiguration kann geändert werden, um die behandelten Ansprüche anzupassen.  
  
-   Das eigenständige Verbunds-Hilfsprogramm (FedUtil) ist in WIF 4.5 nicht verfügbar. Sie können das Identitäts- und Zugriffs-Tool zum Ändern der Konfigurationsdateien verwenden, um die Identitätsverwaltung zu einem Sicherheitstokendienst auszulagern.  
  
 Weitere Informationen zum Identitäts- und Zugriffs-Tool finden Sie unter [Identitäts- und Zugriffs-Tool für Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md).  
  
<a name="BKMK_ToolingChanges"></a>   
### <a name="passive-ws-federation-scenarios"></a>Passive (WS-Verbund)-Szenarien:  
  
-   Klassen, bei denen passive Szenarien unterstützt werden, wurden in den <xref:System.IdentityModel.Services?displayProperty=nameWithType>-Namespace verschoben. In WIF 3.5 waren diese Klassen im `Microsoft.IdentityModel.Web`-Namespace enthalten.  
  
-   Die Klassen im `Microsoft.IdentityModel.Web.Configuration`-Namespace wurden nach <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType> verschoben. Diese Klassen stellen die Objekte dar, die für die Konfiguration in passiven Szenarien spezifisch sind.  
  
-   `FederatedPasssiveSignInControl` wird nicht mehr unterstützt. Alle Klassen im `Microsoft.IdentityModel.Web.Controls`-Namespace wurden aus WIF 4.5 entfernt.  
  
-   Die Abmeldefunktionalität des Authentifizierungsmoduls des WS-Verbunds (<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>) unterscheidet sich von der in WIF 3.5. Weitere Informationen zur Funktionsweise der Abmeldung in WIF 4.5 finden Sie unter dem <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>-Klassenthema.  
  
### <a name="active-wcfws-trust-scenarios"></a>Aktive (WCF/WS-Trust)-Szenarien:  
  
-   Der `Microsoft.IdentityModel.Protocols.WSTrust`-Namespace wurde in WIF 4.5 hauptsächlich in zwei Namespaces aufgeteilt. Klassen, die Artefakte darstellen, die für das WS-Trust-Protokoll spezifisch sind, befinden sich jetzt in <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>. Dies schließt Klassen wie <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken> ein. Klassen, die Dienstverträge, Kanäle, Diensthosts und andere Artefakte darstellen, die bei der Verwendung von WS-Trusts in WCF-Anwendungen beteiligt sind, wurden nach <xref:System.ServiceModel.Security?displayProperty=nameWithType> verschoben, zum Beispiel die Schnittstelle <xref:System.ServiceModel.Security.IWSTrust13AsyncContract>.  
  
-   Das Konfigurieren einer WCF-Anwendung zur Verwendung von WIF wurde drastisch vereinfacht. Zuvor musste `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement` als Verhaltenserweiterung hinzugefügt werden, und diese Funktion wurde dann verwendet, um WIF in das Dienstverhaltens zu zwängen, indem ein `<federatedServiceHostConfiguration>`-Element angegeben wurde. WIF 4.5 wurde enger in WCF integriert. Jetzt können Sie WIF auf einem WCF-Dienst ermöglichen, indem Sie das `useIdentityConfiguration`-Attribut wie im folgenden XML-Code auf dem `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`-Element angeben:  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
-   In WIF 4.5 muss das Dienstzertifikat, das von einem aktiven (WCF)-Dienst verwendet wird, auf dem Diensthost angegeben werden. Bei der Konfiguration können Sie das, wie im vorangehenden Beispiel verdeutlicht, über das `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`/`<serviceCertificate>`-Element ausführen. In WIF 3.5 konnte das Dienstzertifikat über das untergeordnete `<serviceCertificate>`-Element des `<service>`-WIF-Elements angegeben werden. Diese Funktionalität ist in WIF 4.5 nicht vorhanden. Geben Sie stattdessen das `<serviceCertificate>`-Element unter dem `<serviceCredentials>`-Element an.  
  
-   Die Klassen, die verwendet werden, um WIF 3.5 in WCF zu zwängen, sind nicht mehr vorhanden. Das umfasst auch die folgenden Klassen im `Microsoft.IdentityModel.Tokens`-Namespace: `FederatedSecurityTokenManager`, `FederatedServiceCredentials` und die `IdentityModelServiceAuthorizationManager` sowie die `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement`-Klasse.  
  
## <a name="enabling-wif-35-in-windows-8"></a>Aktivieren von WIF 3.5 in Windows 8  
 Da WIF 4.5 Bestandteil von .NET 4.5 ist, ist es auf Computern, auf denen Windows 8 und Windows Server 2012 ausgeführt wird, automatisch aktiviert, und Anwendungen, die mithilfe von WIF 4.5 erstellt wurden, werden unter Windows 8 oder Windows Server 2012 standardmäßig ausgeführt. Möglicherweise müssen Sie auf einem Computer, auf dem Windows 8 oder Windows Server 2012 ausführt wird, jedoch Anwendungen ausführen, die mithilfe von WIF 3.5 erstellt wurden. In diesem Fall müssen Sie auf dem Zielcomputer WIF 3.5 aktivieren. Auf einem Computer, auf dem Windows 8 ausgeführt wird, können Sie hierzu das Tool zur Abbildverwaltung für die Bereitstellung (DISM) verwenden. Auf einem Computer, auf dem Windows Server 2012 ausführt wird, können Sie das DISM-Tool oder das Windows PowerShell-Cmdlet `Add-WindowsFeature` verwenden. In beiden Fällen können die entsprechenden Befehle entweder in der Befehlszeile oder aus der Windows PowerShell-Umgebung heraus aufgerufen werden.  
  
 Anhand der folgenden Befehle wird veranschaulicht, wie das DISM-Tool über die Befehlszeile oder aus der Windows PowerShell-Umgebung heraus verwendet wird. Standardmäßig ist das DISM-PowerShell-Modul in Windows 8 und Windows Server 2012 enthaltenen und muss nicht importiert werden. Weitere Informationen zur Verwendung von DISM mit Windows PowerShell finden Sie unter [Verwenden von DISM in Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=254419).  
  
 So aktivieren WIF 3.5 mithilfe von DISM:  
  
```  
dism /online /enable-feature:windows-identity-foundation  
```  
  
 So deaktivieren Sie WIF 3.5 mithilfe von DISM:  
  
```  
dism /online /disable-feature:windows-identity-foundation  
```  
  
 So überprüfen Sie mithilfe von DISM welche Funktionen aktiviert oder deaktiviert sind:  
  
```  
dism /online /get-features  
```  
  
 Alternativ können Sie auf Computern, auf denen Windows Server 2012 ausgeführt wird, WIF 3.5 mithilfe des Windows PowerShell-Cmdlets `Add-WindowsFeature` aktivieren. Um das von der Befehlszeile aus durchzuführen, können Sie den folgenden Befehl eingeben:  
  
```  
powershell "add-windowsfeature windows-identity-foundation"  
```  
  
 Aus der Windows PowerShell-Umgebung heraus können Sie den Befehl direkt eingeben:  
  
```  
add-windowsfeature windows-identity-foundation  
```  
  
> [!NOTE]
>  Da für viele der Klassen in WIF 3.5 und WIF 4.5 die gleichen Namen verwendet werden, stellen Sie bei der gemeinsamen Verwendung von WIF 3.5 und WIF 4.5 sicher, entweder die vollqualifizierten Klassennamen oder die Namespacealias zu verwenden, um zwischen den Klassen in WIF 3.5 und denen in WIF 4.5 zu unterscheiden.  
  
## <a name="see-also"></a>Siehe auch  
 [WIF Configuration Schema (Schema zur WIF-Konfiguration)](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md)  
 [Namespacezuordnung zwischen WIF 3.5 und WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)  
 [Neuerungen in Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)  
 [Identitäts- und Zugriffs-Tool für Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md)
