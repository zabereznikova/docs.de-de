---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 53f3943524c45a43ddb60553b8ff45f19df66b14
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152462"
---
# <a name="wsfederation"></a>\<wsFöderation>
Stellt die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> Konfiguration für das (WSFAM) bereit.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<FederationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFöderation>**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|authenticationType|Ein URI, der den Authentifizierungstyp angibt. Legt den WED-Bund-Anmeldeanforderungs-Wauth-Parameter fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wauth-Parameter nicht in der Anforderung enthalten ist.|  
|Frische|Der gewünschte Höchstalter für Authentifizierungsanforderungen in Minuten. Legt den wfresh-Parameter für eine WS-Verbund-Anmeldungsanforderung fest. Optional. Der Standardwert beträgt 0. Optional. **Warnung:**  In der nächsten Version von .NET `freshness` Framework 4.5 `xs:string` ist das Attribut `null`vom Typ und sein Standardwert wird .|  
|Homerealm|Der Home-Bereich des Identitätsanbieters (IdP), der für die Authentifizierung verwendet werden soll. Legt den whr-Parameter für eine WS-Verbund-Anmeldungsanforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der whr-Parameter nicht in der Anforderung enthalten ist.|  
|Issuer (Aussteller)|Der URI des beabsichtigten Tokenausstellers. Legt die Basis-URL von WS-Federation-Anmeldeanforderungen und Abmeldeanforderungen erforderlich fest.|  
|persistentCookiesOnPassiveUmleitungen|Gibt an, ob persistente Cookies bei der Authentifizierung ausgegeben werden. Optional. Der Standardwert ist "false", Cookies werden nicht ausgegeben.|  
|passiveRedirectEnabled|Gibt an, ob das WSFAM aktiviert ist, um nicht autorisierte Anforderungen automatisch an einen STS umzuleiten. Optional. Der Standardwert ist "true", nicht autorisierte Anforderungen werden automatisch umgeleitet.|  
|policy|Eine URL, die den Speicherort der entsprechenden Richtlinie angibt, die bei Anmeldeanforderungen verwendet werden soll. Der Standardwert ist eine leere Zeichenfolge. Legt den wp-Parameter für eine WS-Verbund-Anmeldungsanforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wp-Parameter nicht in der Anforderung enthalten ist.|  
|realm|Der URI des anfordernden Bereichs. (Ein URI, der die vertrauende Partei (RP) für den Sicherheitstokendienst (SECURITY Token Service, STS) identifiziert.) Legt den Anforderungsparameter wtrealm WS-Federation-Anmeldeanforderung fest. Erforderlich.|  
|reply|Eine URL, die die Adresse angibt, an der die Applikation der vertrauende Seite (RP) Antworten vom Sicherheitstokendienst (STS) empfangen möchte. Legt den WS-Federation-Anmeldeanforderungs-Wreply-Parameter fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wreply-Parameter nicht in der Anforderung enthalten ist.|  
|request|Die Token-Ausgabeanforderung. Legt den wreq-Parameter für eine WS-Verbund-Anmeldungsanforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wreq-Parameter nicht in der Anforderung enthalten ist. Ohne den Wreq- oder den Wreqptr-Parameter in die Anforderung einzubeziehen, bedeutet dies, dass der STS weiß, welche Art von Token ausgestellt werden soll.|  
|AnfragePtr|Eine URL, die den Speicherort der Tokenausstellungsanforderungen angibt. Legt den Parameter request wreqptr fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der Wreqptr-Parameter nicht in der Anforderung enthalten ist. Ohne den Wreq- oder den Wreqptr-Parameter in die Anforderung einzubeziehen, bedeutet dies, dass der STS weiß, welche Art von Token ausgestellt werden soll.|  
|requireHttps|Gibt an, ob die Kommunikation mit dem Sicherheitstokendienst (SECURITY Token Service, STS) das HTTPS-Protokoll verwenden muss. Optional. Der Standardwert ist "true", HTTPS muss verwendet werden.|  
|resource|Ein URI, der die Ressource identifiziert, auf die zugegriffen wird, die vertrauende Seite (RP) auf dem Sicherheitstokendienst (STS). Optional. Legt den Parameter WS-Federation Sign-in Request wres fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass der wres-Parameter nicht in der Anforderung enthalten ist. **Hinweis:** wres ist ein Legacy-Parameter. Geben `realm` Sie das Attribut an, das stattdessen den parameter wtrealm verwenden soll.|  
|signInQueryString|Stellt einen Erweiterbarkeitspunkt bereit, um anwendungsdefinierte Abfrageparameter in der WS-Federation-Anmeldeanforderungs-URL anzugeben. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in die Anforderung eingeschlossen werden sollen. Die Parameter werden als Abfragezeichenfolgenfragment mit `"param1=value1&param2=value2&param3=value3"` dem folgenden Formular angegeben: usw. **Hinweis:**  In einer Konfigurationsdatei muss das Zeichen "&" in der `&`Abfragezeichenfolge mit dem Entitätsverweis angegeben werden.|  
|signOutQueryString|Stellt einen Erweiterbarkeitspunkt bereit, um anwendungsdefinierte Abfrageparameter in der WS-Federation-Anmeldeanforderungs-URL anzugeben. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in die Anforderung eingeschlossen werden sollen. Die Parameter werden als Abfragezeichenfolgenfragment mit `"param1=value1&param2=value2&param3=value3"` dem folgenden Formular angegeben: usw. **Hinweis:**  In einer Konfigurationsdatei muss das Zeichen "&" in der `&`Abfragezeichenfolge mit dem Entitätsverweis angegeben werden.|  
|signOutReply|Gibt die URL an, an die der Client während der passiven Abmelden über das WS-Federation-Protokoll vom Sicherheitstokendienst (SECURITY Token Service, STS) umgeleitet werden soll. Legt den wreply-Parameter für eine WS-Federation-Abmeldeanforderung fest. Optional. Der Standardwert ist eine leere Zeichenfolge, die angibt, dass keine zusätzlichen Parameter in die Anforderung eingeschlossen werden sollen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<FederationConfiguration>](federationconfiguration.md)|Enthält die Einstellungen, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> die das (WSFAM) und das <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) konfigurieren.|  
  
