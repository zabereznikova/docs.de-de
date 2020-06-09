---
title: Sichern von Nachrichten mithilfe der Nachrichtensicherheit
ms.date: 03/30/2017
ms.assetid: a17ebe67-836b-4c52-9a81-2c3d58e225ee
ms.openlocfilehash: 70c645101033c31da01d79f624ab03ce328dd3a6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589980"
---
# <a name="securing-messages-using-message-security"></a>Sichern von Nachrichten mithilfe der Nachrichtensicherheit
In diesem Abschnitt wird die WCF-Nachrichten Sicherheit bei Verwendung von erörtert <xref:System.ServiceModel.NetMsmqBinding> .  
  
> [!NOTE]
> Bevor Sie dieses Thema lesen, empfiehlt es sich, [Sicherheitskonzepte](security-concepts.md)zu lesen.  
  
 Die folgende Abbildung stellt ein konzeptionelles Modell der Kommunikation in der Warteschlange mithilfe von WCF bereit. Anhand dieser Abbildung und der Terminologie werden  
  
 die Konzepte der Transportsicherheit erläutert.  
  
 ![In die Warteschlange gestelltes Anwendungsdiagramm](media/distributed-queue-figure.jpg "Verteilte Warteschlangen (Abbildung)")  
  
 Beim Senden von Nachrichten in der Warteschlange mithilfe von WCF wird die WCF-Nachricht als Text der MSMQ-Nachricht (Message Queuing) angefügt. Mit der Transportsicherheit wird die gesamte MSMQ-Nachricht gesichert, mit der Nachrichtensicherheit (oder SOAP-Sicherheit) hingegen wird nur der Textkörper der MSMQ-Nachricht gesichert.  
  
 Das Kernkonzept der Nachrichtensicherheit besteht darin, dass der Client die Nachricht für die empfangende Anwendung (Dienst) sichert. Im Gegensatz dazu sichert der Client bei der Transportsicherheit die Nachricht für die Zielwarteschlange. Daher spielt MSMQ keinen Teil, wenn die WCF-Nachricht mithilfe der Nachrichten Sicherheit gesichert wird.  
  
 WCF Message Security fügt der WCF-Nachricht Sicherheits Header hinzu, die in vorhandene Sicherheitsinfrastrukturen integriert sind, z. b. ein Zertifikat oder das Kerberos-Protokoll.  
  
## <a name="message-credential-type"></a>Anmeldeinformationstypen für Nachrichten  
 Bei der Verwendung der Nachrichtensicherheit können der Dienst und der Client Anmeldeinformationen bereitstellen, um sich gegenseitig zu authentifizieren. Sie können die Nachrichtensicherheit auswählen, indem Sie den <xref:System.ServiceModel.NetMsmqBinding.Security%2A>-Modus auf `Message` oder `Both` (d. h. Transport- und Nachrichtensicherheit werden verwendet) festlegen.  
  
 Der Dienst kann anhand der <xref:System.ServiceModel.ServiceSecurityContext.Current%2A>-Eigenschaft die Anmeldeinformationen überprüfen, mit denen der Client authentifiziert wird. Damit können weitere Autorisierungsüberprüfungen vorgenommen werden, die der Dienst zur Implementierung auswählen kann.  
  
 Dieser Abschnitt erklärt die verschiedenen Anmeldeinformationstypen und ihre Verwendung mit Warteschlangen.  
  
### <a name="certificate"></a>Zertifikat  
 Der Zertifikat-Anmeldeinformationstyp identifiziert mit einem X.509-Zertifikat den Dienst und den Client.  
  
 In einem typischen Szenario stellt eine vertrauenswürdige Zertifizierungsstelle dem Client und dem Dienst ein gültiges Zertifikat aus. Dann wird die Verbindung hergestellt, und der Client authentifiziert die Gültigkeit des Dienstes, indem er anhand des Zertifikat des Dienstes entscheidet, ob der Dienst vertrauenswürdig ist. Entsprechend verwendet der Dienst das Zertifikat des Clients, um dessen Vertrauenswürdigkeit zu überprüfen.  
  
 Da im Fall von Warteschlangen nicht immer eine Verbindung hergestellt ist, sind der Client und der Dienst möglicherweise nicht zur selben Zeit online. Daher müssen der Client und der Dienst Zertifikate out-of-band austauschen. Insbesondere der Client, bei dem sich das Dienstzertifikat (das mit einer Zertifizierungsstelle verkettet sein kann) im vertrauenswürdigen Speicher befindet, muss verlässlich mit dem richtigen Dienst kommunizieren. Zur Authentifizierung des Clients gleicht der Dienst das X.509-Zertifikat, das an die Nachricht angehängt ist, mit dem Zertifikat in seinem Speicher ab, um die Echtzeit des Clients zu überprüfen. Auch hier muss das Zertifikat mit einer Zertifizierungsstelle verkettet sein.  
  
 Auf einem Computer unter Windows befinden sich die Zertifikate in verschiedenen Arten von Speichern. Weitere Informationen zu den unterschiedlichen speichern finden Sie unter [Zertifikat Speicher](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc757138(v=ws.10)).  
  
### <a name="windows"></a>Windows  
 Der Windows-Anmeldeinformationstyp für Nachrichten verwendet das Kerberos-Protokoll.  
  
 Das Kerberos-Protokoll ist ein Sicherheitsmechanismus, der Benutzer in einer Domäne authentifiziert und den authentifizierten Benutzern das Erstellen sicherer Kontexte mit anderen Entitäten einer Domäne ermöglicht.  
  
 Die Verwendung des Kerberos-Protokolls für die Kommunikation unter Verwendung von Warteschlangen ist problematisch, insofern als die vom Schlüsselverteilungscenter verteilten Tickets mit der Clientidentität relativ kurzlebig sind. Dem Kerberos-Ticket wird eine *Lebensdauer* zugeordnet, die die Gültigkeit des Tickets angibt. Bei einer hohen Latenz können Sie somit nicht sicher sein, ob das Token noch für den Dienst gültig ist, der den Client authentifiziert.  
  
 Wenn dieser Anmeldeinformationstyp verwendet wird, muss der Dienst unter dem SERVICE-Konto ausgeführt werden.  
  
 Das Kerberos-Protokoll wird standardmäßig bei der Auswahl von Nachrichtenanmeldeinformationen verwendet.
  
### <a name="username-password"></a>Benutzernamenkennwort (Username Password)  
 Mit dieser Eigenschaft kann sich der Client beim Server durch Angabe eines Benutzernamenkennworts im Sicherheitsheader der Nachricht authentifizieren.  
  
### <a name="issuedtoken"></a>IssuedToken  
 Der Client kann den Sicherheitstokendienst zum Ausstellen eines Tokens verwenden. Dieses Token kann dann der Nachricht angefügt werden, um den Client für den Dienst zu identifizieren.  
  
## <a name="using-transport-and-message-security"></a>Verwenden der Transport- und der Nachrichtensicherheit  
 Wenn die Transportsicherheit und die Nachrichtensicherheit verwendet werden, muss das auf der Transportebene zum Sichern der Nachricht verwendete Zertifikat mit dem auf der SOAP-Nachrichtenebene verwendeten Zertifikat identisch sein.  
  
## <a name="see-also"></a>Weitere Informationen

- [Sichern von Nachrichten mit Transportsicherheit](securing-messages-using-transport-security.md)
- [Nachrichtensicherheit über Message Queuing](../samples/message-security-over-message-queuing.md)
- [Sicherheitskonzepte](security-concepts.md)
- [Sichern von Diensten und Clients](securing-services-and-clients.md)
