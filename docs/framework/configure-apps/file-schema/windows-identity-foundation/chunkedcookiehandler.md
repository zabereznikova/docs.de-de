---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252108"
---
# \<chunkedCookieHandler>
Konfiguriert den <xref:System.IdentityModel.Services.ChunkedCookieHandler> . Dieses Element kann nur vorhanden sein, wenn das- `mode` Attribut des- `<cookieHandler>` Elements "Default" oder "Chunked" ist.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|chunkSize|Die maximale Größe der HTTP-Cookie-Daten für ein beliebiges HTTP-Cookie in Zeichen. Beim Anpassen der Segmentgröße müssen Sie vorsichtig sein. Webbrowser haben unterschiedliche Beschränkungen hinsichtlich der Größe von Cookies und der pro Domäne zulässigen Anzahl. Die ursprüngliche Netscape-Spezifikation hat z. b. die folgenden Grenzwerte festgelegt: 300 Cookies Gesamt, 4096 Bytes pro Cookieheader (einschließlich Metadaten, nicht nur den Cookiewert) und 20 Cookies pro Domäne. Der Standardwert ist „2000“. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , den der <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) zum Lesen und Schreiben von Cookies verwendet.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn Sie einen angeben <xref:System.IdentityModel.Services.ChunkedCookieHandler> , indem Sie das- `mode` Attribut des- `<cookieHandler>` Elements auf "Default" oder "Chunked" festlegen, können Sie die Segmentgröße angeben, die der cookiehandler zum Lesen und Schreiben von Cookies verwendet, indem Sie ein untergeordnetes `<chunkedCookieHandler>` -Element einschließen und sein- `chunkSize` Attribut festlegen. Wenn das- `<chunkedCookieHandler>` Element nicht vorhanden ist, wird die Standard Segmentgröße von 2000 Bytes verwendet. Dieses Element kann nicht angegeben werden, wenn das- `mode` Attribut auf "Custom" festgelegt ist.  
  
 Das- `<chunkedCookieHandler>` Element wird durch die- <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> Klasse dargestellt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein segmentierter cookiehandler konfiguriert, der Cookies in Blöcken von 3000 Bytes schreibt.  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
