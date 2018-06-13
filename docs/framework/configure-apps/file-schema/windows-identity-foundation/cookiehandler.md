---
title: '&lt;"cookiehandler"&gt;'
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7fcdf1e89c3b68daa36ee80fe7234737c61a5a3c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758138"
---
# <a name="ltcookiehandlergt"></a>&lt;"cookiehandler"&gt;
Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) zum Lesen und Schreiben von Cookies verwendet.  
  
 \<system.identityModel.services >  
\<FederationConfiguration >  
\<"cookiehandler" >  
  
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
|Name|Gibt den Basisnamen für Cookies geschrieben. Der Standardwert ist "FedAuth".|  
|path|Gibt an, der Pfadwert für Cookies geschrieben. Der Standardwert ist "HttpRuntime.AppDomainAppVirtualPath".|  
|mode|Eines der <xref:System.IdentityModel.Services.CookieHandlerMode> Werte, der angibt, die Art der Cookie-Handler, die von der Sicherheitskontenverwaltung verwendet. Die folgenden Werte können verwendet werden:<br /><br /> -"Default" – "Chunked" identisch.<br />-"Aufgeteilte" – verwendet eine Instanz der <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse. Diesen Cookie-Handler wird sichergestellt, dass einzelne Cookies eine festgelegte maximale Größe nicht überschreiten. Dies wird erreicht, indem "Segmentierung" potenziell eine logische Cookie in eine Anzahl von Cookies auf das Netzwerk wird.<br />-"Custom" – wird eine Instanz einer benutzerdefinierten Klasse abgeleitet <xref:System.IdentityModel.Services.CookieHandler>. Die abgeleitete Klasse verweist auf die `<customCookieHandler>` untergeordnetes Element.<br /><br /> Der Standardwert ist "Default".|  
|persistentSessionLifetime|Die Lebensdauer von persistenten Sitzungen angibt. Wenn der Wert 0 ist, werden immer vorübergehende Sitzungen verwendet. Der Standardwert ist "0:0:0", die eine vorübergehende Sitzung angibt. Der maximale Wert ist "365:0:0", die eine Sitzung von 365 Tagen angibt. Der Wert sollte entsprechend der folgenden Einschränkung angegeben werden: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, wobei der äußeren linken Wert gibt die Tage an, der mittlere Wert (falls vorhanden) gibt die Stunden und der äußeren rechten Wert (falls vorhanden) gibt die Minuten an.|  
|RequireSsl|Gibt an, ob das Kennzeichen "Secure" für Cookies geschrieben ausgegeben werden. Wenn dieser Wert festgelegt ist, werden die Anmeldeseite Sitzungscookies über HTTPS nur verfügbar sein. Der Standardwert ist "true".|  
|hideFromScript|Steuert, ob das Flag "HttpOnly" für Cookies geschrieben ausgegeben wird. Bestimmte Webbrowsern Auswirkungen dieses Flag durch Speicherung der Zugriff auf den Cookiewert Skriptdatei auf Clientseite. Der Standardwert ist "true".|  
|Domäne|Der Domänenwert für Cookies geschrieben werden soll. Der Standardwert ist "".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ChunkedCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|Konfiguriert die <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Dieses Element kann nur vorhanden sein, wenn die `mode` Attribut des der `<cookieHandler>` Element ist "Default" oder "Aufgeteilte".|  
|[\<CustomCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Legt die benutzerdefinierten cookiehandlertyp fest. Dieses Element muss vorhanden sein wenn die `mode` Attribut von der `<cookieHandler>` Element ist "Custom". Es kann nicht vorhanden sein, um alle anderen Werte von der `mode` Attribut. Der benutzerdefinierte Typ muss von abgeleitet werden die <xref:System.IdentityModel.Services.CookieHandler> Klasse.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Enthält die Einstellungen zur Konfiguration der <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Hinweise  
 Die <xref:System.IdentityModel.Services.CookieHandler> ist verantwortlich für das Lesen und Schreiben von Rohdaten Cookies der HTTP-Protokoll auf. Sie können konfigurieren, entweder eine <xref:System.IdentityModel.Services.ChunkedCookieHandler> oder ein benutzerdefinierten Cookie Handler abgeleitet der <xref:System.IdentityModel.Services.CookieHandler> Klasse.  
  
 Um einen Handler aufgeteilte Cookie zu konfigurieren, legen Sie die Mode-Attribut auf "Chunked" oder "Default". Die Standardblockgröße beträgt 2000 Bytes, aber Sie können optional eine andere Segmentgröße angeben, indem einschließlich einer `<chunkedCookieHandler>` untergeordnetes Element.  
  
 Um einen benutzerdefinierten Cookie-Handler zu konfigurieren, legen Sie die Mode-Attribut auf "Custom". Sie müssen auch angeben, ein `<customCookieHandler>` untergeordnetes Element, das den Typ des benutzerdefinierten Handler verweist.  
  
 Die `<cookieHandler>` Element dargestellt ist, durch die <xref:System.IdentityModel.Services.CookieHandlerElement> Klasse. Der Cookie-Handler, der in der Konfiguration angegeben wurde steht über die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> Eigenschaft von der <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Objektsatz auf die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt ein `<cookieHandler>` Element. In diesem Beispiel da die `mode` Attribut nicht angegeben wird, der Standardhandler für das Cookie wird von der SAM verwendet werden. Dies ist eine Instanz von der <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse. Da die `<chunkedCookieHandler>` untergeordnetes Element nicht angegeben ist, wird die Standardblockgröße verwendet werden. HTTPS wird nicht benötigt werden, da die `requireSsl` -Attribut festgelegt ist `false`.  
  
> [!WARNING]
>  In diesem Beispiel muss HTTPS nicht Sitzungscookies schreiben. Grund hierfür ist die `requireSsl` -Attribut auf die `<cookieHandler>` -Elementgruppe ist `false`. Diese Einstellung wird für die meisten produktionsumgebungen nicht empfohlen, da es ein Sicherheitsrisiko vorhanden sein können.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Services.CookieHandler>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>
