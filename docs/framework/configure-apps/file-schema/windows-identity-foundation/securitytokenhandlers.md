---
title: '&lt;securityTokenHandlers&gt;'
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 16827aa774a8a76f16106a8650423d0d7f084982
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritytokenhandlersgt"></a>&lt;securityTokenHandlers&gt;
Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<SecurityTokenHandlers >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Gibt den Namen einer Tokenhandler-Auflistung. Erkannt, durch das Framework nur die Werte sind "ActAs" und "OnBehalfOf". Wenn Tokenhandler Sammlungen mit einer dieser Namen angegeben sind, wird die Auflistung beim Verarbeiten von Actas- oder ein "onbehalfof" bzw. Token verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Fügt eine Sicherheitstokenhandler der Tokenhandler Auflistung hinzu.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|Löscht alle Sicherheitstokenhandler aus der Tokenhandler-Auflistung.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|Entfernt eine Sicherheitstokenhandler aus der Tokenhandler-Auflistung.|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Die Konfiguration für die Auflistung der Tokenhandler bereitstellt.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt an, Service Level identitätseinstellungen.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine oder mehrere benannte Sammlungen von sicherheitstokenhandlern in einer Dienstkonfiguration angeben. Sie können einen Namen für eine Sammlung angeben, mit der `name` Attribut. Die einzigen Namen, die das Framework verarbeitet werden "ActAs" und "OnBehalfOf". Wenn Handler in diesen Sammlungen vorhanden sind, werden von verwendet ein Sicherheitstokendienst (STS) anstelle der Standardhandler bei der Verarbeitung von `ActAs` und `OnBehalfOf` Token.  
  
 Standardmäßig wird die Auflistung mit folgende Handlertypen aufgefüllt: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, und <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>. Sie können die Auflistung ändern, indem Sie mit der `<add>`, `<remove>`, und `<clear>` Elemente. Sie müssen sicherstellen, dass nur ein einzelner Handler keinen bestimmten Typ in der Auflistung vorhanden ist. Z. B., wenn Sie einen Handler von Ableiten der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> entweder die Klasse den Handler oder <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> kann in einer einzelnen Auflistung, aber nicht beides konfiguriert werden.  
  
 Verwenden der `<securityTokenHandlerConfiguration>` Element Konfigurationseinstellungen für die Handler in der Auflistung an. Durch dieses Element angegebene Einstellungen außer Kraft angegeben wird, auf den Dienst über die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element. Einige Handler (einschließlich einiger der integrierten Handlertypen) unterstützen zusätzliche Konfiguration über ein untergeordnetes Element von der `<add>` Element. Für einen Ereignishandler angegebene Einstellungen außer Kraft setzen entsprechende Einstellungen für die Auflistung oder den Dienst angegeben.
