---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b3b4cf0d7c2748079af7a94534622b1dbadd3ab5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941895"
---
# <a name="chunkedcookiehandler"></a>\<chunkedCookieHandler>
Konfiguriert den <xref:System.IdentityModel.Services.ChunkedCookieHandler>. Dieses Element kann nur vorhanden sein, wenn `mode` das-Attribut `<cookieHandler>` des-Elements "Default" oder "Chunked" ist.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler>  
\<chunkedCookieHandler>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|chunkSize|Die maximale Größe der HTTP-Cookie-Daten für ein beliebiges HTTP-Cookie in Zeichen. Beim Anpassen der Segmentgröße müssen Sie vorsichtig sein. Webbrowser haben unterschiedliche Beschränkungen hinsichtlich der Größe von Cookies und der pro Domäne zulässigen Anzahl. Die ursprüngliche Netscape-Spezifikation hat z. b. diese Limits festgelegt: 300 Cookies Gesamt, 4096 Bytes pro Cookieheader (einschließlich Metadaten, nicht nur der Cookiewert) und 20 Cookies pro Domäne. Der Standardwert ist 2000. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , den der <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) zum Lesen und Schreiben von Cookies verwendet.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie <xref:System.IdentityModel.Services.ChunkedCookieHandler> einen angeben, indem Sie `mode` das-Attribut `<cookieHandler>` des-Elements auf "Default" oder "Chunked" festlegen, können Sie die Segmentgröße angeben, die der cookiehandler zum Lesen und Schreiben von `<chunkedCookieHandler>` Cookies verwendet, indem er ein untergeordnetes Element einschließt. Festlegen des `chunkSize` Attributs. Wenn das `<chunkedCookieHandler>` -Element nicht vorhanden ist, wird die Standard Segmentgröße von 2000 Bytes verwendet. Dieses Element kann nicht angegeben werden, `mode` wenn das-Attribut auf "Custom" festgelegt ist.  
  
 Das `<chunkedCookieHandler>` -Element wird durch die <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> -Klasse dargestellt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein segmentierter cookiehandler konfiguriert, der Cookies in Blöcken von 3000 Bytes schreibt.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
