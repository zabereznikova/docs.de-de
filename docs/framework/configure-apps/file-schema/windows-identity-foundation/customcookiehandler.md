---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: ebf1f7f3de1b44dba63977bf524dea9af2690fb1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942781"
---
# <a name="customcookiehandler"></a>\<customCookieHandler>
Legt den Typ des benutzerdefinierten Cookie-Handlers fest. Dieses Element kann nur vorhanden sein, wenn `mode` das-Attribut `<cookieHandler>` des-Elements "Custom" ist. Der benutzerdefinierte Typ muss von der <xref:System.IdentityModel.Services.CookieHandler> -Klasse abgeleitet werden.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
\<customCookieHandler>  
  
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
|Typ|Gibt einen benutzerdefinierten Typ an, der <xref:System.IdentityModel.Services.CookieHandler> von der-Klasse abgeleitet wird. Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , der <xref:System.IdentityModel.Services.SessionAuthenticationModule> von verwendet wird, um Cookies zu lesen und zu schreiben.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierten cookiehandler `mode` angeben, indem `<cookieHandler>` Sie das-Attribut des-Elements auf "Custom" festlegen, müssen Sie den Typ des Benutzer `<customCookieHandler>` definierten cookiehandlers angeben, indem Sie ein untergeordnetes-Element einschließen, das auf den Typ der Dieses Element kann nicht angegeben werden, `mode` wenn das-Attribut auf "Chunked" oder "Default" festgelegt ist. Benutzerdefinierte Cookie-Handler müssen von der <xref:System.IdentityModel.Services.CookieHandler> -Klasse abgeleitet werden.  
  
 Das `<customCookieHandler>` -Element wird durch die <xref:System.IdentityModel.Configuration.CustomTypeElement> -Klasse dargestellt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird Sam für die Verwendung eines benutzerdefinierten cookiehandlers vom Typ `MyNamespace.MyCustomCookieHandler`konfiguriert.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Services.CookieHandler>
