---
title: "Übersicht über das WSFederation-Authentifizierungsmodul"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02c4d5e8-f0a7-49ee-9cf5-3647578510ad
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ea17e384ecb4536ed544e3b874631db6fe54e0e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="wsfederation-authentication-module-overview"></a>Übersicht über das WSFederation-Authentifizierungsmodul
Windows Identity Foundation (WIF) umfasst die Verbundauthentifizierung in ASP.NET-Anwendungen über das WS-Verbundauthentifizierungsmodul (WS-FAM). In diesem Thema wird beschrieben, wie Verbundauthentifizierung funktioniert und verwendet wird.  
  
### <a name="overview-of-federated-authentication"></a>Übersicht über die Verbundauthentifizierung  
 Mit Verbundauthentifizierung kann ein Sicherheitstokendienst (STS) in einer vertrauenswürdigen Domäne Authentifizierungsinformationen für ein STS in einer anderen vertrauenswürdigen Domäne bereitstellen, wenn zwischen den beiden Domänen eine Vertrauensstellung besteht. Ein Beispiel dafür wird in der folgenden Abbildung gezeigt.  
  
 ![Szenario für Verbundauthentifizierung](../../../docs/framework/security/media/federatedauthentication.gif "FederatedAuthentication")  
  
1.  Ein Client in der vertrauenswürdigen Fabrikam-Domäne sendet eine Anforderung an eine Anwendung der vertrauenden Seite (Relying Party, RP) in der vertrauenswürdigen Contoso-Domäne.  
  
2.  Die vertrauende Seite leitet den Client an einen STS in der vertrauenswürdigen Contoso-Domäne um. Dieser STS kennt den Client nicht.  
  
3.  Der Contoso-STS leitet den Client an einen STS in der vertrauenswürdigen Fabrikam-Domäne um, zu der seitens der Contoso-Domäne eine Vertrauensstellung besteht.  
  
4.  Der Fabrikam-STS überprüft die Identität des Clients und gibt einen Sicherheitstoken an den Contoso-STS aus.  
  
5.  Der Contoso-STS verwendet das Fabrikam-Token, um sein eigenes Token zu erstellen, das von der vertrauenden Seite verwendet werden kann, und sendet es an die vertrauende Seite.  
  
6.  Die vertrauende Seite extrahiert die Ansprüche des Clients aus dem Sicherheitstoken und trifft eine Autorisierungsentscheidung.  
  
### <a name="using-the-federated-authentication-module-with-aspnet"></a>Verwenden des Verbundauthentifizierungsmoduls mit ASP.NET  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WS-FAM) ist ein HTTP-Modul, mit dem Sie einer [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Anwendung Verbundauthentifizierung hinzufügen können. Mit Verbundauthentifizierung kann der STS Authentifizierungslogik verwenden, sodass Sie sich auf das Schreiben von Geschäftslogik konzentrieren können.  
  
 Bei der Konfiguration des WS-FAM geben Sie den STS an, an den nicht authentifizierte Anforderungen umgeleitet werden sollen. Mit WIF können Sie einen Benutzer auf zwei Arten authentifizieren:  
  
1.  Passive Umleitung: Wenn ein nicht authentifizierter Benutzer versucht, auf eine geschützte Ressource zuzugreifen, Sie den Benutzer aber einfach auf einen STS umleiten möchten, ohne eine Anmeldeseite zu benötigen, ist dies der richtige Ansatz. Der STS überprüft die Identität des Benutzers und gibt ein Sicherheitstoken aus, das die entsprechenden Ansprüche für diesen Benutzer enthält. Für diese Option muss das WS-FAM in der HTTP-Modulpipeline hinzugefügt werden. Mit dem Identitäts- und Zugriffs-Tool können Sie in Visual Studio 2012 die Konfigurationsdatei der Anwendung ändern, damit das WS-FAM verwendet und ein Verbund-STS erstellt wird. Weitere Informationen finden Sie unter [Identitäts- und Zugriffs-Tool für Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md).  
  
