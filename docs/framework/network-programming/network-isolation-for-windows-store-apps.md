---
title: Netzwerkisolation für Windows Store-Apps
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4d26b6df5d26a96bb8fa41dd3a8151fcb4a08b75
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43773656"
---
# <a name="network-isolation-for-windows-store-apps"></a>Netzwerkisolation für Windows Store-Apps
Klassen in den Namespaces <xref:System.Net>, <xref:System.Net.Http> und <xref:System.Net.Http.Headers> können verwendet werden, um Windows Store-Apps oder Desktop-Apps zu entwickeln. Bei Verwendung in einer Windows Store-App sind Klassen in diesen Namespaces von Netzwerkisolation betroffen, als Teil des Anwendungssicherheitsmodells, das von [!INCLUDE[win8](../../../includes/win8-md.md)] verwendet wird. Die entsprechenden Netzwerkfunktionen müssen im App-Manifest für eine Windows Store-App aktiviert sein, damit das System den Netzwerkzugriff erlaubt.  
  
## <a name="checklist-for-network-isolation"></a>Prüfliste für die Netzwerkisolation  
 Verwenden Sie diese Prüfliste, um sicherzustellen, dass die Netzwerkisolation für Ihre Windows Store-App konfiguriert ist.  
  
1.  Bestimmen Sie die Richtung der Netzwerkzugriffsanforderungen, die von der App benötigt werden. Dies können entweder ausgehende, vom Client initiierte Anforderungen sein oder eingehende, unaufgeforderte Anforderungen, oder es könnte möglicherweise eine Kombination aus beiden Netzwerkanforderungstypen sein.  
  
2.  Bestimmen Sie den Typ der Netzwerkressourcen, mit denen diese App kommunizieren wird. Eine App muss möglicherweise mit vertrauenswürdigen Ressourcen in einem Heimnetzwerk oder einem Arbeitsplatznetzwerk kommunizieren. Eine App muss möglicherweise mit Ressourcen im Internet kommunizieren. Eine App benötigt möglicherweise den Zugriff auf beide Netzwerkressourcentypen.  
  
3.  Konfigurieren Sie die minimal erforderlichen Netzwerkisolationsfunktionen im App-Manifest.  
  
4.  Stellen Sie Ihre App bereit, und führen Sie diese zu Testzwecken aus, indem Sie die Netzwerkisolationstools für die Problembehandlung verwenden.  
  
 Weitere ausführliche Informationen zum Konfigurieren der Netzwerkfunktionen und der Isolationstools zur Problembehandlung im Rahmen der Netzwerkisolation finden Sie unter [How to configure network isolation capabilities (Vorgehensweise beim Konfigurieren von Netzwerkisolierungseigenschaften)](https://go.microsoft.com/fwlink/?LinkID=228265) in der [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-Entwicklerdokumentation.  
  
## <a name="see-also"></a>Siehe auch  
 [Connecting to a web service (Herstellen einer Verbindung mit einem Webdienst)](https://go.microsoft.com/fwlink/?LinkID=245696)  
 [Guidelines and checklist for network isolation (Richtlinien und Checkliste für die Netzwerkisolation)](https://go.microsoft.com/fwlink/?LinkID=228265)  
 [Quickstart: Connecting using HttpClient (Schnellstart: Verbindungsherstellung mithilfe von „HttpClient“)](https://go.microsoft.com/fwlink/?LinkId=245697)  
 [How to use HttpClient handlers (Verwenden des Handlers für „HttpClient“)](https://go.microsoft.com/fwlink/?LinkId=245699)  
 [How to secure HttpClient connections (Sichern von „HttpClient“-Verbindungen)](https://go.microsoft.com/fwlink/?LinkId=245698)  
 [HttpClient Sample (HttpClient-Beispiel)](https://go.microsoft.com/fwlink/?LinkId=242550)
