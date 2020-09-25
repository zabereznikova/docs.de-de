---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 93661af6c907d8cce1a73536a8ebca7bd53c00d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185508"
---
# \<wsFederation>

Stellt die Konfiguration für <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) bereit.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederation>**  
  
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
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|authenticationType|Ein URI, der den Authentifizierungstyp angibt. Legt den WAUTH-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der WAUTH-Parameter nicht in der Anforderung enthalten ist.|  
|vermittelt|Der gewünschte Höchstalter für Authentifizierungsanforderungen in Minuten. Legt den wfresh-Parameter für eine WS-Verbund-Anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist 0. Dies ist optional. **Warnung:**  In der nächsten Version von .NET Framework 4,5 ist das `freshness` -Attribut vom Typ, `xs:string` und sein Standardwert ist `null` .|  
|homeRealm|Der Startbereich des Identitäts Anbieters (IDP), der für die Authentifizierung verwendet werden soll. Legt den whr-Parameter für eine WS-Verbund-Anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der whr-Parameter nicht in der Anforderung enthalten ist.|  
|Issuer (Aussteller)|Der URI des vorgesehenen Tokenausstellers. Legt die Basis-URL der WS-Verbund-Anmeldungs Anforderungen und Abmelde Anforderungen fest.|  
|persistentcookiesonpassivereumleitungen|Gibt an, ob persistente Cookies bei der Authentifizierung ausgegeben werden. Dies ist optional. Der Standardwert ist "false", Cookies werden nicht ausgegeben.|  
|passiveredirectenabled|Gibt an, ob die wsfam aktiviert ist, um nicht autorisierte Anforderungen automatisch an einen STS umzuleiten. Dies ist optional. Der Standardwert ist "true", nicht autorisierte Anforderungen werden automatisch umgeleitet.|  
|policy|Eine URL, die den Speicherort der relevanten Richtlinie angibt, die bei Anmelde Anforderungen verwendet werden soll. Der Standardwert ist eine leere Zeichenfolge. Legt den wp-Parameter für eine WS-Verbund-Anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der WP-Parameter nicht in der Anforderung enthalten ist.|  
|realm|Der URI des angeforderten Bereichs. (Ein URI, der die vertrauende Seite (RP) für den Sicherheitstokendienst (Security Token Service, STS) identifiziert.) Legt den Anforderungs Parameter für den wtrealm-WS-Verbund-Anmelde Anforderung fest. Erforderlich.|  
|reply|Eine URL, die die Adresse angibt, an der die Applikation der vertrauende Seite (RP) Antworten vom Sicherheitstokendienst (STS) empfangen möchte. Legt den wreply-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wreply-Parameter nicht in der Anforderung enthalten ist.|  
|request|Die tokenausstellungsanforderung. Legt den wreq-Parameter für eine WS-Verbund-Anmeldungsanforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wreq-Parameter nicht in der Anforderung enthalten ist. Wenn der wreq-Parameter oder der wreqptr-Parameter in der Anforderung nicht enthalten ist, bedeutet dies, dass der STS weiß, welche Art von Token ausgestellt werden muss|  
|requestptr|Eine URL, die den Speicherort der Tokenausstellungsanforderungen angibt. Legt den wreqptr-Parameter der Anforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wreqptr-Parameter nicht in der Anforderung enthalten ist. Wenn der wreq-Parameter oder der wreqptr-Parameter in der Anforderung nicht enthalten ist, bedeutet dies, dass der STS weiß, welche Art von Token ausgestellt werden muss|  
|requireHttps|Gibt an, ob die Kommunikation mit dem Sicherheitstokendienst (STS) das HTTPS-Protokoll verwenden muss. Dies ist optional. Der Standardwert ist "true", HTTPS muss verwendet werden.|  
|resource|Ein URI, der die Ressource identifiziert, auf die zugegriffen wird, die vertrauende Seite (RP) auf dem Sicherheitstokendienst (STS). Dies ist optional. Legt den wres-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wres-Parameter nicht in der Anforderung enthalten ist. **Hinweis:**  wres ist ein Legacy Parameter. Geben Sie das- `realm` Attribut an, um stattdessen den wtrealm-Parameter zu verwenden.|  
|signinquerystring|Stellt einen Erweiterbarkeits Punkt bereit, um Anwendungs definierte Abfrage Parameter in der URL der WS-Verbund-Anmeldungs Anforderung anzugeben. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in die Anforderung eingeschlossen werden sollen. Die Parameter werden als Abfrage Zeichenfolgen-Fragmente im folgenden Format angegeben: `"param1=value1&param2=value2&param3=value3"` usw. **Hinweis:**  In einer Konfigurationsdatei muss das Zeichen "&" in der Abfrage Zeichenfolge mit dem zugehörigen Entitäts Verweis angegeben werden `&` .|  
|signoutquerystring|Stellt einen Erweiterbarkeits Punkt bereit, um Anwendungs definierte Abfrage Parameter in der URL der WS-Verbund-Anmeldungs Anforderung anzugeben. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in die Anforderung eingeschlossen werden sollen. Die Parameter werden als Abfrage Zeichenfolgen-Fragmente im folgenden Format angegeben: `"param1=value1&param2=value2&param3=value3"` usw. **Hinweis:**  In einer Konfigurationsdatei muss das Zeichen "&" in der Abfrage Zeichenfolge mit dem zugehörigen Entitäts Verweis angegeben werden `&` .|  
|signply|Gibt die URL an, an die der Client vom Sicherheitstokendienst (STS) während der passiven Abmeldung über das WS-Verbund-Protokoll umgeleitet werden soll. Legt den wreply-Parameter für eine WS-Verbund-Abmelde Anforderung fest. Dies ist optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in die Anforderung eingeschlossen werden sollen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Enthält die Einstellungen, mit denen <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) und <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) konfiguriert werden.|  
  
## <a name="remarks"></a>Bemerkungen  

 Sie können das `<wsFederation>` -Element verwenden, um die Standardeinstellungen für WS-Verbund Parameter und das Standardverhalten für wsfam zu konfigurieren. Einstellungen für WS-Verbund Parameter, die unter dem-Element definiert sind, `<wsFederation>` legen äquivalente Eigenschaften fest <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Diese Eigenschaften bleiben für jede Anforderung, die von wsfam ausgegeben wird, unverändert. Die WS-Verbund-Parameter können während der Anforderungs Verarbeitung dynamisch geändert werden, indem Ereignishandler für die von wsfam verfügbar gemachten Ereignisse hinzugefügt werden. beispielsweise das- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> Ereignis. Weitere Informationen finden Sie in der Dokumentation für die- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Klasse.  
  
 Das- `<wsFederation>` Element wird durch die- <xref:System.IdentityModel.Services.Configuration.WSFederationElement> Klasse dargestellt. Das Konfigurationsobjekt selbst wird durch die- <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> Klasse dargestellt. Für <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> das <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Objekt, auf das über die-Eigenschaft zugegriffen wird, wird eine einzelne Instanz festgelegt, und es wird eine <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> Konfiguration für wsfam bereitstellt  
  
## <a name="example"></a>Beispiel  

 Der folgende XML-Code zeigt ein- `<wsFederation>` Element, das Einstellungen für das wsfam angibt.  
  
> [!WARNING]
> In diesem Beispiel ist das wsfam nicht erforderlich, um HTTPS zu verwenden. Dies liegt daran, dass das- `requireHttps` Attribut für das- `<wsFederation>` Element festgelegt ist `false` . Diese Einstellung wird für die meisten Produktionsumgebungen nicht empfohlen, da Sie ein Sicherheitsrisiko darstellen kann.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
