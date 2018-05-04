---
title: '&lt;wsFederation&gt;'
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: de7be463403b675e5f03786e85807e6685348680
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltwsfederationgt"></a>&lt;wsFederation&gt;
Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
\<system.identityModel.services >  
\<FederationConfiguration >  
\<WsFederation >  
  
## <a name="syntax"></a>Syntax  
  
```xml
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
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|authenticationType|Ein URI, der den Authentifizierungstyp angibt. Legt den WS-Verbund-anmeldeanforderung Wauth-Parameter. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wauth-Parameter nicht in der Anforderung enthalten ist.|  
|Aktualität|Die gewünschte maximale Alter von authentifizierungsanforderungen, in Minuten. Legt den WS-Verbund-anmeldeanforderung Wfresh-Parameter. Dies ist optional. Der Standardwert ist 0. Dies ist optional. **Warnung:** In der nächsten Version von .NET Framework 4.5, den `freshness` Attributs werden vom Typ `xs:string` und der Standardwert werden `null`.|  
|homeRealm|Den Startbereich des Identitätsanbieters (IP) für die Authentifizierung verwenden. Legt den WS-Verbund anmeldeanforderung Whr-Parameter. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Parameter Whr nicht in der Anforderung enthalten ist.|  
|issuer|Der URI des vorgesehenen Tokenausstellers. Legt das Basis-URL des WS-Verbund-Anmeldung Anforderungen und Anforderungen für einmaliges Abmelden erforderlich.|  
|persistentCookiesOnPassiveRedirects|Gibt an, ob es sich bei permanenten Cookies auf Authentifizierung ausgegeben werden. Dies ist optional. Der Standardwert ist "false", Cookies werden nicht ausgegeben.|  
|passiveRedirectEnabled|Gibt an, ob die WSFAM aktiviert ist, nicht autorisierte Anfragen automatisch an einen STS umleiten. Dies ist optional. Der Standardwert ist "true", nicht autorisierte Anfragen werden automatisch umgeleitet.|  
|behandelte Ausnahmen|Eine URL, die den Speicherort der entsprechenden Richtlinie für anmeldeanforderungen verwendet angibt. Der Standardwert ist eine leere Zeichenfolge. Legt den WS-Verbund anmeldeanforderung wp-Parameter. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wp-Parameter nicht in der Anforderung enthalten ist.|  
|realm|Der URI des anfordernden-Bereichs darstellt. (Ein URI, der die vertrauende Seite (RP) an den Sicherheitstokendienst (STS) bezeichnet.) Legt den Anforderung Wtrealm WS-Verbund-Anmeldung Anforderung-Parameter. Erforderlich.|  
|reply|Eine URL, die die Adresse identifiziert, an der die Anwendung vertrauenden Seite (RP) Antworten aus dem Sicherheitstokendienst (STS) erhalten sollen. Legt den WS-Verbund-anmeldeanforderung Wreply-Parameter. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wreply-Parameter nicht in der Anforderung enthalten ist.|  
|request|Die Anforderung tokenausstellung. Legt den WS-Verbund-anmeldeanforderung Wreq-Parameter. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wreq-Parameter nicht in der Anforderung enthalten ist. Einschließlich nicht in der Anforderung der Wreq oder mit dem Parameter Wreqptr impliziert, dass der STS weiß, welche Art von Token ausstellen.|  
|requestPtr|Eine URL, die den Speicherort der tokenausstellung Anforderung angibt. Legt den Anforderung Wreqptr-Parameter. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wreqptr-Parameter nicht in der Anforderung enthalten ist. Einschließlich nicht in der Anforderung der Wreq oder mit dem Parameter Wreqptr impliziert, dass der STS weiß, welche Art von Token ausstellen.|  
|requireHttps|Gibt an, ob die Kommunikation mit dem Sicherheitstokendienst (STS) HTTPS-Protokoll verwenden muss. Dies ist optional. Der Standardwert ist "true", muss HTTPS verwendet werden.|  
|Ressource|Ein URI, zu identifiziert die Ressource zugegriffen wird, die vertrauende Seite (RP), die an den Sicherheitstokendienst (STS). Dies ist optional. Legt den WS-Verbund-anmeldeanforderung Wres-Parameter. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wres-Parameter nicht in der Anforderung enthalten ist. **Hinweis:** Wres ist ein legacy-Parameter. Geben Sie die `realm` Attribut den Wtrealm-Parameter dafür verwenden.|  
|signInQueryString|Stellt einen Erweiterbarkeitspunkt zum Angeben von anwendungsdefinierten Abfrageparameter in der WS-Verbund-in-Anforderungs-URL bereit. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in der Anforderung enthalten sein soll. Die Parameter werden als ein Abfragefragment-Zeichenfolge im folgenden Format angegeben: `"param1=value1&param2=value2&param3=value3"` und so weiter. **Hinweis:** In einer Konfigurationsdatei den "&" Zeichen in der Abfragezeichenfolge muss angegeben werden, mithilfe der Entitätsverweis `&`.|  
|signOutQueryString|Stellt einen Erweiterbarkeitspunkt zum Angeben von anwendungsdefinierten Abfrageparameter in der WS-Verbund-in-Anforderungs-URL bereit. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in der Anforderung enthalten sein soll. Die Parameter werden als ein Abfragefragment-Zeichenfolge im folgenden Format angegeben: `"param1=value1&param2=value2&param3=value3"` und so weiter. **Hinweis:** In einer Konfigurationsdatei den "&" Zeichen in der Abfragezeichenfolge muss angegeben werden, mithilfe der Entitätsverweis `&`.|  
|signOutReply|Gibt die URL, zu dem der Client sollen, von der Sicherheitstokendienst (STS umgeleitet werden) während der Abmeldung über das WS-Verbund-Protokoll Passiv an. Legt den Wreply-Parameter für einen WS-Verbund-abmeldeanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in der Anforderung enthalten sein soll.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Enthält die Einstellungen zur Konfiguration der <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `<wsFederation>` Element so konfigurieren Sie Standardeinstellungen für WS-Verbund-Parameter und Standardverhalten für die WSFAM. WS-Verbund-parametereinstellungen unter definiert die `<wsFederation>` -Elementgruppe entsprechende Eigenschaften verfügbar gemacht werden, indem die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Klasse. Diese Eigenschaften bleiben für jede Anforderung, die von der WSFAM ausgegeben. Sie können die WS-Verbund-Parameter dynamisch während der anforderungsverarbeitung durch Hinzufügen von Ereignishandlern für die von WSFAM verfügbar gemachten Ereignisse ändern. z. B. die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> Ereignis. Weitere Informationen finden Sie in der Dokumentation für die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Klasse.  
  
 Die `<wsFederation>` Element dargestellt ist, durch die <xref:System.IdentityModel.Services.Configuration.WSFederationElement> Klasse. Das Konfigurationsobjekt selbst wird dargestellt, indem die <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> Klasse. Ein einzelnes <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> -Instanzensatz auf die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> -Objekt, das über zugegriffen wird die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> Eigenschaft und die Konfiguration für die WSFAM bereitstellt.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt ein `<wsFederation>` Element, das Einstellungen für die WSFAM angibt.  
  
> [!WARNING]
>  In diesem Beispiel ist die WSFAM nicht zur Verwendung von HTTPS erforderlich. Grund hierfür ist die `requireHttps` -Attribut auf die `<wsFederation>` -Elements festgelegt `false`. Diese Einstellung wird für die meisten produktionsumgebungen nicht empfohlen, da es ein Sicherheitsrisiko vorhanden sein können.  
  
```xml
<wsFederation passiveRedirectEnabled="true"   
              issuer="http://localhost:15839/wsFederationSTS/Issue"   
              realm="http://localhost:50969/"   
              reply="http://localhost:50969/"   
              requireHttps="false"   
              signOutReply="http://localhost:50969/SignedOutPage.html"   
              signOutQueryString="Param1=value2&Param2=value2"   
              persistentCookiesOnPassiveRedirects="true" />
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
