---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152579"
---
# <a name="servicetokenresolver"></a>\<dienstTokenResolver>
Registriert den Diensttoken-Resolver, der von Handlern in der Tokenhandlerauflistung verwendet wird. Der Diensttokenlöser wird verwendet, um das Verschlüsselungstoken für eingehende Token und Nachrichten aufzulösen.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dienstTokenResolver>**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|type|Gibt den Typ des Diensttokenresolvers an. Entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> der Typ oder ein Typ, <xref:System.IdentityModel.Selectors.SecurityTokenResolver> der von der Klasse stammt. Weitere Informationen zum Angeben `type` des Attributs finden Sie unter [Benutzerdefinierte Typreferenzen]. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Bemerkungen  
 Der Diensttokenlöser kann verwendet werden, um das Verschlüsselungstoken für eingehende Token und Nachrichten aufzulösen. Es wird verwendet, um den Schlüssel abzurufen, der zum Entschlüsseln eingehender Token verwendet werden soll. Sie müssen `type` das Attribut angeben. Der angegebene Typ <xref:System.IdentityModel.Selectors.SecurityTokenResolver> kann entweder oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse abstammt.  
  
 Einige Tokenhandler ermöglichen es Ihnen, Diensttoken-Resolvereinstellungen in der Konfiguration anzugeben. Einstellungen für einzelne Tokenhandler überschreiben die in der Sicherheitstokenhandlerauflistung angegebenen.  
  
> [!NOTE]
> Die Angabe `<serviceTokenResolver>` des Elements als untergeordnetes Element der [ \<identityConfiguration>-Element](identityconfiguration.md) sprägiert, wird aber aus Gründen der Abwärtskompatibilität weiterhin unterstützt. Einstellungen für `<securityTokenHandlerConfiguration>` das Element überschreiben die Einstellungen für das `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
