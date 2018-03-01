---
title: HttpListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: b4b8c1e916aa9382d156a197fa15c2e72e900a1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="httplistener"></a>HttpListener
Die <xref:System.Net.HttpListener>-Klasse stellt einen programmgesteuerten HTTP-Protokolllistener bereit. Der Listener ist für die Lebensdauer des <xref:System.Net.HttpListener>-Objekts aktiv und wird in der Anwendung ausgeführt.  
  
## <a name="httpsys"></a>HTTP.SYS  
 Die <xref:System.Net.HttpListener>-Klasse basiert auf HTTP.sys; hierbei handelt es sich um den Kernelmoduslistener, der den gesamten HTTP-Verkehr für Windows verarbeitet. HTTP.sys bietet Verbindungsverwaltung, Bandbreiteneinschränkung und Webserverprotokollierung. Verwenden Sie das Tool "`HttpCfg.exe`", um SSL-Zertifikate hinzuzufügen. Weitere Informationen finden Sie in der Dokumentation zum Tool [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) in der [Server](http://go.microsoft.com/fwlink/?LinkID=178285)-Dokumentation.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [HTTP-Server](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [Security Enhancements in Internetinformation](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [Beispiel zur HttpListener ASPX-Hostanwendung](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [Beispiel zur HttpListener-Technologie](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)
