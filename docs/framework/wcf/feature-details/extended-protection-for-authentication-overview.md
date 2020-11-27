---
title: Übersicht über den erweiterten Schutz für die Authentifizierung
ms.date: 03/30/2017
ms.assetid: 3d2ceffe-a7bf-4bd9-a5a2-9406423bd7f8
ms.openlocfilehash: 0537e6147a7b43dabcb4c3612fc58da11dfd4d6d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255545"
---
# <a name="extended-protection-for-authentication-overview"></a>Übersicht über den erweiterten Schutz für die Authentifizierung

Der erweiterte Schutz für die Authentifizierung schützt gegen sog. Man-In-The-Middle (MITM)-Angriffe, bei denen die Anmeldeinformationen eines Clients von einem Angreifer abgefangen und an einen Server weitergeleitet werden.  
  
 Betrachten wir ein Szenario mit drei Teilnehmern: einem Client, einem Server und einem Angreifer. Der Server weist die URL `https://server` auf, wohingegen der Angreifer die URL `https://attacker` verwendet. Der Angreifer gibt sich gegenüber dem Client als Server aus. Anschließend sendet der Angreifer eine Anfrage an den Server. Versucht der Angreifer auf eine sichere Ressource zuzugreifen, antwortet der Server dem Angreifer mit einem WWW-Authentifizierungsheader. Der Angreifer verfügt jedoch nicht über die Authentifizierungsinformationen. Daher sendet er den WWW-Authentifizierungsheader an den Client. Der Client sendet den Authentifizierungsheader an den Angreifer, und der Angreifer sendet den Header an den Server, wodurch er mit den Anmeldeinformationen des Clients Zugriff auf sichere Ressourcen erhält.  
  
 Aktuell wird zunächst ein Transport Level Security (TLS)-Kanal eingerichtet und eine Authentifizierung über diesen Kanal durchgeführt, wenn sich eine Clientanwendung mit Kerberos, Hashwert oder NTLM mit HTTPS im Server authentifiziert. Zwischen dem von Secure Sockets Layer (SSL) und dem bei der Authentifizierung erstellten Sitzungsschlüssel besteht jedoch keine Bindung. Wenn also im genannten Szenario über TLS (z. B. ein HTTPS-Kanal) kommuniziert wird, werden zwei SSL-Kanäle erstellt: einer zwischen dem Client und dem Angreifer und ein weiterer zwischen dem Angreifer und dem Server. Die Anmeldeinformationen des Clients werden zunächst über den SSL-Kanal zwischen dem Client und dem Angreifer und anschließend über den Kanal zwischen dem Angreifer und dem Server vom Client an den Server gesendet. Nachdem die Anmeldeinformationen des Clients vom Server empfangen wurden, werden die Anmeldeinformationen vom Server geprüft. Dabei bemerkt der Server nicht, dass der Kanal, über den die Anmeldeinformationen gesendet wurden, zum Angreifer und nicht zum Client führt.  
  
 Die Lösung besteht in der Verwendung eines TLS-gesicherten Außenkanals und eines clientauthentifizierten Innenkanals und der Übergabe eines Kanalbindungstokens (CBT) an den Server. Die CBT ist eine Eigenschaft des CBT-gesicherten Außenkanals und wird zur Bindung des Außenkanals an eine Konversation über den clientauthentifizierten Innenkanal verwendet.  
  
 Im genannten Szenario wird der CBT des Client-Angreifer-TLS-Kanals mit den an den Server gesendeten Autorisierungsinformationen verbunden. Ein CBT verarbeitender Server vergleicht das CBT in den Authentifizierungsinformationen des Clients, die dem Client-Angreifer-Kanal entsprechen, mit dem CBT des Angreifer-Server-Kanals. Ein CBT ist einem Kanalziel eindeutig zuordenbar. Das Client-Angreifer-CBT entspricht nicht dem Angreifer-Server-CBT. Der Server entdeckt so den MITM-Angriff und weist die Authentifizierungsanfrage ab.  
  
 Clientseitig sind keine Konfigurationseinstellungen erforderlich. Nach einmaliger Aktualisierung übergibt der Client das CBT dauerhaft an den Server. Wurde der Server ebenfalls aktualisiert, kann er für die Verwendung des CBT oder seine Ignorierung konfiguriert werden. Wurde keine Aktualisierung durchgeführt, wird das CBT ignoriert.  
  
 Der Server kann folgende Sicherheitsstufen aufweisen:  
  
- Keine Keine Kanalbindungsvalidierung wird durchgeführt. Dies ist das Standardverhalten aller nicht aktualisierten Server.  
  
- Teilweise. Alle aktualisierten Clients müssen Kanalbindungsinformationen für den Server bereitstellen. Dies gilt nicht für nicht aktualisierte Clients. Dies ist eine Zwischenoption, durch die Anwendungskompatibilität gewahrt wird.  
  
- Vollständig. Alle Clients müssen Kanalbindungsinformationen bereitstellen. Authentifizierungsanfragen von Clients, bei denen dies nicht der Fall ist, werden abgewiesen.  
  
 Weitere Informationen finden Sie im Beispiel zu Win7 CBT/Erweiterter Schutz.  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))