2.  Sie können die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignIn%2A?displayProperty=nameWithType>-Methode oder die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectToIdentityProvider%2A>-Methode aus dem zugrunde liegenden Code einer Anmeldeseite in der Anwendung der vertrauenden Seiten aufrufen.  
  
 In der passiven Umleitung wird die gesamte Kommunikation durch Antwort/Umleitung vom Client ausgeführt (in der Regel ein Browser). Sie können der HTTP-Pipeline der Anwendung das WS-FAM hinzufügen. Hier sucht es nach nicht authentifizierten Benutzeranforderungen und leitet die Benutzer an den angegebenen STS um.  
  
 Das WS-FAM löst außerdem verschiedene Ereignisse aus, mit denen Sie seine Funktionalität in einer [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Anwendung anpassen können.  
  
### <a name="how-the-ws-fam-works"></a>So funktioniert das WS-FAM  
 Das WS-FAM wird in der <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>-Klasse implementiert. In der Regel fügen Sie das WS-FAM der HTTP-Pipeline der [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Anwendung der vertrauenden Seite hinzu. Wenn ein nicht authentifizierter Benutzer versucht, auf eine geschützte Ressource zuzugreifen, gibt die vertrauende Seite die HTTP-Antwort „401 Autorisierung verweigert“ zurück. Das WS-FAM fängt diese Antwort ab und lässt nicht zu, dass der Client sie erhält. Dann wird der Benutzer direkt auf den angegebenen STS umgeleitet. Der STS gibt ein Sicherheitstoken aus, das das WS-FAM erneut abfängt. Das WS-FAM verwendet das Token, um eine Instanz von <xref:System.Security.Claims.ClaimsPrincipal> für den authentifizierten Benutzer zu erstellen. Damit können die regulären [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Autorisierungsmechanismen funktionieren.  
  
 Da HTTP statusfrei ist, benötigen wir eine Methode, mit der verhindert wird, dass der gesamte Prozess jedes Mal wiederholt wird, wenn der Benutzer versucht, auf eine andere geschützte Ressource zuzugreifen. Hier setzt das <xref:System.IdentityModel.Services.SessionAuthenticationModule> an. Wenn der STS ein Sicherheitstoken für den Benutzer ausgibt, erstellt <xref:System.IdentityModel.Services.SessionAuthenticationModule> auch ein Sitzungssicherheitstoken für den Benutzer und legt es in einem Cookie ab. Bei nachfolgenden Anforderungen wird dieses Cookie durch das <xref:System.IdentityModel.Services.SessionAuthenticationModule> abgefangen und dazu verwendet, den <xref:System.Security.Claims.ClaimsPrincipal> des Benutzers zu rekonstruieren.  
  
 Im folgenden Diagramm ist der Gesamtinformationsfluss für eine passive Umleitung dargestellt. Die Anforderung wird automatisch über STS umgeleitet, sodass Anmeldeinformationen ohne eine Anmeldeseite erstellt werden:  
  
 ![Diagramm für die zeitliche Steuerung, das die Anmeldung mithilfe passiver Umleitung zeigt](../../../docs/framework/security/media/signinusingpassiveredirect.gif "SignInUsingPassiveRedirect")  
  
 Das folgende Diagramm zeigt weitere Details dazu, was geschieht, wenn der Benutzer für den STS authentifiziert ist und seine Sicherheitstoken von <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> verarbeitet werden:  
  
 ![Zeitliche Steuerung für die Tokenverarbeitung mit passiver Umleitung](../../../docs/framework/security/media/signinusingpassiveredirect-tokenprocessing.gif "SignInUsingPassiveRedirect_TokenProcessing")  
  
 Das folgende Diagramm zeigt weitere Details dazu, was geschieht, wenn die Sicherheitstoken des Benutzers in Cookies serialisiert wurden und über <xref:System.IdentityModel.Services.SessionAuthenticationModule> abgefangen werden:  
  
 ![Diagramm für die zeitliche Steuerung von SAM, das die Anmeldung mithilfe von Steuerelementen zeigt](../../../docs/framework/security/media/signinusingconrols-sam.gif "SignInUsingConrols_SAM")  
  
### <a name="events"></a>Ereignisse  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>, <xref:System.IdentityModel.Services.SessionAuthenticationModule> und die übergeordnete Klasse <xref:System.IdentityModel.Services.HttpModuleBase> lösen an verschiedenen Punkten der Verarbeitung einer HTTP-Anforderung Ereignisse aus. Sie können diese Ereignisse in der Datei `global.asax` der [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Anwendung bearbeiten.  
  
-   Die ASP.NET-Infrastruktur ruft die <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A>-Methode des Moduls auf, um das Modul zu initialisieren.  
  
-   Das <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated?displayProperty=nameWithType>-Ereignis wird ausgelöst, wenn die ASP.NET-Infrastruktur die <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A>-Methode zum ersten Mal für eines der Anwendungsmodule aufruft, die von <xref:System.IdentityModel.Services.HttpModuleBase> abgeleitet sind. Diese Methode greift auf die statische <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>-Eigenschaft zu, mit der die Konfiguration aus der Datei Web.config geladen wird. Dieses Ereignis wird beim ersten Zugriff auf die Eigenschaft ausgelöst. Auf das <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>-Objekt, das durch die Konfiguration initialisiert wird, kann durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType>-Eigenschaft in einem Ereignishandler zugegriffen werden. Mit diesem Ereignis können Sie die Konfiguration ändern, bevor sie in allen Modulen angewendet wird. Sie können einen Handler für dieses Ereignis in der Application_Start-Methode hinzufügen:  
  
    ```  
    void Application_Start(object sender, EventArgs e)  
    {  
        FederatedAuthentication.FederationConfigurationCreated += new EventHandler<FederationConfigurationCreatedEventArgs>(FederatedAuthentication_FederationConfigurationCreated);  
    }  
    ```  
  
     Jedes Modul überschreibt die abstrakten Methoden <xref:System.IdentityModel.Services.HttpModuleBase.InitializeModule%2A?displayProperty=nameWithType> und <xref:System.IdentityModel.Services.HttpModuleBase.InitializePropertiesFromConfiguration%2A?displayProperty=nameWithType>. Die erste dieser Methoden fügt Handler für ASP.NET-Pipelineereignisse hinzu, die für das Modul von Interesse sind. In den meisten Fällen genügt die Standardimplementierung des Moduls. Die zweite dieser Methoden initialisiert die Eigenschaften des Moduls aus der <xref:System.IdentityModel.Services.HttpModuleBase.FederationConfiguration%2A?displayProperty=nameWithType>-Eigenschaft. (Hierbei handelt es sich um eine Kopie der Konfiguration, die bereits geladen wurde). Sie müssen möglicherweise die zweite Methode überschreiben, wenn die Initialisierung neuer Eigenschaften aus einer Konfiguration in Klassen unterstützt werden soll, die Sie von <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> oder <xref:System.IdentityModel.Services.SessionAuthenticationModule> ableiten. In solchen Fällen müssen Sie auch von den entsprechenden Konfigurationsobjekten ableiten, damit die hinzugefügten Konfigurationseigenschaften unterstützt werden; zum Beispiel von <xref:System.IdentityModel.Configuration.IdentityConfiguration>, <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> oder <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>.  
  
-   Das WS-FAM löst das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenReceived>-Ereignis aus, wenn ein Sicherheitstoken abgefangen wird, das durch den STS ausgegeben wurde.  
  
-   Nach der Überprüfung des Tokens löst das WS-FAM das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenValidated>-Ereignis aus.  
  
-   Das <xref:System.IdentityModel.Services.SessionAuthenticationModule> löst das <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenCreated>-Ereignis aus, wenn es ein Sitzungssicherheitstoken für den Benutzer erstellt.  
  
-   Das <xref:System.IdentityModel.Services.SessionAuthenticationModule> löst das <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenReceived>-Ereignis aus, wenn es nachfolgende Anforderungen mit dem Cookie abfängt, das das Sitzungssicherheitstoken enthält.  
  
-   Bevor das WS-FAM den Benutzer an den Aussteller umleitet, löst es das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>-Ereignis aus. Die Anmeldungsanforderung für den WS-Verbund ist über die <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs.SignInRequestMessage%2A> -Eigenschaft des <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs> verfügbar, das im Ereignis übergeben wird. Sie können die Anforderung ändern, bevor Sie sie an den Aussteller senden.  
  
-   Das WS-FAM löst das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignedIn>-Ereignis aus, wenn das Cookie erfolgreich geschrieben wurde und der Benutzer angemeldet ist.  
  
-   Das WS-FAM löst das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SigningOut>-Ereignis einmal pro Sitzung aus, da die Sitzung für jeden Benutzer geschlossen wird. Es wird nicht ausgelöst, wenn die Sitzung clientseitig geschlossen wird (beispielsweise durch Löschen des Sitzungscookie). In einer SSO-Umgebung kann der IP-STS auch anfordern, dass sich jede vertrauende Seite abmeldet. Damit wird dieses Ereignis ebenfalls ausgelöst, wenn <xref:System.IdentityModel.Services.SigningOutEventArgs.IsIPInitiated%2A> auf `true` festgelegt ist.  
  
> [!NOTE]
>  Sie sollten die <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType>-Eigenschaft nicht während jedes Ereignisses verwenden, das von <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> oder <xref:System.IdentityModel.Services.SessionAuthenticationModule> ausgelöst wird. Der Grund dafür ist, dass <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> nach den Authentifizierungsprozess festgelegt wird, während Ereignisse während des Authentifizierungsprozesses ausgelöst werden.  
  
### <a name="configuration-of-federated-authentication"></a>Konfiguration der Verbundauthentifizierung  
 Das WS-FAM und SAM werden über das [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)-Element konfiguriert. Das untergeordnete Element [\<wsFederation>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md) konfiguriert Standardwerte für die WS-FAM-Eigenschaften; dazu gehören z.B. die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Issuer%2A>- und die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Realm%2A>-Eigenschaft. (Diese Werte können für einzelne Anforderungen geändert werden. Dazu stellen Sie Handler für einige der WS-FAM-Ereignisse bereit; beispielsweise <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>.) Der von SAM verwendete Cookiehandler wird über das untergeordnete [\<cookieHandler>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)-Element konfiguriert. WIF stellt einen Standardcookiehandler bereit, der in der <xref:System.IdentityModel.Services.ChunkedCookieHandler>-Klasse implementiert wird, deren Segmentgröße über das [\<chunkedCookieHandler>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)-Element festgelegt werden kann. Das `<federationConfiguration>`-Element verweist auf ein <xref:System.IdentityModel.Configuration.IdentityConfiguration>, das die Konfiguration für andere WIF-Komponenten bereitstellt, die in der Anwendung verwendet werden, wie z. B. <xref:System.Security.Claims.ClaimsAuthenticationManager> und <xref:System.Security.Claims.ClaimsAuthorizationManager>. Auf die Identitätskonfiguration kann explizit durch Angabe eines benannten [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)-Elements im `identityConfigurationName`-Attribut des `<federationConfiguration>`-Elements verwiesen werden. Wenn nicht explizit auf die Identitätskonfiguration verwiesen wird, wird die Standardidentitätskonfiguration verwendet.  
  
 Das folgende XML-Element zeigt eine Konfiguration der vertrauenden Seite einer ASP.NET-Anwendung. Die Konfigurationsabschnitte <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> und <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> werden unter dem `<configSections>`-Element hinzugefügt. Das SAM und das WS-FAM werden den HTTP-Modulen unter dem `<system.webServer>`/`<modules>`-Element hinzugefügt. Schließlich werden die WIF-Komponenten unter den Elementen `<system.identityModel>`/`<identityConfiguration>` und `<system.identityModel.services>`/`<federationConfiguration>` konfiguriert. Mit dieser Konfiguration wird der segmentierte Cookiehandler festgelegt, wenn es sich um den Standardcookiehandler handelt und im `<cookieHandler>`-Element kein Cookiehandlertyp angegeben ist.  
  
> [!WARNING]
>  Im folgenden Beispiel werden sowohl das `requireHttps`-Attribut des `<wsFederation>`-Elements und das `requireSsl`-Attribut des `<cookieHandler>`-Elements `false` verwendet. Dies stellt ein potenzielles Sicherheitsrisiko dar. In der Produktionsumgebung sollten beide Werte auf `true` gesetzt sein.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  ...  
  
  <system.webServer>  
    <modules>  
      <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
    </modules>  
  </system.webServer>  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost:50969/" />  
      </audienceUris>  
      <certificateValidation certificateValidationMode="None" />  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
        <trustedIssuers>  
          <add thumbprint="9B74CB2F320F7AAFC156E1252270B1DC01EF40D0" name="LocalSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
    </identityConfiguration>  
  </system.identityModel>  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:15839/wsFederationSTS/Issue" realm="http://localhost:50969/" reply="http://localhost:50969/" requireHttps="false" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)
