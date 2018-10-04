---
title: '&lt;cookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
ms.openlocfilehash: 99bf6edb4e4f631eba292990c65c1f0c8553d8c0
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48580221"
---
# <a name="ltcookiehandlergt"></a>&lt;cookieHandler&gt;
Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) zum Lesen und Schreiben von Cookies verwendet.  
  
 \<system.identityModel.services >  
\<FederationConfiguration >  
\<CookieHandler >  
  
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
|path|Gibt den Pfadwert für alle Cookies geschrieben. Der Standardwert ist "HttpRuntime.AppDomainAppVirtualPath".|  
|mode|Eines der <xref:System.IdentityModel.Services.CookieHandlerMode> Werte, der die Art der von SAM verwendete cookiehandler angibt. Die folgenden Werte können verwendet werden:<br /><br /> -"Default", "Chunked" identisch.<br />-"Aufgeteilte" – wird eine Instanz der dem <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse. Dieses Cookie-Handler wird sichergestellt, dass es sich bei einzelner Cookies eine festgelegte maximale Größe nicht überschreiten. Dabei wird "chunking" möglicherweise eine logische Cookie in eine Anzahl von Cookies auf das Netzwerk.<br />-"Custom" – wird eine Instanz einer benutzerdefinierten Klasse, die von abgeleiteten <xref:System.IdentityModel.Services.CookieHandler>. Die abgeleitete Klasse verweist auf die `<customCookieHandler>` untergeordnetes Element.<br /><br /> Der Standardwert ist "Default".|  
|persistentSessionLifetime|Gibt die Lebensdauer permanenter Sitzungen. Bei NULL werden immer flüchtige Sitzungen verwendet. Der Standardwert ist "0:0:0", die eine vorübergehende Sitzung angibt. Der maximale Wert ist "365:0:0", die eine Sitzung von 365 Tagen angibt. Der Wert muss angegeben werden, entsprechend die folgende Einschränkung: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, wobei der äußeren linken Wert gibt die Tage an, der Mittelwert (falls vorhanden) gibt die Stunden und der äußeren rechten Wert (falls vorhanden) gibt die Minuten.|  
|"RequireSSL"|Gibt an, ob die Kennzeichen "Secure" für jede geschriebene Cookies ausgegeben werden. Wenn dieser Wert festgelegt ist, werden die Anmeldung Sitzungscookies über HTTPS nur verfügbar sein. Der Standardwert ist "true".|  
|hideFromScript|Steuert, ob das Flag "HttpOnly" für jede geschriebene Cookies ausgegeben wird. Bestimmte Webbrowser berücksichtigt dieses Flag werden, da der Client-seitige Skript Zugriff auf den Cookiewert an. Der Standardwert ist "true".|  
|Domäne|Der Domänenwert für Cookies geschrieben. Der Standardwert ist "".|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ChunkedCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|Konfiguriert die <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Dieses Element kann nur vorhanden sein, wenn die `mode` Attribut der `<cookieHandler>` -Element ist "Default" oder "Aufgeteilte".|  
|[\<CustomCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Legt fest, den Handlertyp der benutzerdefinierten Cookies. Dieses Element muss vorhanden sein wenn die `mode` Attribut der `<cookieHandler>` Element ist "Custom". Es kann nicht für alle anderen Werte vorhanden sein. die `mode` Attribut. Aus der benutzerdefinierte Typ abgeleitet werden die <xref:System.IdentityModel.Services.CookieHandler> Klasse.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Enthält Einstellungen, konfigurieren die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Hinweise  
 Die <xref:System.IdentityModel.Services.CookieHandler> ist verantwortlich für das Lesen und Schreiben von Rohdaten-Cookies auf den HTTP-Protokoll auf. Sie können konfigurieren, entweder eine <xref:System.IdentityModel.Services.ChunkedCookieHandler> oder ein benutzerdefinierten cookiehandler abgeleitet der <xref:System.IdentityModel.Services.CookieHandler> Klasse.  
  
 Um einen segmentierten cookiehandler konfigurieren zu können, legen Sie das Mode-Attribut auf "Chunked" oder "Default". Die standardmäßige Segmentgröße beträgt 2000 Bytes, aber optional können Sie eine andere Blockgröße angeben, durch Einschließen einer `<chunkedCookieHandler>` untergeordnetes Element.  
  
 Um einen benutzerdefinierten cookiehandler konfigurieren zu können, legen Sie das Mode-Attribut auf "Benutzerdefiniert". Sie müssen auch angeben, ein `<customCookieHandler>` untergeordneten-Element, das den Typ des benutzerdefinierten Handler verweist.  
  
 Die `<cookieHandler>` Element wird dargestellt, durch die <xref:System.IdentityModel.Services.CookieHandlerElement> Klasse. Steht der cookiehandler, der in der Konfiguration angegeben wurde der <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> Eigenschaft der <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Objekt festgelegt werden, auf die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt ein `<cookieHandler>` Element. In diesem Beispiel da die `mode` Attribut nicht angegeben ist, der standardcookiehandler von SAM verwendet werden. Dies ist eine Instanz der <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse. Da die `<chunkedCookieHandler>` untergeordnete Element nicht angegeben ist, wird die standardmäßige Segmentgröße verwendet werden. HTTPS wird nicht benötigt werden, da die `requireSsl` -Attribut festgelegt ist `false`.  
  
> [!WARNING]
>  In diesem Beispiel ist HTTPS nicht erforderlich, um Sitzungscookies zu schreiben. Grund hierfür ist, die `requireSsl` -Attribut für die `<cookieHandler>` Element nastaven NA hodnotu `false`. Diese Einstellung ist für die meisten produktionsumgebungen nicht empfohlen, wie sie ein Sicherheitsrisiko darstellen kann.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Services.CookieHandler>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>
