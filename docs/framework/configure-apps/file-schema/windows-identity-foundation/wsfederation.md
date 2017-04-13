---
title: "&lt;wsFederation&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;wsFederation&gt;
Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\).  
  
## Syntax  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation authenticationType=xs:string (URI)  
        freshness=xs:decimal  
        homerealm=xs:string (URI)  
        issuer=xs:string (URI)  
        persistentCookiesOnPassiveRedirects=xs:boolean  
        passiveRedirectEnabled=xs:boolean  
        policy=xs:string (URI)  
        realm=xs:string (URI)  
        reply=xs:string (URI)  
        request=xs:string (URI)  
        requestPtr=xs:string (URI)  
        requireHttps=xs:boolean  
        resource=xs:string (URI)  
        signInQueryString=xs:string  
        signOutQueryString=xs:string  
        signOutReply=xs:string (URL)  
    </wsFederation>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|authenticationType|Ein URI, der den Authentifizierungstyp angibt.  Legt die WS\-Verbund\-in Vertretung Anforderungsparameter.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Vertretung\-Parameter nicht in der Anforderung enthalten ist.|  
|frische Luft|Die gewünschte maximale Alter der Authentifizierungsanforderungen, in Minuten.  Setzt den WS\-Verbund\-in\-Anforderung\-Wfresh\-Parameter.  Optional.  Der Standardwert ist 0.  Optional. **Warning:**  In der nächsten Version von.NET Framework 4.5, die `freshness` Attribut werden der Typ `xs:string` und der Standardwert werden `null`.|  
|homeRealm|Home Bereich der Identitätsprovider \(IP\) zur Authentifizierung verwenden.  Setzt den WS\-Federation\-in\-Anfrage\-Wh\-Parameter.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Whr\-Parameter nicht in der Anforderung enthalten ist.|  
|issuer|Der URI des beabsichtigten Tokenausgeber.  Legt die Basis URL der WS\-Verbund\-Anmeldung und Abmeldung Anforderungen erforderlich.|  
|persistentCookiesOnPassiveRedirects|Gibt an, ob persistente Cookies zur Authentifizierung ausgestellt werden.  Optional.  Der Standardwert ist "false", Cookies werden nicht ausgestellt.|  
|passiveRedirectEnabled|Gibt an, ob die WSFAM aktiviert ist, um nicht autorisierte Anforderungen automatisch zu einem STS umzuleiten.  Optional.  Der Standardwert ist "true", nicht autorisierte Zugriffe werden automatisch umgeleitet.|  
|policy|Ein URL, den Speicherort der einschlägigen Richtlinie auf Anmeldeanforderungen angibt.  Der Standard ist eine leere Zeichenfolge.  Setzt den WS\-Verbund\-in Anfrage wp\-Parameter.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wp\-Parameter nicht in der Anforderung enthalten ist.|  
|realm|Der URI des anfordernden Realm.  \(Ein URI, der die relying Party \(RP\) gegenüber dem Sicherheitstokendienst \(STS\) identifiziert.\) Setzt den Antrag Wtrealm WS\-Verbund\-Anmeldung Anfrage\-Parameter.  Erforderlich.|  
|reply|Eine URL, die Adresse angibt, an der die relying Party \(RP\) Anwendung Antworten von Security Token Service \(STS\) erhalten möchten.  Setzt den WS\-Verbund\-in\-Anforderung\-Wreply\-Parameter.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wreply\-Parameter nicht in der Anforderung enthalten ist.|  
|request|Die Anforderung der Tokenausstellung.  Setzt den WS\-Verbund\-in\-Anforderung Wreq\-Parameter.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wreq\-Parameter nicht in der Anforderung enthalten ist.  Einschließlich nicht die Wreq oder der Wreqptr\-Parameter in der Anforderung impliziert, dass der STS weiß, welche Art von Token ausstellen.|  
|requestPtr|Ein URL, den Speicherort der Tokenausstellung Anforderung angibt.  Setzt den Parameter der Anforderung Wreqptr.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wreqptr\-Parameter nicht in der Anforderung enthalten ist.  Einschließlich nicht die Wreq oder der Wreqptr\-Parameter in der Anforderung impliziert, dass der STS weiß, welche Art von Token ausstellen.|  
|requireHttps|Gibt an, ob die Kommunikation mit dem Sicherheitstokendienst \(STS\) HTTPS\-Protokoll verwenden muss.  Optional.  Der Standardwert ist "true", die HTTPS verwendet werden muss.|  
|Ressource|Ein URI, zu die Ressource, auf die zugegriffen wird, die relying Party \(RP\) identifiziert, die zu dem Sicherheitstokendienst \(STS\).  Optional.  Setzt den WS\-Verbund\-in\-Anforderung Wres\-Parameter.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wres\-Parameter nicht in der Anforderung enthalten ist. **Note:**  WRES ist eine legacy\-Parameter.  Geben Sie die `realm` Attribut den Wtrealm\-Parameter verwenden.|  
|signInQueryString|Ein Erweiterungspunkt Anwendung definierten Abfrage\-Parameter in der WS\-Verbund\-in Anforderungs\-URL angeben.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine weiteren Parameter in der Anforderung enthalten sein sollten.  Die Parameter werden als ein Fragment einer Verbindungszeichenfolge Abfrage der folgenden Form angegeben: `“param1=value1&param2=value2&param3=value3”` und so weiter. **Note:**  In einer Konfigurationsdatei der "&" Zeichen in der Abfragezeichenfolge angegeben werden mithilfe der Entity\-Referenz `&`.|  
|signOutQueryString|Ein Erweiterungspunkt Anwendung definierten Abfrage\-Parameter in der WS\-Verbund\-in Anforderungs\-URL angeben.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine weiteren Parameter in der Anforderung enthalten sein sollten.  Die Parameter werden als ein Fragment einer Verbindungszeichenfolge Abfrage der folgenden Form angegeben: `“param1=value1&param2=value2&param3=value3”` und so weiter. **Note:**  In einer Konfigurationsdatei der "&" Zeichen in der Abfragezeichenfolge angegeben werden mithilfe der Entity\-Referenz `&`.|  
|signOutReply|Gibt den URL, zu dem der Client soll, von dem Sicherheitstokendienst \(STS umgeleitet werden\) während der Abmeldung über das Protokoll, WS\-Federation Passive.  Legt den Wreply\-Parameter auf eine Abmeldeseite WS\-Verbund\-Anfrage.  Optional.  Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine weiteren Parameter in der Anforderung enthalten sein sollten.|  
  