## <a name="remarks"></a>Bemerkungen  
 Sie können `<wsFederation>` das Element verwenden, um die standardmäßigen WS-Federation-Parametereinstellungen und das Standardverhalten für das WSFAM zu konfigurieren. WS-Federation-Parametereinstellungen, `<wsFederation>` die unter dem Element <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> definiert sind, legen äquivalente Eigenschaften fest, die von der Klasse verfügbar gemacht werden. Diese Eigenschaften bleiben für jede anforderung, die vom WSFAM ausgegeben wird, gleich. Sie können die WS-Federation-Parameter während der Anforderungsverarbeitung dynamisch ändern, indem Sie Ereignishandler für die ereignisse hinzufügen, die von WSFAM verfügbar gemacht werden. z. B. das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> Ereignis. Weitere Informationen finden Sie in <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> der Dokumentation für die Klasse.  
  
 Das `<wsFederation>` Element wird <xref:System.IdentityModel.Services.Configuration.WSFederationElement> durch die Klasse dargestellt. Das Konfigurationsobjekt selbst wird <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> durch die Klasse dargestellt. Für <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> das <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Objekt, auf das über <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> die Eigenschaft zugegriffen wird, wird eine einzelne Instanz festgelegt, die eine Konfiguration für das WSFAM bereitstellt.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt ein `<wsFederation>` Element, das Einstellungen für das WSFAM angibt.  
  
> [!WARNING]
> In diesem Beispiel ist das WSFAM nicht erforderlich, um HTTPS zu verwenden. Dies liegt `requireHttps` daran, `<wsFederation>` dass `false`das Attribut für das Element festgelegt ist. Diese Einstellung wird für die meisten Produktionsumgebungen nicht empfohlen, da sie möglicherweise ein Sicherheitsrisiko darstellt.  
  
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
