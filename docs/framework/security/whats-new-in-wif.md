---
title: Neuerungen in Windows Identity Foundation 4.5
ms.date: 03/30/2017
ms.assetid: 3b381f04-593b-471f-bd33-0362be1aade5
author: BrucePerlerMS
ms.openlocfilehash: 673294ccdb76e6016169a4e2b4e7713ba63fa1e7
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836815"
---
# <a name="what39s-new-in-windows-identity-foundation-45"></a>Neuerungen in Windows Identity Foundation 4.5
Die erste Version von Windows Identity Foundation (WIF) ist als eigenständiger Download erhältlich und wird als WIF 3.5 bezeichnet, da sie im .NET 3.5 SP1-Zeitrahmen eingeführt wurde. Ab .NET 4.5 ist WIF Bestandteil von .NET Framework. Da die WIF-Klassen direkt im Framework selbst verfügbar sind, ist eine weitaus umfassendere Integration der anspruchsbasierten Identität in .NET möglich, sodass Ansprüche einfacher verwendet werden können. Anwendungen, die für WIF 3.5 geschrieben wurden, müssen geändert werden, um das neue Modell nutzen zu können. Weitere Informationen finden Sie unter [Richtlinien für die Migration einer mit WIF 3.5 bis WIF 4.5 erstellten Anwendung](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).  
  
 Im Folgenden sind einige Merkmale der wichtigsten Änderungen angegeben.  
  
