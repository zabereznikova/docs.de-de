---
title: "&lt;customCookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# &lt;customCookieHandler&gt;
Legt den Typ des benutzerdefinierten Cookies\-Handler.  Dieses Element kann nur vorhanden sein, wenn die `mode` \-Attribut des der `<cookieHandler>` Element ist "Custom".  Der benutzerdefinierte Typ muss abgeleitet werden die <xref:System.IdentityModel.Services.CookieHandler> Klasse.  
  
## Syntax  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode=”Custom”>  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|type|Gibt einen benutzerdefinierten Typ, der von abgeleitet wird die <xref:System.IdentityModel.Services.CookieHandler> Klasse.  Weitere Informationen zum Angeben der `type` \-Attribut, finden Sie unter [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Untergeordnete Elemente  
 None  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die <xref:System.IdentityModel.Services.SessionAuthenticationModule> zum Lesen und Schreiben von Cookies verwendet.|  
  
## Hinweise  
 Wenn Sie einen benutzerdefinierten Cookies Handler angeben, indem Sie die `mode` \-Attribut des der `<cookieHandler>` Element zu "Custom", müssen Sie den Typ des benutzerdefinierten Cookies\-Handler durch einschließlich ein `<customCookieHandler>` untergeordnetes Element, das den Typ des Cookie\-Ereignishandler verweist.  Dieses Element nicht angegeben, wann die `mode` \-Attribut auf "Chunked" oder "Standard" festgelegt ist.  Benutzerdefinierte Cookie\-Handler die Ableitung müssen von der <xref:System.IdentityModel.Services.CookieHandler> Klasse.  
  
 Die `<customCookieHandler>` Element dargestellt durch die <xref:System.IdentityModel.Configuration.CustomTypeElement> Klasse.  
  
## Beispiel  
 Das folgende Beispiel konfiguriert das SAM mit einen benutzerdefinierten Cookies Handler vom Typ `MyNamespace.MyCustomCookieHandler`.  
  
```  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Services.CookieHandler>