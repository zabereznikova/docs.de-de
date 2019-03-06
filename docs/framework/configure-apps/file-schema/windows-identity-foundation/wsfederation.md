---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 801970ec05fc88587a5b45b5bb3a855d1a81afb3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356090"
---
# <a name="wsfederation"></a>\<wsFederation>
Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
\<system.identityModel.services>  
\<federationConfiguration>  
\<wsFederation>  
  
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
|authenticationType|Ein URI, der den Authentifizierungstyp angibt. Legt den Wauth-Parameters von WS-Verbund-anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge und gibt an, dass es sich bei der Wauth-Parameter nicht in der Anforderung enthalten ist.|  
|Aktualität|Der gewünschte Höchstalter für authentifizierungsanforderungen in Minuten. Legt den Wfresh-Parameter in WS-Verbund-anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist 0. Dies ist optional. **Warnung:**  In der nächsten Version von .NET Framework 4.5 den `freshness` Attributs werden vom Typ `xs:string` und seinen Standardwert `null`.|  
|homeRealm|Den Startbereich des Identitätsanbieters (IP) für die Authentifizierung verwenden. Legt den Whr-Parameter in WS-Verbund-anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge und gibt an, dass es sich bei der Whr-Parameter nicht in der Anforderung enthalten ist.|  
|issuer|Der URI des den beabsichtigten Aussteller des Tokens. Legt das base URL des WS-Verbund-anmeldeanforderungen und abmeldeanforderungen erforderlich sind.|  
|persistentCookiesOnPassiveRedirects|Gibt an, ob permanente Cookies auf Authentifizierung ausgegeben werden. Dies ist optional. Der Standardwert ist "false", Cookies werden nicht ausgegeben.|  
|passiveRedirectEnabled|Gibt an, ob das WSFAM aktiviert ist, nicht autorisierte Anforderungen automatisch an einen STS umleiten. Dies ist optional. Der Standardwert ist "true", nicht autorisierte Anforderungen werden automatisch umgeleitet.|  
|behandelte Ausnahmen|Eine URL, die den Speicherort der betreffenden Richtlinie für die Verwendung auf anmeldeanforderungen angibt. Der Standardwert ist eine leere Zeichenfolge. Legt den wp-Parameter in WS-Verbund-anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge und gibt an, dass es sich bei der wp-Parameter nicht in der Anforderung enthalten ist.|  
|realm|Der URI des anfordernden Bereichs. (Ein URI, der die vertrauende Seite (RP) an den Sicherheitstokendienst (STS) identifiziert.) Legt den Wtrealm WS-Verbund-SSO-in-Parameter-Anforderung fest. Erforderlich.|  
|reply|Eine URL, die Adresse angibt, an der die Anwendung der vertrauenden Seite (Relying Party, RP) Antworten aus dem Sicherheitstokendienst (STS) empfangen möchte. Legt den Wreply-Parameter in WS-Verbund-anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge und gibt an, dass es sich bei der Wreply-Parameter nicht in der Anforderung enthalten ist.|  
|request|Die Anforderung der tokenausstellung. Legt den Wreq-Parameter in WS-Verbund-anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge und gibt an, dass es sich bei der Wreq-Parameter nicht in der Anforderung enthalten ist. Einschließlich nicht den Wreq oder den Wreqptr-Parameter in der Anforderung impliziert, dass der STS weiß, welche Art von Token ausstellen.|  
|requestPtr|Eine URL, der den Speicherort der tokenausstellungsanforderungen angibt. Legt den Wreqptr-Parameter fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge und gibt an, dass es sich bei der Wreqptr-Parameter nicht in der Anforderung enthalten ist. Einschließlich nicht den Wreq oder den Wreqptr-Parameter in der Anforderung impliziert, dass der STS weiß, welche Art von Token ausstellen.|  
|requireHttps|Gibt an, ob die Kommunikation mit dem Sicherheitstokendienst (STS), HTTPS-Protokoll verwenden muss. Dies ist optional. Der Standardwert ist "true", muss HTTPS verwendet werden.|  
|Ressource|Ein URI, der die Ressource zugegriffen wird, wird die vertrauende Seite (RP) identifiziert, zu der an den Sicherheitstokendienst (STS). Dies ist optional. Legt den Wres-Parameter in WS-Verbund-anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge und gibt an, dass es sich bei der Wres-Parameter nicht in der Anforderung enthalten ist. **Hinweis:** Wres ist ein legacy-Parameter. Geben Sie die `realm` Attribut zu verwenden. den Wtrealm-Parameter.|  
|signInQueryString|Bietet einen Erweiterungspunkt darstellen, um anwendungsdefinierte Abfrageparameter in der URL des WS-Verbund-anmeldungsanforderung anzugeben. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in der Anforderung enthalten sein soll. Die Parameter werden als ein Fragment einer Abfrage im folgenden Format angegeben: `"param1=value1&param2=value2&param3=value3"` und so weiter. **Hinweis**:  In einer Konfigurationsdatei das "&" Zeichen in der Abfragezeichenfolge muss angegeben werden, mithilfe der Entitätsverweis `&`.|  
|signOutQueryString|Bietet einen Erweiterungspunkt darstellen, um anwendungsdefinierte Abfrageparameter in der URL des WS-Verbund-anmeldungsanforderung anzugeben. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in der Anforderung enthalten sein soll. Die Parameter werden als ein Fragment einer Abfrage im folgenden Format angegeben: `"param1=value1&param2=value2&param3=value3"` und so weiter. **Hinweis**:  In einer Konfigurationsdatei das "&" Zeichen in der Abfragezeichenfolge muss angegeben werden, mithilfe der Entitätsverweis `&`.|  
|signOutReply|Gibt Sie die URL, an dem der Client vom Sicherheitstokendienst (STS) umgeleitet werden soll, während der passiven Abmeldung durch das WS-Verbund-Protokoll. Legt den Wreply-Parameter für eine WS-Verbund-abmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in der Anforderung enthalten sein soll.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Enthält Einstellungen, konfigurieren die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `<wsFederation>` Element, um Standardeinstellungen für WS-Verbund-Parameter und Standardverhalten für das WSFAM konfigurieren. WS-Verbund-parametereinstellungen unter definiert die `<wsFederation>` -Elementgruppe entsprechende Eigenschaften verfügbar gemacht werden, indem die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Klasse. Diese Eigenschaften sind identisch für jede Anforderung, der von WSFAM ausgegeben. Sie können die WS-Verbund-Parameter dynamisch ändern, während der anforderungsverarbeitung durch Hinzufügen von Ereignishandlern für die Ereignisse, die von WSFAM verfügbar gemacht werden. z. B. die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> Ereignis. Weitere Informationen finden Sie in der Dokumentation für die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Klasse.  
  
 Die `<wsFederation>` Element wird dargestellt, durch die <xref:System.IdentityModel.Services.Configuration.WSFederationElement> Klasse. Das Konfigurationsobjekt selbst wird dargestellt, durch die <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> Klasse. Ein einzelnes <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> Instanz wird festgelegt, auf die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> -Objekt, das über zugegriffen wird die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> Eigenschaft und die Konfiguration für das WSFAM stellt.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt ein `<wsFederation>` -Element, das Einstellungen für das WSFAM angibt.  
  
> [!WARNING]
>  In diesem Beispiel ist das WSFAM nicht zur Verwendung von HTTPS erforderlich. Grund hierfür ist die `requireHttps` -Attribut für die `<wsFederation>` -Elements festgelegt `false`. Diese Einstellung ist für die meisten produktionsumgebungen nicht empfohlen, wie sie ein Sicherheitsrisiko darstellen kann.  
  
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
- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
