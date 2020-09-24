---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: df512960b522f17dc9247bb5959e246c8c1f15b8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169803"
---
# \<tokenReplayDetection>

Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|enabled|Ein Wert, der angibt, ob die Erkennung der tokenwiedergabe aktiviert ist. "true", um die Erkennung von tokenwiedergabe zu aktivieren.|  
|expirationperiod|Eine <xref:System.TimeSpan> , die die maximale Zeitspanne angibt, nach der ein Element als abgelaufen betrachtet und aus dem Cache entfernt wird.  Weitere Informationen zum Angeben von <xref:System.TimeSpan> Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Gibt Identitäts Einstellungen auf Dienst Ebene an.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Bemerkungen  

 Ein- `<tokenReplayDetection>` Element kann auf der Dienst Ebene unterhalb des- `<identityConfiguration>` Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem-Element angegeben werden `<securityTokenHandlerConfiguration>` . Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen.  
  
 Der Typ des tokenreplay-Caches wird durch das- [\<tokenReplayCache>](tokenreplaycache.md) Element angegeben.
