---
title: '&lt;securityTokenHandlers&gt;'
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: e63f02add81495e474b59b6c5cc090bd69add3d2
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206171"
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
|Name|Gibt den Namen einer Auflistung der Tokenhandler. Erkannt, die durch das Framework nur die Werte sind "ActAs" und "OnBehalfOf". Wenn Sicherheitstokenhandler-Sammlungen mit einer dieser Namen angegeben sind, wird die Auflistung beim Verarbeiten der Actas- oder ein OnBehalfOf bzw. Token verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Der Tokenhandler-Auflistung hinzugefügt einen Sicherheitstokenhandler.|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|Löscht alle Sicherheitstokenhandler aus der Auflistung der Tokenhandler.|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|Entfernt einen Sicherheitstoken-Handler aus der Auflistung der Tokenhandler.|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Ermöglicht die Konfiguration für die Sammlung von tokenhandlern.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die identitätseinstellungen der Servicelevel.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine oder mehrere benannte Auflistungen der Sicherheitstokenhandler in einer Dienstkonfiguration angeben. Sie können einen Namen für eine Sammlung angeben, mit der `name` Attribut. Die einzigen Namen, die das Framework verarbeitet werden "ActAs" und "OnBehalfOf". Wenn der Handler in diesen Sammlungen vorhanden sind, sie werden verwendet von einem Sicherheitstokendienst (STS) die Standardhandler bei der Verarbeitung von `ActAs` und `OnBehalfOf` Token.  
  
 Standardmäßig wird die Auflistung mit folgende Handlertypen aufgefüllt: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, und <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>. Sie können die Auflistung ändern, indem Sie mit der `<add>`, `<remove>`, und `<clear>` Elemente. Sie müssen sicherstellen, dass nur auf ein einzelnen Handler keinen bestimmten Typ in der Auflistung vorhanden ist. Angenommen, Sie ableiten, dass ein Ereignishandler aus der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse entweder Ihren Handler oder <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> kann in einer einzelnen Sammlung, aber nicht beide konfiguriert werden.  
  
 Verwenden der `<securityTokenHandlerConfiguration>` Element, um Konfigurationseinstellungen für die Handler in der Auflistung anzugeben. Einstellungen, die durch dieses Element angegeben, überschreiben die Optionen angegeben werden, auf den Dienst über die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element. Einige Handler (einschließlich mehrere Handler für integrierte Typen) können zusätzliche Konfiguration über ein untergeordnetes Element des unterstützen die `<add>` Element. Auf einen Handler angegebene Einstellungen überschreiben entsprechende Einstellungen, die in der Auflistung oder den Dienst angegeben.
