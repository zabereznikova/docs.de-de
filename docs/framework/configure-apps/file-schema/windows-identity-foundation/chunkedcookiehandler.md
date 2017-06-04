---
title: "&lt;chunkedCookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;chunkedCookieHandler&gt;
Konfiguriert die <xref:System.IdentityModel.Services.ChunkedCookieHandler>.  Dieses Element kann nur vorhanden sein, wenn die `mode` \-Attribut des der `<cookieHandler>` Element ist "Default" oder "Chunked".  
  
## Syntax  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|chunkSize|Die maximale Größe in Zeichen des HTTP\-Cookie\-Daten für jede eine HTTP\-Cookie.  Sie müssen vorsichtig, wenn die Chunk\-Größe anpassen können.  Web\-Browser haben unterschiedliche Grenzwerte für die Größe von Cookies und Anzahl pro Domäne zulässig.  Zum Beispiel Netscape\-Originalspezifikation diese Grenzwerte festgelegt: 300 Cookies insgesamt 4096 Bytes pro Cookie\-Header \(einschließlich Metadaten, nicht nur den Cookiewert\) und 20 Cookies pro Domäne.  Standardwert: 2000.  Erforderlich.|  
  
### Untergeordnete Elemente  
 None  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\) zum Lesen und Schreiben von Cookies verwendet.|  
  
## Hinweise  
 Wenn Sie angeben ein <xref:System.IdentityModel.Services.ChunkedCookieHandler> durch Festlegen der `mode` \-Attribut des der `<cookieHandler>` Element "Default" oder "Chunked" können Sie die Cookie\-Handler zum Lesen und Schreiben von Cookies verwendet durch einschließlich Chunk\-Größe ein `<chunkedCookieHandler>` untergeordnetes Element und die Einstellung seiner `chunkSize` Attribut.  Wenn die `<chunkedCookieHandler>` Element nicht vorhanden ist, wird die standardmäßige Chunk\-Größe von 2000 Bytes verwendet.  Dieses Element nicht angegeben, wann die `mode` \-Attribut auf "Custom" festgelegt ist.  
  
 Die `<chunkedCookieHandler>` Element dargestellt durch die <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> Klasse.  
  
## Beispiel  
 Im folgenden Beispiel wird einen aufgeteilte Cookie\-Handler, der Cookies in Blöcken von 3000 Bytes schreibt.  
  
```  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>