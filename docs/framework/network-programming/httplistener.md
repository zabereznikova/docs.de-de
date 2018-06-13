---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: db2c42dab15b4282c5474c50f970ffe47a101215
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393451"
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
 [Security Enhancements in Internet Information (Sicherheitsverbesserungen bei Internetinformationen)](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [Beispiel zur HttpListener ASPX-Hostanwendung](http://go.microsoft.com/fwlink/?LinkID=179560)  
 [Beispiel zur HttpListener-Technologie](http://go.microsoft.com/fwlink/?LinkID=179558)  
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)
