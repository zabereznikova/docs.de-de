---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251850"
---
# <a name="servicetokenresolver"></a>\<serviceTokenResolver>
Registriert den diensttokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird. Der diensttokenresolver wird verwendet, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlerconfiguration->** ](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicetokenresolver >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Gibt den Typ des diensttokenresolvers an. Entweder der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> -Klasse abgeleitet wird. Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [Custom Type References]. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Hinweise  
 Der diensttokenresolver kann verwendet werden, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen. Sie wird verwendet, um den Schlüssel abzurufen, der zum Entschlüsseln eingehender Token verwendet werden soll. Sie müssen das `type` -Attribut angeben. Der angegebene Typ kann entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> -Klasse abgeleitet wird.  
  
 Mit einigen tokenhandlern können Sie Einstellungen für den diensttokenresolver in der Konfiguration angeben. Einstellungen in einzelnen tokenhandlern überschreiben die in der Auflistung der Sicherheitstokenhandler angegebenen.  
  
> [!NOTE]
> Die Angabe `<serviceTokenResolver>` des-Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt. Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 