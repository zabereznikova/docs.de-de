---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: d892fbd802ed366ca7af9b85fbf5c23d4d27e0f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157004"
---
# \<securityTokenHandlers>

Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**  
  
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
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|name|Gibt den Namen einer tokenhandlerauflistung an. Die einzigen Werte, die vom Framework erkannt werden, sind "ACTAS" und "onbehalfof". Wenn tokenhandlerauflistungen mit einem dieser Namen angegeben werden, wird die Auflistung verwendet, wenn ACTAS bzw. onbehalfof-Token verarbeitet werden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](add.md)|Fügt der tokenhandlerauflistung einen Sicherheitstokenhandler hinzu.|  
|[\<clear>](clear.md)|Löscht alle Sicherheitstokenhandler aus der Auflistung von tokenhandlern.|  
|[\<remove>](remove.md)|Entfernt einen Sicherheitstokenhandler aus der tokenhandlerauflistung.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für die Auflistung von tokenhandlern bereit.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Gibt Identitäts Einstellungen auf Dienst Ebene an.|  
  
## <a name="remarks"></a>Bemerkungen  

 Sie können eine oder mehrere benannte Sammlungen von Sicherheitstokenhandlern in einer Dienst Konfiguration angeben. Mithilfe des-Attributs können Sie einen Namen für eine Sammlung angeben `name` . Die einzigen Namen, die das Framework behandelt, sind "ACTAS" und "onbehalfof". Wenn Handler in diesen Auflistungen vorhanden sind, werden Sie bei der Verarbeitung von `ActAs` -und-Token von einem Sicherheitstokendienst (STS) anstelle von Standard Handlern verwendet `OnBehalfOf` .  
  
 Standardmäßig wird die Auflistung mit den folgenden Handlertypen aufgefüllt: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> und <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> . Sie können die Sammlung mithilfe der `<add>` `<remove>` Elemente, und ändern `<clear>` . Sie müssen sicherstellen, dass nur ein einzelner Handler eines bestimmten Typs in der Auflistung vorhanden ist. Wenn Sie z. b. einen Handler von der- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse ableiten, kann entweder der Handler oder der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> in einer einzelnen Auflistung konfiguriert werden, aber nicht beides.  
  
 Verwenden Sie das- `<securityTokenHandlerConfiguration>` Element, um Konfigurationseinstellungen für die Handler in der Auflistung anzugeben. Durch dieses Element angegebene Einstellungen überschreiben die für den Dienst durch das-Element angegebenen Einstellungen [\<identityConfiguration>](identityconfiguration.md) . Einige Handler (einschließlich mehrerer integrierter Handlertypen) können zusätzliche Konfigurationen durch ein untergeordnetes Element des-Elements unterstützen `<add>` . Die Einstellungen, die für einen Handler angegeben werden, überschreiben die in der Auflistung oder dem Dienst angegebenen entsprechenden Einstellungen.
