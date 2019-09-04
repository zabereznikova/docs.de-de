---
title: <cookieHandler>
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: 853dc9817d080e59ac7a792576eda862bd0b1f1d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252029"
---
# <a name="cookiehandler"></a>\<cookieHandler>
Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , den der <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) zum Lesen und Schreiben von Cookies verwendet.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. IdentityModel. Services->** ](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationconfiguration->** ](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<cookiehandler->**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Gibt den Basis Namen für alle geschriebenen Cookies an. Der Standardwert ist "fedauth".|  
|path|Gibt den Pfadwert für alle geschriebenen Cookies an. Der Standardwert ist "HttpRuntime. AppDomainAppVirtualPath".|  
|Modus|Einer der <xref:System.IdentityModel.Services.CookieHandlerMode> -Werte, der die Art des von Sam verwendeten Cookie-Handlers angibt. Die folgenden Werte können verwendet werden:<br /><br /> -"Default" – identisch mit "segmentiert".<br />-"Chunked" – verwendet eine Instanz der <xref:System.IdentityModel.Services.ChunkedCookieHandler> -Klasse. Dieser cookiehandler stellt sicher, dass einzelne Cookies eine festgelegte maximale Größe nicht überschreiten. Dies wird erreicht, indem ein logisches Cookie ggf. in eine Reihe von Cookies übertragen wird.<br />-"Custom" – verwendet eine Instanz einer benutzerdefinierten Klasse, die <xref:System.IdentityModel.Services.CookieHandler>von abgeleitet ist. Auf die abgeleitete Klasse wird durch `<customCookieHandler>` das untergeordnete-Element verwiesen.<br /><br /> Der Standardwert ist "Default".|  
|persistentSessionLifetime|Gibt die Lebensdauer von persistenten Sitzungen an. Wenn 0 (null), werden vorübergehende Sitzungen immer verwendet. Der Standardwert ist "0:0:0", der eine vorübergehende Sitzung angibt. Der Höchstwert ist "365:0:0", wodurch eine Sitzung von 365 Tagen angegeben wird. Der Wert sollte gemäß der folgenden Einschränkung angegeben werden: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, wobei der äußteste Wert Days angibt, der mittlere Wert (falls vorhanden) Stunden angibt und der äußteste Wert (falls vorhanden) Minuten angibt.|  
|requireSsl|Gibt an, ob das Flag "Secure" für geschriebene Cookies ausgegeben wird. Wenn dieser Wert festgelegt ist, sind die Anmelde Sitzungs Cookies nur über HTTPS verfügbar. Der Standardwert ist "true".|  
|hideFromScript|Steuert, ob das Flag "HttpOnly" für geschriebene Cookies ausgegeben wird. Bestimmte Webbrowser berücksichtigen dieses Flag, indem das Client seitige Skript keinen Zugriff auf den Cookie-Wert hat. Der Standardwert ist "true".|  
|Domäne|Der Domänen Wert für alle geschriebenen Cookies. Der Standardwert ist "".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<chunkedCookieHandler>](chunkedcookiehandler.md)|Konfiguriert den <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Dieses Element kann nur vorhanden sein, wenn `mode` das-Attribut `<cookieHandler>` des-Elements "Default" oder "Chunked" ist.|  
|[\<customCookieHandler>](customcookiehandler.md)|Legt den Typ des benutzerdefinierten Cookie-Handlers fest. Dieses Element muss vorhanden sein, wenn `mode` das-Attribut `<cookieHandler>` des-Elements "Custom" ist. Er darf nicht für andere Werte des `mode` Attributs vorhanden sein. Der benutzerdefinierte Typ muss von der <xref:System.IdentityModel.Services.CookieHandler> -Klasse abgeleitet werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Enthält die Einstellungen, mit denen <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) <xref:System.IdentityModel.Services.SessionAuthenticationModule> und (Sam) konfiguriert werden.|  
  
## <a name="remarks"></a>Hinweise  
 Der <xref:System.IdentityModel.Services.CookieHandler> ist für das Lesen und Schreiben von unformatierten Cookies auf der http-Protokollebene verantwortlich. Sie können einen <xref:System.IdentityModel.Services.ChunkedCookieHandler> oder einen benutzerdefinierten cookiehandler konfigurieren <xref:System.IdentityModel.Services.CookieHandler> , der von der-Klasse abgeleitet wird.  
  
 Legen Sie zum Konfigurieren eines segmentierten cookiehandlers das Mode-Attribut auf "aufgeteilte" oder "Default" fest. Die Standard Segmentgröße beträgt 2000 Bytes, aber Sie können optional eine andere Segmentgröße angeben, indem Sie ein `<chunkedCookieHandler>` untergeordnetes Element einschließen.  
  
 Legen Sie zum Konfigurieren eines benutzerdefinierten cookiehandlers das Mode-Attribut auf "Custom" fest. Sie müssen auch ein `<customCookieHandler>` untergeordnetes Element angeben, das auf den Typ des benutzerdefinierten Handlers verweist.  
  
 Das `<cookieHandler>` -Element wird durch die <xref:System.IdentityModel.Services.CookieHandlerElement> -Klasse dargestellt. Der in der Konfiguration angegebene cookiehandler ist über <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> die-Eigenschaft <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> des-Objekts verfügbar <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> , das in der-Eigenschaft festgelegt ist.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code `<cookieHandler>` zeigt ein-Element. Da das `mode` -Attribut in diesem Beispiel nicht angegeben wird, wird der standardmäßige Cookie-Handler von Sam verwendet. Dies ist eine Instanz der <xref:System.IdentityModel.Services.ChunkedCookieHandler> -Klasse. Da das `<chunkedCookieHandler>` untergeordnete-Element nicht angegeben ist, wird die Standard Segmentgröße verwendet. HTTPS ist nicht erforderlich, da das `requireSsl` -Attribut fest `false`gelegt ist.  
  
> [!WARNING]
> In diesem Beispiel ist HTTPS nicht erforderlich, um Sitzungs Cookies zu schreiben. Dies liegt daran, `requireSsl` dass das- `<cookieHandler>` Attribut des-Elements `false`auf festgelegt ist. Diese Einstellung wird für die meisten Produktionsumgebungen nicht empfohlen, da Sie ein Sicherheitsrisiko darstellen kann.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Services.CookieHandler>
- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