### Untergeordnete Elemente  
 None  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Enthält die Einstellungen, konfigurieren die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).|  
  
## Hinweise  
 Sie können die `<wsFederation>` Element so konfigurieren Sie die Standardeinstellungen für WS\-Verbund\-Parameter und Standardverhalten für die WSFAM.  WS\-Verbund\-Parametereinstellungen, die gemäß der `<wsFederation>` Elementsatz entsprechende verfügbar gemachten Eigenschaften der <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Klasse.  Diese Eigenschaften bleiben gleich für jede Anforderung von der WSFAM ausgestellt.  Sie können die WS\-Verbund\-Parameter dynamisch während der Anforderungsverarbeitung durch Hinzufügen von Ereignishandlern für die WSFAM verfügbar gemachten Ereignisse ändern; zum Beispiel die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> Ereignis.  Weitere Informationen finden Sie in der Dokumentation zur <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>\-Klasse.  
  
 Die `<wsFederation>` Element dargestellt durch die <xref:System.IdentityModel.Services.Configuration.WSFederationElement> Klasse.  Das Configuration\-Objekt selbst wird dargestellt durch die <xref:System.IdentityModel.Services.Configuration.WSFederationConfiguration> Klasse.  Ein einzelnes <xref:System.IdentityModel.Services.Configuration.WSFederationConfiguration> Instanz wird festgelegt, auf die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> \-Objekt, das über die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> Eigenschaft und ermöglicht die Konfiguration für die WSFAM.  
  
## Beispiel  
 Das folgende XML zeigt eine `<wsFederation>` Element, das Einstellungen für die WSFAM angibt.  
  
> [!WARNING]
>  In diesem Beispiel wird die WSFAM nicht benötigt, um HTTPS zu verwenden.  Dies liegt daran, die `requireHttps` \-Attribut auf die `<wsFederation>` Element festgelegt ist `false`.  Diese Einstellung ist für die meisten Produktionsumgebungen nicht empfohlen, da es ein Sicherheitsrisiko darstellen kann.  
  
```  
<wsFederation passiveRedirectEnabled="true"   
  issuer="http://localhost:15839/wsFederationSTS/Issue"   
  realm="http://localhost:50969/"   
  reply="http://localhost:50969/"   
  requireHttps="false"   
  signOutReply="http://localhost:50969/SignedOutPage.html"   
  signOutQueryString="Param1=value2&Param2=value2"   
  persistentCookiesOnPassiveRedirects="true" />  
  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName>