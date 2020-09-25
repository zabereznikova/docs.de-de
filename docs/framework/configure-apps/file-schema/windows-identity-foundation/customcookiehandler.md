---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: a8ee23ac6facaea18cd7f1820616cb9b16afa336
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189850"
---
# \<customCookieHandler>

Legt den Typ des benutzerdefinierten Cookie-Handlers fest. Dieses Element kann nur vorhanden sein, wenn das- `mode` Attribut des- `<cookieHandler>` Elements "Custom" ist. Der benutzerdefinierte Typ muss von der- <xref:System.IdentityModel.Services.CookieHandler> Klasse abgeleitet werden.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|type|Gibt einen benutzerdefinierten Typ an, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Services.CookieHandler> . Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , der <xref:System.IdentityModel.Services.SessionAuthenticationModule> von verwendet wird, um Cookies zu lesen und zu schreiben.|  
  
## <a name="remarks"></a>Bemerkungen  

 Wenn Sie einen benutzerdefinierten cookiehandler angeben, indem Sie das- `mode` Attribut des- `<cookieHandler>` Elements auf "Custom" festlegen, müssen Sie den Typ des benutzerdefinierten cookiehandlers angeben, indem Sie ein untergeordnetes- `<customCookieHandler>` Element einschließen, das auf den Typ der Dieses Element kann nicht angegeben werden, wenn das- `mode` Attribut auf "Chunked" oder "Default" festgelegt ist. Benutzerdefinierte Cookie-Handler müssen von der-Klasse abgeleitet werden <xref:System.IdentityModel.Services.CookieHandler> .  
  
 Das- `<customCookieHandler>` Element wird durch die- <xref:System.IdentityModel.Configuration.CustomTypeElement> Klasse dargestellt.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird Sam für die Verwendung eines benutzerdefinierten cookiehandlers vom Typ konfiguriert `MyNamespace.MyCustomCookieHandler` .  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Services.CookieHandler>
