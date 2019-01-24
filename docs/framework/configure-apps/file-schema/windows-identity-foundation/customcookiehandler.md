---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: a3d032279d0b568d7072dbbe020344365c341c1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724017"
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
Legt fest, den Handlertyp der benutzerdefinierten Cookies. Dieses Element kann nur vorhanden sein, wenn die `mode` Attribut der `<cookieHandler>` Element ist "Custom". Aus der benutzerdefinierte Typ abgeleitet werden die <xref:System.IdentityModel.Services.CookieHandler> Klasse.  
  
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
|Typ|Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Services.CookieHandler> Klasse. Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<cookieHandler>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die die <xref:System.IdentityModel.Services.SessionAuthenticationModule> zum Lesen und Schreiben von Cookies verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierten cookiehandler angeben, indem Sie festlegen der `mode` Attribut der `<cookieHandler>` Element in "Benutzerdefiniert", geben Sie den Typ des der benutzerdefinierten cookiehandler dazu eine `<customCookieHandler>` untergeordnetes Element, das den Cookie Handlertyp verweist. Dieses Element nicht angegeben, wenn die `mode` -Attribut auf "Chunked" oder "Default" festgelegt ist. Benutzerdefiniertes Cookie Handler müssen abgeleitet werden, aus der <xref:System.IdentityModel.Services.CookieHandler> Klasse.  
  
 Die `<customCookieHandler>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.CustomTypeElement> Klasse.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das SAM um einen benutzerdefinierten cookiehandler des Typs verwenden `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.IdentityModel.Services.CookieHandler>
