---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: d21a819f789b5be4bdf7ebf57b37a072e1d213ff
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206217"
---
# <a name="lttokenreplaycachegt"></a>&lt;tokenReplayCache&gt;
Registriert einen tokenwiederholungscache mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<Speichert >  
\<TokenReplayCache >  
  
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
|Typ|Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.TokenReplayCache> Klasse. Weitere Informationen zur Vorgehensweise beim Angeben eines benutzerdefiniertes `type`, finden Sie unter [benutzerdefinierte Typverweise].
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Speichert >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches, die von einem Dienst oder ein Sicherheitstoken-Handlerauflistung verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Tokenwiederholungs-Cache wird verwendet, um wiedergegebene Token erkennen. Erkennung von tokenwiederholungen ist aktiviert, die [ \<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) Element, das auch die maximale Ablaufzeit für Token angibt.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Cache für wiedergegebene Token erkennen.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [\<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
