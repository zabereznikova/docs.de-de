---
title: Netzwerkisolation für Windows Store-Apps
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 0f9288b53b969838cac64c24d3c9861a0f841aca
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558458"
---
# <a name="network-isolation-for-windows-store-apps"></a>Netzwerkisolation für Windows Store-Apps

Klassen in den Namespaces <xref:System.Net>, <xref:System.Net.Http> und <xref:System.Net.Http.Headers> können verwendet werden, um Windows Store- oder Desktop-Apps zu entwickeln. Bei Verwendung in einer Windows Store-App sind Klassen in diesen Namespaces von Netzwerkisolation betroffen, als Teil des Anwendungssicherheitsmodells, das von Windows 8 verwendet wird. Die entsprechenden Netzwerkfunktionen müssen im App-Manifest für eine Windows Store-App aktiviert sein, damit das System den Netzwerkzugriff erlaubt.  
  
## <a name="checklist-for-network-isolation"></a>Prüfliste für die Netzwerkisolation  

Verwenden Sie diese Prüfliste, um sicherzustellen, dass die Netzwerkisolation für Ihre Windows Store-App konfiguriert ist.  
  
1. Bestimmen Sie die Richtung der Netzwerkzugriffsanforderungen, die von der App benötigt werden. Dies können entweder ausgehende, vom Client initiierte Anforderungen sein oder eingehende, unaufgeforderte Anforderungen, oder es könnte möglicherweise eine Kombination aus beiden Netzwerkanforderungstypen sein.  
  
2. Bestimmen Sie den Typ der Netzwerkressourcen, mit denen die App kommunizieren wird. Eine App muss möglicherweise mit vertrauenswürdigen Ressourcen in einem Heimnetzwerk oder einem Arbeitsplatznetzwerk kommunizieren. Eine App muss möglicherweise mit Ressourcen im Internet kommunizieren. Eine App benötigt möglicherweise den Zugriff auf beide Netzwerkressourcentypen.  
  
3. Konfigurieren Sie die minimal erforderlichen Netzwerkisolationsfunktionen im App-Manifest.  
  
4. Stellen Sie Ihre App bereit, und führen Sie diese zu Testzwecken aus, indem Sie die Netzwerkisolationstools für die Problembehandlung verwenden.  
  
Weitere ausführliche Informationen zum Konfigurieren der Netzwerkfunktionen und der Isolationstools zur Problembehandlung im Rahmen der Netzwerkisolation finden Sie unter [So wird’s gemacht: Konfigurieren von Netzwerkisolationsfunktionen](/previous-versions/windows/apps/hh770532(v=win.10)) in der Windows 8.x Store-Entwicklerdokumentation.
  
## <a name="see-also"></a>Weitere Informationen

- [Connecting to a web service (Herstellen einer Verbindung mit einem Webdienst)](/previous-versions/windows/apps/hh761504(v=win.10))
- [Guidelines and checklist for network isolation (Richtlinien und Checkliste für die Netzwerkisolation)](/previous-versions/windows/apps/hh770532(v=win.10))
- [Quickstart: Connecting using HttpClient (Schnellstart: Verbindungsherstellung mithilfe von „HttpClient“)](/previous-versions/windows/apps/hh781239(v=win.10))
- [How to use HttpClient handlers (Verwenden des Handlers für „HttpClient“)](/previous-versions/windows/apps/hh781241(v=win.10))
- [How to secure HttpClient connections (Sichern von „HttpClient“-Verbindungen)](/previous-versions/windows/apps/hh781240(v=win.10))
- [HttpClient Sample (HttpClient-Beispiel)](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
