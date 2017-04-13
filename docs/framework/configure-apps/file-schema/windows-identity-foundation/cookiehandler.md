---
title: "&lt;cookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;cookieHandler&gt;
Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\) zum Lesen und Schreiben von Cookies verwendet.  
  
## Syntax  
  
```  
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
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|name|Gibt den Basisnamen für die keine Cookies geschrieben.  Der Standardwert ist "FedAuth".|  
|path|Gibt den Pfadwert für Cookies geschrieben.  Der Standardwert ist "HttpRuntime.AppDomainAppVirtualPath".|  
|mode|Eines der <xref:System.IdentityModel.Services.CookieHandlerMode> \-Werte, die Art von Cookie\-Handler, mit dem von der SAM angibt.  Die folgenden Werte können verwendet werden:<br /><br /> -   "Default" — "Chunked" identisch.<br />-   "Chunked" – verwendet eine Instanz der <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse.  Dieser Cookie\-Handler wird sichergestellt, dass es sich bei einzelnen Cookies keine maximale Größe überschreiten.  Dies wird erreicht, indem Sie "chunking" möglicherweise eine logische Cookie in eine Anzahl von Cookies on\-the\-Wire.<br />-   "Custom" – verwendet eine Instanz einer benutzerdefinierten Klasse, abgeleitet von <xref:System.IdentityModel.Services.CookieHandler>.  Die abgeleitete Klasse verweist die `<customCookieHandler>` untergeordnetes Element.<br /><br /> Der Standardwert ist "Default".|  
|persistentSessionLifetime|Gibt die Lebensdauer der permanenten Sitzungen.  Falls der Wert NULL ist, werden Sitzungen mit transiente immer verwendet.  Der Standardwert ist "Commitdatensatz", die eine vorübergehende Sitzung angibt.  Der Maximalwert ist "365:0:0", die eine Sitzung von 365 Tagen angibt.  Der Wert sollte angegeben werden, entsprechend der folgenden Einschränkung: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, wobei der am weitesten links stehende Wert gibt die Tage, der mittlere Wert \(falls vorhanden\) gibt die Stunden und Minuten gibt an, der am weitesten rechts stehenden Wert \(falls vorhanden\).|  
|requireSsl|Gibt an, ob das "Secure"\-Flag für alle Cookies geschrieben ausgegeben wird.  Wenn dieser Wert festgelegt ist, werden die\-in\-Sitzungs\-Cookies nur über HTTPS verfügbar.  Der Standardwert ist "true".|  
|hideFromScript|Steuert, ob das Flag "HttpOnly", für die keine Cookies geschrieben ausgegeben wird.  Bestimmten Webbrowsern Ehren dieses Flag provozieren clientseitiges Skript den Zugriff auf den Cookiewert.  Der Standardwert ist "true".|  
|domain|Der Domain\-Wert für Cookies geschrieben werden soll.  Der Standardwert ist "".|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<chunkedCookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|Konfiguriert die <xref:System.IdentityModel.Services.ChunkedCookieHandler>.  Dieses Element kann nur vorhanden sein, wenn die `mode` \-Attribut des der `<cookieHandler>` Element ist "Default" oder "Chunked".|  
|[\<customCookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|Legt den Typ des benutzerdefinierten Cookies\-Handler.  Dieses Element muss vorhanden sein, wenn die `mode` \-Attribut des der `<cookieHandler>` Element ist "Custom".  Es kann nicht vorhanden sein, damit alle anderen Werte von den `mode` Attribut.  Der benutzerdefinierte Typ muss abgeleitet werden die <xref:System.IdentityModel.Services.CookieHandler> Klasse.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Enthält die Einstellungen, konfigurieren die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).|  
  
## Hinweise  
 Die <xref:System.IdentityModel.Services.CookieHandler> ist verantwortlich für das Lesen und Schreiben von raw Cookies mit dem HTTP\-Protokoll auf.  Können Sie entweder eine <xref:System.IdentityModel.Services.ChunkedCookieHandler> oder ein benutzerdefinierten Cookie\-Handler aus der <xref:System.IdentityModel.Services.CookieHandler> Klasse.  
  
 Legen Sie das Mode\-Attribut auf "Chunked" oder "Default" um chunked Cookie\-Handler zu konfigurieren.  Die standardmäßige Chunk\-Größe beträgt 2000 Bytes, aber Sie können optional eine anderen Chunk\-Größe angeben, indem einschließlich einer `<chunkedCookieHandler>` untergeordnetes Element.  
  
 Um einen benutzerdefiniertes Cookie\-Handler zu konfigurieren, legen Sie das Mode\-Attribut auf "Custom".  Müssen Sie eine `<customCookieHandler>` untergeordnetes Element, das den Typ des benutzerdefinierten Handler verweist.  
  
 Die `<cookieHandler>` Element dargestellt durch die <xref:System.IdentityModel.Services.CookieHandlerElement> Klasse.  Der Cookie\-Handler, der in der Konfiguration angegeben wurde steht die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> \-Eigenschaft des der <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> \-Objekt auf die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> Eigenschaft.  
  
## Beispiel  
 Das folgende XML zeigt eine `<cookieHandler>` Element.  In diesem Beispiel weil die `mode` \-Attribut nicht angegeben ist, von der SAM der Standardhandler für das Cookie verwendet werden.  Dies ist eine Instanz der <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse.  Da die `<chunkedCookieHandler>` untergeordnete Element nicht angegeben ist, wird die standardmäßige Chunk\-Größe verwendet werden.  HTTPS wird nicht benötigt werden, da die `requireSsl` \-Attribut festgelegt ist `false`.  
  
> [!WARNING]
>  In diesem Beispiel wird HTTPS nicht benötigt, um die Session\-Cookies zu schreiben.  Dies liegt daran, die `requireSsl` \-Attribut auf die `<cookieHandler>` auf Element festgelegt ist `false`.  Diese Einstellung ist für die meisten Produktionsumgebungen nicht empfohlen, da es ein Sicherheitsrisiko darstellen kann.  
  
```  
<cookieHandler requireSsl="false" />  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Services.CookieHandler>   
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>   
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>