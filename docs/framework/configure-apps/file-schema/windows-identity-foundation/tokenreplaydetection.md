---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: bd2272cb83dc0183d5008cfa178e11783f51ca2d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47205929"
---
# <a name="lttokenreplaydetectiongt"></a>&lt;tokenReplayDetection&gt;
Ermöglicht die Erkennung einer tokenmehrfachverwendung, und gibt an, die Ablaufzeit für Token.  
  
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
|enabled|Ein Wert, der angibt, ob die Erkennung einer tokenmehrfachverwendung aktiviert ist. "true", um Token zu aktivieren. replay-Erkennung.|  
|expirationPeriod|Ein <xref:System.TimeSpan> , der angibt, dass der Höchstmenge des Zeitraums, bevor ein Element als abgelaufen erachtet wird und aus dem Cache entfernt.  Weitere Informationen zur Vorgehensweise beim angeben <xref:System.TimeSpan> Werte finden Sie unter [Timespan-Werten](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die identitätseinstellungen der Servicelevel.|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `<tokenReplayDetection>` Element kann angegeben werden, auf der Dienstebene unter der `<identityConfiguration>` Element oder die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element. Einstellungen für eine Auflistung der Tokenhandler überschreiben jene, die für den Dienst angegeben.  
  
 Der Typ der tokenwiedergabecache wird angegeben, durch die [ \<TokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) Element.
