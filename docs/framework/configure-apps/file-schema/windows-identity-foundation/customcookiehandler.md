---
title: '&lt;customCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 61b128d5856fd8e35516949b637177dc38a17164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
Legt die benutzerdefinierten cookiehandlertyp fest. Dieses Element kann nur vorhanden sein, wenn die `mode` Attribut des der `<cookieHandler>` Element ist "Custom". Der benutzerdefinierte Typ muss von abgeleitet werden die <xref:System.IdentityModel.Services.CookieHandler> Klasse.  
  
 \<system.identityModel.services >  
\<FederationConfiguration >  
\<"cookiehandler" >  
\<CustomCookieHandler >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Services.CookieHandler> Klasse. Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<"cookiehandler" >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die die <xref:System.IdentityModel.Services.SessionAuthenticationModule> zum Lesen und Schreiben von Cookies verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Beim Angeben von eines benutzerdefinierten Cookie-Handlers Festlegen der `mode` Attribut des der `<cookieHandler>` Element auf "Benutzerdefiniert", müssen Sie den Typ des benutzerdefinierten Cookie-Handlers angeben, indem z. B. eine `<customCookieHandler>` untergeordnetes Element, das die cookiehandlertyp verweist. Dieses Element nicht angegeben, wann die `mode` -Attribut auf "Chunked" oder "Default" festgelegt ist. Benutzerdefinierte Cookie Handler leiten sich aus der <xref:System.IdentityModel.Services.CookieHandler> Klasse.  
  
 Die `<customCookieHandler>` Element dargestellt ist, durch die <xref:System.IdentityModel.Configuration.CustomTypeElement> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel konfiguriert die SAM um einen benutzerdefinierten Cookie-Handler des Typs verwenden `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Services.CookieHandler>
