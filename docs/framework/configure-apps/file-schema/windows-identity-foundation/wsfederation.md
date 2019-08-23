---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 57a1513f6de7f7bd9ea441b6cbc3db6a06d76fc2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940261"
---
# <a name="wsfederation"></a>\<wsFederation>
Stellt die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Konfiguration für (wsfam) bereit.  
  
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
|authenticationType|Ein URI, der den Authentifizierungstyp angibt. Legt den WAUTH-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der WAUTH-Parameter nicht in der Anforderung enthalten ist.|  
|vermittelt|Das gewünschte maximale Alter von Authentifizierungsanforderungen (in Minuten). Legt den wfresh-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Optional. Der Standardwert ist 0. Optional. **Warnung:**  In der nächsten Version von .NET Framework 4,5 ist das `freshness` -Attribut vom Typ `xs:string` , und sein Standardwert `null`ist.|  
|homeRealm|Der Startbereich des Identitäts Anbieters (IDP), der für die Authentifizierung verwendet werden soll. Legt den whr-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der whr-Parameter nicht in der Anforderung enthalten ist.|  
|issuer|Der URI des vorgesehenen Tokenausstellers. Legt die Basis-URL der WS-Verbund-Anmeldungs Anforderungen und Abmelde Anforderungen fest.|  
|persistentCookiesOnPassiveRedirects|Gibt an, ob persistente Cookies bei der Authentifizierung ausgegeben werden. Optional. Der Standardwert ist "false", Cookies werden nicht ausgegeben.|  
|passiveRedirectEnabled|Gibt an, ob die wsfam aktiviert ist, um nicht autorisierte Anforderungen automatisch an einen STS umzuleiten. Optional. Der Standardwert ist "true", nicht autorisierte Anforderungen werden automatisch umgeleitet.|  
|Richtlinie|Eine URL, die den Speicherort der relevanten Richtlinie angibt, die bei Anmelde Anforderungen verwendet werden soll. Der Standardwert ist eine leere Zeichenfolge. Legt den WP-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der WP-Parameter nicht in der Anforderung enthalten ist.|  
|realm|Der URI des angeforderten Bereichs. (Ein URI, der die vertrauende Seite (RP) für den Sicherheitstokendienst (Security Token Service, STS) identifiziert.) Legt den Anforderungs Parameter für den wtrealm-WS-Verbund-Anmelde Anforderung fest. Erforderlich.|  
|reply|Eine URL, die die Adresse identifiziert, an der die Anwendung der vertrauenden Seite Antworten vom Sicherheitstokendienst (Security Token Service, STS) empfangen möchte. Legt den wreply-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wreply-Parameter nicht in der Anforderung enthalten ist.|  
|request|Die tokenausstellungsanforderung. Legt den wreq-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wreq-Parameter nicht in der Anforderung enthalten ist. Wenn der wreq-Parameter oder der wreqptr-Parameter in der Anforderung nicht enthalten ist, bedeutet dies, dass der STS weiß, welche Art von Token ausgestellt werden muss|  
|requestptr|Eine URL, die den Speicherort der tokenausstellungsanforderung angibt. Legt den wreqptr-Parameter der Anforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wreqptr-Parameter nicht in der Anforderung enthalten ist. Wenn der wreq-Parameter oder der wreqptr-Parameter in der Anforderung nicht enthalten ist, bedeutet dies, dass der STS weiß, welche Art von Token ausgestellt werden muss|  
|requireHttps|Gibt an, ob die Kommunikation mit dem Sicherheitstokendienst (STS) das HTTPS-Protokoll verwenden muss. Optional. Der Standardwert ist "true", HTTPS muss verwendet werden.|  
|Ressource|Ein URI, der die Ressource identifiziert, auf die zugegriffen wird, der vertrauenden Seite (RP) für den Sicherheitstokendienst (STS). Optional. Legt den wres-Parameter für die WS-Verbund-Anmeldungs Anforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wres-Parameter nicht in der Anforderung enthalten ist. **Hinweis:** wres ist ein Legacy Parameter. Geben Sie `realm` das-Attribut an, um stattdessen den wtrealm-Parameter zu verwenden.|  
|signInQueryString|Stellt einen Erweiterbarkeits Punkt bereit, um Anwendungs definierte Abfrage Parameter in der URL der WS-Verbund-Anmeldungs Anforderung anzugeben. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in die Anforderung eingeschlossen werden sollen. Die Parameter werden als Abfrage Zeichenfolgen-Fragmente im folgenden Format angegeben `"param1=value1&param2=value2&param3=value3"` : usw. **Hinweis**:  In einer Konfigurationsdatei muss das Zeichen "&" in der Abfrage Zeichenfolge mit dem zugehörigen Entitäts `&`Verweis angegeben werden.|  
|signOutQueryString|Stellt einen Erweiterbarkeits Punkt bereit, um Anwendungs definierte Abfrage Parameter in der URL der WS-Verbund-Anmeldungs Anforderung anzugeben. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in die Anforderung eingeschlossen werden sollen. Die Parameter werden als Abfrage Zeichenfolgen-Fragmente im folgenden Format angegeben `"param1=value1&param2=value2&param3=value3"` : usw. **Hinweis**:  In einer Konfigurationsdatei muss das Zeichen "&" in der Abfrage Zeichenfolge mit dem zugehörigen Entitäts `&`Verweis angegeben werden.|  
|signOutReply|Gibt die URL an, an die der Client vom Sicherheitstokendienst (STS) während der passiven Abmeldung über das WS-Verbund-Protokoll umgeleitet werden soll. Legt den wreply-Parameter für eine WS-Verbund-Abmelde Anforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in die Anforderung eingeschlossen werden sollen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Enthält die Einstellungen, mit denen <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule> und (Sam) konfiguriert werden.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können das `<wsFederation>` -Element verwenden, um die Standardeinstellungen für WS-Verbund Parameter und das Standardverhalten für wsfam zu konfigurieren. `<wsFederation>` Einstellungen<xref:System.IdentityModel.Services.WSFederationAuthenticationModule> für WS-Verbund Parameter, die unter dem-Element definiert sind, legen äquivalente Eigenschaften fest Diese Eigenschaften bleiben für jede Anforderung, die von wsfam ausgegeben wird, unverändert. Die WS-Verbund-Parameter können während der Anforderungs Verarbeitung dynamisch geändert werden, indem Ereignishandler für die von wsfam verfügbar gemachten Ereignisse hinzugefügt werden. beispielsweise das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> -Ereignis. Weitere Informationen finden Sie in der Dokumentation für die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> -Klasse.  
  
 Das `<wsFederation>` -Element wird durch die <xref:System.IdentityModel.Services.Configuration.WSFederationElement> -Klasse dargestellt. Das Konfigurationsobjekt selbst wird durch die <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> -Klasse dargestellt. Für das <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Objekt, auf das über die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> -Eigenschaft zugegriffen wird, wird eine einzelne Instanz festgelegt, und es wird eine Konfiguration für wsfam bereitstellt  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code `<wsFederation>` zeigt ein-Element, das Einstellungen für das wsfam angibt.  
  
> [!WARNING]
>  In diesem Beispiel ist das wsfam nicht erforderlich, um HTTPS zu verwenden. Dies liegt daran, `requireHttps` dass das- `<wsFederation>` Attribut für das `false`-Element festgelegt ist. Diese Einstellung wird für die meisten Produktionsumgebungen nicht empfohlen, da Sie ein Sicherheitsrisiko darstellen kann.  
  
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