## <a name="wif-is-now-part-of-the-net-framework"></a>WIF ist nun Bestandteil von .NET Framework  
 WIF-Klassen sind nun über mehrere Assemblys verteilt. Die wichtigsten Klassen hierbei sind `mscorlib`, `System.IdentityModel`, `System.IdentityModel.Services` und `System.ServiceModel`. Entsprechend sind die WIF-Klassen über mehrere Namespaces verteilt: <xref:System.Security.Claims?displayProperty=nameWithType>, mehrere [System.IdentityModel](https://go.microsoft.com/fwlink/?LinkId=272004)-Namespaces und <xref:System.ServiceModel.Security?displayProperty=nameWithType>. Der <xref:System.Security.Claims?displayProperty=nameWithType>-Namespace enthält die neuen <xref:System.Security.Claims.ClaimsPrincipal>- und <xref:System.Security.Claims.ClaimsIdentity>-Klassen (siehe unten). Alle Prinzipale in .NET werden nun von <xref:System.Security.Claims.ClaimsPrincipal> abgeleitet. Ausführlichere Informationen zu den WIF-Namespaces und den Arten von Klassen, die diese enthalten, finden Sie unter [WIF-API-Referenz](../../../docs/framework/security/wif-api-reference.md). Informationen zur Zuordnung von Namespaces zwischen WIF 3.5 und 4.5 finden Sie unter [Namespacezuordnung zwischen WIF 3.5 und WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).  
  
## <a name="new-claims-model-and-principal-object"></a>Neues Anspruchsmodell und Prinzipalobjekt  
 Ansprüche bilden das Kernstück von .NET Framework 4.5. Die Basisanspruchsklassen (<xref:System.Security.Claims.Claim>, <xref:System.Security.Claims.ClaimsIdentity>, <xref:System.Security.Claims.ClaimsPrincipal>, <xref:System.Security.Claims.ClaimTypes> und <xref:System.Security.Claims.ClaimValueTypes>) sind direkt in `mscorlib` im <xref:System.Security.Claims?displayProperty=nameWithType>-Namespace enthalten. Es ist nicht mehr notwendig, Schnittstellen zu verwenden, um Ansprüche in das .NET-Identitätssystem einzubinden: <xref:System.Security.Principal.WindowsPrincipal>, <xref:System.Security.Principal.GenericPrincipal> und <xref:System.Web.Security.RolePrincipal> erben nun von <xref:System.Security.Claims.ClaimsPrincipal>, und <xref:System.Security.Principal.WindowsIdentity>, <xref:System.Security.Principal.GenericIdentity> und <xref:System.Web.Security.FormsIdentity> erben nun von <xref:System.Security.Claims.ClaimsIdentity>. Kurz gesagt, jede Prinzipalklasse behandelt jetzt Ansprüche. Die WIF 3.5-Integrationsklassen und -Schnittstellen (`WindowsClaimsIdentity`, `WindowsClaimsPrincipal`, `IClaimsPrincipal`, `IClaimsIdentity`) wurden daher entfernt. Darüber hinaus macht die <xref:System.Security.Claims.ClaimsIdentity>-Klasse jetzt Methoden verfügbar, die die Abfrage der Identitäts-Anspruchsauflistung erleichtern.  
  
## <a name="changes-to-the-wif-45-visual-studio-experience"></a>Änderungen der WIF 4.5 Visual Studio-Umgebung  
  
-   Die Visual Studio-Funktion **STS-Verweis hinzufügen...** (FedUtil-Befehlszeilenprogramm) ist nicht mehr vorhanden. Stattdessen können Sie die neue Visual Studio-Erweiterung **Identitäts- und Zugriffstool für Visual Studio 2012** verwenden. Dies ermöglicht es Ihnen, zum Testen der Lösungen einen Verbund mit einem vorhandenen STS einzugehen oder LocalSTS zu verwenden. Nachdem Sie die Erweiterung installiert haben, können Sie mit der rechten Maustaste auf das Projekt klicken und im Kontextmenü nach **Identität und Zugriff** suchen.  
  
-   Die ASP.NET- und STS-Vorlagen werden nicht mehr bereitgestellt, da Ansprüche direkt in vorhandenen Projektvorlagen für ASP.NET, Websites und WCF verwendet werden können.  
  
-   Die Steuerelemente im `Microsoft.IdentityModel.Web.Controls`-Namespace (`SignInControl`, `FederatedPassiveSignInControl` und `FederatedPassiveSignInStatus`) werden in WIF 4.5 nicht übernommen.  
  
## <a name="changes-to-the-wif-45-api"></a>Änderungen der WIF 4.5-API  
  
-   Im Allgemeinen befinden sich Ansprüche zu Klassen im <xref:System.Security.Claims?displayProperty=nameWithType>-Namespace. Mit WCF verknüpfte Klassen (Dienstverträge, Kanäle, Kanalfactorys und Diensthosts, die für WS-Trust-Szenarios verwendet werden) befinden sich im <xref:System.ServiceModel.Security?displayProperty=nameWithType>-Namespace. Alle anderen WIF-Klassen sind über verschiedene [System.IdentityModel](https://go.microsoft.com/fwlink/?LinkId=272004)-Namespaces verteilt. Hierzu gehören beispielsweise Klassen, die WS-* und SAML-Artefakte, Tokenhandler und verwandte Klassen sowie die in den WS-Federation-Szenarios verwendeten Klassen darstellen. Weitere Informationen finden Sie unter [Namespacezuordnung zwischen WIF 3.5 und WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md) und [WIF-API-Verweis](../../../docs/framework/security/wif-api-reference.md).  
  
-   Der Computerschlüssel wurde zur Verwendung in Sitzungscookies für Webfarmenszenarien aktiviert. Weitere Informationen finden Sie unter [WIF und Webfarmen](../../../docs/framework/security/wif-and-web-farms.md).  
  
-   Sie konfigurieren WIF jetzt deklarativ unter den Elementen [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) und [ \<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md). Weitere Informationen zur WIF-Konfiguration finden Sie unter [Referenz zur WIF-Konfiguration](../../../docs/framework/security/wif-configuration-reference.md).  
  
## <a name="other-notable-net-changes-or-features-that-are-caused-by-the-integration-of-wif-into-net"></a>Andere wichtige .NET-Änderungen oder -Funktionen, die durch die Integration von WIF in .NET verursacht werden  
  
-   Das Potenzial für das Ausführen der anspruchsbasierten Autorisierung (CBAC) ist jetzt ein wesentlicher Bestandteil von .NET Framework. Sie können ein <xref:System.Security.Claims.ClaimsAuthorizationManager>-Objekt konfigurieren und dann die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission>- und <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute>-Klassen verwenden, um imperative und deklarative Zugriffsüberprüfungen im Code auszuführen. CBAC bietet mehr Flexibilität und größere Granularität als herkömmliche rollenbasierte Zugriffsüberprüfungen (RBAC). Außerdem ermöglicht sie eine stärkere Trennung der Autorisierungsrichtlinie von der Geschäftslogik, da die Geschäftslogik die Zugriffsüberprüfung auf einen bestimmten Anspruch oder auf einen Satz von Ansprüchen basieren kann und die Autorisierungsrichtlinie für diese Ansprüche mit dem [\<claimsAuthorizationManager>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)-Element deklarativ konfiguriert werden kann.  
  
## <a name="wcf-changes-as-a-result-of-wif-integration"></a>WCF-Änderungen aufgrund der WIF-Integration:  
  
-   Das anspruchsbasierte WCF-Identitätsmodell wird von WIF abgelöst. Dies bedeutet, dass Klassen in den <xref:System.IdentityModel.Claims?displayProperty=nameWithType>-, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>- und <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>-Namespaces zugunsten von WIF-Klassen verworfen werden sollen.  
  
-   WIF ist nun für einen WCF-Dienst aktiviert, indem das `useIdentityConfiguration`-Attribut wie im folgenden XML-Code für das `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`-Element angeben wird:  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
     Wenn Sie das **Identitäts- und Zugriffstool für Visual Studio 2012** verwenden (siehe **Änderungen der Visual Studio-Umgebung** weiter oben), fügt das Tool für Sie ein `<serviceCredentials>`-Element mit dem `useIdentityConfiguration`-Attributsatz zur Konfigurationsdatei hinzu. Es fügt auch ein entsprechendes [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)-Element hinzu, das die WIF-Konfigurationseinstellungen enthält. Außerdem werden eine Bindung und andere Einstellungen hinzugefügt, die zur Auslagerung der Authentifizierung in der gewählten STS erforderlich sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für die Migration einer mit WIF 3.5 bis WIF 4.5 erstellten Anwendung](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)  
 [Namespacezuordnung zwischen WIF 3.5 und WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)  
 [WIF-API-Referenz](../../../docs/framework/security/wif-api-reference.md)  
 [Referenz zur WIF-Konfiguration](../../../docs/framework/security/wif-configuration-reference.md)
