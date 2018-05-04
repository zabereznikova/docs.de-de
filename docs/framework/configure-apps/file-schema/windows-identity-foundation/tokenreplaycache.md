---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 79022319944c4042c6f62a7521784b826b90d4ce
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="lttokenreplaycachegt"></a>&lt;tokenReplayCache&gt;
Registriert einen token-Replay-Cache mit einem Dienst oder einer Sicherheit Tokenhandler-Auflistung.  
  
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
|Typ|Ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.TokenReplayCache> Klasse. Weitere Informationen über das Angeben eines benutzerdefiniertes `type`, finden Sie unter [benutzerdefinierte Typverweise].
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Speichert >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches, die von einem Dienst oder eine Auflistung der Security-Tokenhandler verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Die token-Replay-Cache wird verwendet, wiedergegebene Token erkannt. Tokenwiedergabeerkennung wird aktiviert, indem die [ \<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) Element, das auch die maximale Ablaufzeit für Token angibt.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Caches zum Erkennen von wiedergegebenen Token.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [\<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
