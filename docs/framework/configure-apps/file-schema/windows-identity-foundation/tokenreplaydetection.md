---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 4deeb1d84f2621adb7ff1b649a505138b6856ec1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790493"
---
# <a name="tokenreplaydetection"></a>\<tokenReplayDetection>
Ermöglicht die Erkennung einer tokenmehrfachverwendung, und gibt an, die Ablaufzeit für Token.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<tokenReplayDetection>  
  
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
|[\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die identitätseinstellungen der Servicelevel.|  
|[\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `<tokenReplayDetection>` Element kann angegeben werden, auf der Dienstebene unter der `<identityConfiguration>` Element oder die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element. Einstellungen für eine Auflistung der Tokenhandler überschreiben jene, die für den Dienst angegeben.  
  
 Der Typ der tokenwiedergabecache wird angegeben, durch die [ \<TokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) Element.
