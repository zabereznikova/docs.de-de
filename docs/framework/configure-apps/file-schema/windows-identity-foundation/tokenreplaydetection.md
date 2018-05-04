---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7f0cef2590bb301e6897aa4922454942ecdd0957
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="lttokenreplaydetectiongt"></a>&lt;tokenReplayDetection&gt;
Tokenwiedergabeerkennung aktiviert, und gibt die Ablaufzeit für Token.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<TokenReplayDetection >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>Typ  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Ein Wert, der angibt, ob tokenwiederholungen aktiviert ist. "true", um Token zu aktivieren replay-Erkennung.|  
|expirationPeriod|Ein <xref:System.TimeSpan> , die angibt, dass der maximale Zeitspanne, bevor ein Element betrachtet wird, ist abgelaufen und aus dem Cache entfernt.  Weitere Informationen zum Angeben der <xref:System.TimeSpan> -Werte finden Sie in [Timespan Werte](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt an, Service Level identitätseinstellungen.|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `<tokenReplayDetection>` Element angegeben werden kann, auf Dienstebene unter der `<identityConfiguration>` Element oder auf die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element. Einstellungen für eine Sammlung Tokenhandler außer Kraft für den Dienst angegeben.  
  
 Der Typ des Caches aufbewahrungsdateu wird angegeben, durch die [ \<TokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) Element.
