---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944079"
---
# <a name="tokenreplaycache"></a>\<tokenReplayCache>
Registriert einen tokenwiedergabe-Cache bei einem Dienst oder einer Sammlung von Sicherheitstokenhandlern.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<Caches >  
\<tokenReplayCache>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Ein Typ, der von der <xref:System.IdentityModel.Tokens.TokenReplayCache> -Klasse abgeleitet wird. Weitere Informationen zum Angeben eines benutzerdefinierten `type`finden Sie unter [Custom Type References].
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<caches>](caches.md)|Registriert die von einem Dienst oder einer sicherheitstokenhandlerauflistung verwendeten Caches.|  
  
## <a name="remarks"></a>Hinweise  
 Der tokenwiedergabe-Cache wird verwendet, um wiedergegebene Token zu erkennen. Die Erkennung der tokenwiedergabe wird durch das [ \<tokenreplayerkennungs->](tokenreplaydetection.md) -Element aktiviert, das auch die maximale Ablaufzeit für Tokens angibt.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt die Konfiguration eines benutzerdefinierten Caches zum Erkennen von wiedergegebenen Token.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
