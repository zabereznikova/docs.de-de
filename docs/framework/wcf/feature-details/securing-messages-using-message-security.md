---
title: Sichern von Nachrichten mithilfe der Nachrichtensicherheit
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a17ebe67-836b-4c52-9a81-2c3d58e225ee
caps.latest.revision: 16
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 088b01151d0471527bbfc2ffa04b5b5064700081
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="securing-messages-using-message-security"></a>Sichern von Nachrichten mithilfe der Nachrichtensicherheit
In diesem Abschnitt wird die Nachrichtensicherheit von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bei der Verwendung von <xref:System.ServiceModel.NetMsmqBinding> erläutert.  
  
> [!NOTE]
>  In diesem Thema lesen, wird empfohlen, vor dem Lesen Sie [Schlüsselbegriffe der Sicherheit](../../../../docs/framework/wcf/feature-details/security-concepts.md).  
  
 Die folgende Abbildung zeigt ein Modell einer Kommunikation unter Verwendung von Warteschlangen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Anhand dieser Abbildung und der Terminologie werden  
  
 die Konzepte der Transportsicherheit erläutert.  
  
 ![In der Warteschlange Anwendungsdiagramm](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed-Warteschlange-Abbildung")  
  
 Wenn Sie Nachrichten in einer Warteschlange in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] senden, wird die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Nachricht als Textkörper der MSMQ-Nachricht (Message Queuing) angefügt. Mit der Transportsicherheit wird die gesamte MSMQ-Nachricht gesichert, mit der Nachrichtensicherheit (oder SOAP-Sicherheit) hingegen wird nur der Textkörper der MSMQ-Nachricht gesichert.  
  
 Das Kernkonzept der Nachrichtensicherheit besteht darin, dass der Client die Nachricht für die empfangende Anwendung (Dienst) sichert. Im Gegensatz dazu sichert der Client bei der Transportsicherheit die Nachricht für die Zielwarteschlange. Folglich spielt MSMQ keine aktive Rolle, wenn die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Nachricht mit der Nachrichtensicherheit gesichert wird.  
  
 Mit der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Nachrichtensicherheit werden der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Nachricht Sicherheitsheader hinzugefügt, die sich in vorhandene Sicherheitsinfrastrukuren integrieren lassen, wie z. B. ein Zertifikat oder das Kerberos-Protokoll.  
  
## <a name="message-credential-type"></a>Anmeldeinformationstypen für Nachrichten  
 Bei der Verwendung der Nachrichtensicherheit können der Dienst und der Client Anmeldeinformationen bereitstellen, um sich gegenseitig zu authentifizieren. Sie können die Nachrichtensicherheit auswählen, indem Sie den <xref:System.ServiceModel.NetMsmqBinding.Security%2A>-Modus auf `Message` oder `Both` (d. h. Transport- und Nachrichtensicherheit werden verwendet) festlegen.  
  
 Der Dienst kann anhand der <xref:System.ServiceModel.ServiceSecurityContext.Current%2A>-Eigenschaft die Anmeldeinformationen überprüfen, mit denen der Client authentifiziert wird. Damit können weitere Autorisierungsüberprüfungen vorgenommen werden, die der Dienst zur Implementierung auswählen kann.  
  
 Dieser Abschnitt erklärt die verschiedenen Anmeldeinformationstypen und ihre Verwendung mit Warteschlangen.  
  
### <a name="certificate"></a>Zertifikat  
 Der Zertifikat-Anmeldeinformationstyp identifiziert mit einem X.509-Zertifikat den Dienst und den Client.  
  
 In einem typischen Szenario stellt eine vertrauenswürdige Zertifizierungsstelle dem Client und dem Dienst ein gültiges Zertifikat aus. Dann wird die Verbindung hergestellt, und der Client authentifiziert die Gültigkeit des Dienstes, indem er anhand des Zertifikat des Dienstes entscheidet, ob der Dienst vertrauenswürdig ist. Entsprechend verwendet der Dienst das Zertifikat des Clients, um dessen Vertrauenswürdigkeit zu überprüfen.  
  
 Da im Fall von Warteschlangen nicht immer eine Verbindung hergestellt ist, sind der Client und der Dienst möglicherweise nicht zur selben Zeit online. Daher müssen der Client und der Dienst Zertifikate out-of-band austauschen. Insbesondere der Client, bei dem sich das Dienstzertifikat (das mit einer Zertifizierungsstelle verkettet sein kann) im vertrauenswürdigen Speicher befindet, muss verlässlich mit dem richtigen Dienst kommunizieren. Zur Authentifizierung des Clients gleicht der Dienst das X.509-Zertifikat, das an die Nachricht angehängt ist, mit dem Zertifikat in seinem Speicher ab, um die Echtzeit des Clients zu überprüfen. Auch hier muss das Zertifikat mit einer Zertifizierungsstelle verkettet sein.  
  
 Auf einem Computer unter Windows befinden sich die Zertifikate in verschiedenen Arten von Speichern. Weitere Informationen zu den verschiedenen speichern, finden Sie unter [Zertifikatspeichern](http://go.microsoft.com/fwlink/?LinkId=87787).  
  
### <a name="windows"></a>Windows  
 Der Windows-Anmeldeinformationstyp für Nachrichten verwendet das Kerberos-Protokoll.  
  
 Das Kerberos-Protokoll ist ein Sicherheitsmechanismus, der Benutzer in einer Domäne authentifiziert und den authentifizierten Benutzern das Erstellen sicherer Kontexte mit anderen Entitäten einer Domäne ermöglicht.  
  
 Die Verwendung des Kerberos-Protokolls für die Kommunikation unter Verwendung von Warteschlangen ist problematisch, insofern als die vom Schlüsselverteilungscenter verteilten Tickets mit der Clientidentität relativ kurzlebig sind. Ein *Lebensdauer* bezieht sich auf das Kerberos-Ticket, der die Gültigkeit des Tickets angibt. Bei einer hohen Latenz können Sie somit nicht sicher sein, ob das Token noch für den Dienst gültig ist, der den Client authentifiziert.  
  
 Wenn dieser Anmeldeinformationstyp verwendet wird, muss der Dienst unter dem SERVICE-Konto ausgeführt werden.  
  
 Das Kerberos-Protokoll wird standardmäßig bei der Auswahl von Nachrichtenanmeldeinformationen verwendet. Weitere Informationen finden Sie unter [Kerberos untersuchen, das Protokoll für verteilte Sicherheit in Windows 2000](http://go.microsoft.com/fwlink/?LinkId=87790).  
  
### <a name="username-password"></a>Benutzernamenkennwort (Username Password)  
 Mit dieser Eigenschaft kann sich der Client beim Server durch Angabe eines Benutzernamenkennworts im Sicherheitsheader der Nachricht authentifizieren.  
  
### <a name="issuedtoken"></a>IssuedToken  
 Der Client kann den Sicherheitstokendienst zum Ausstellen eines Tokens verwenden. Dieses Token kann dann der Nachricht angefügt werden, um den Client für den Dienst zu identifizieren.  
  
## <a name="using-transport-and-message-security"></a>Verwenden der Transport- und der Nachrichtensicherheit  
 Wenn die Transportsicherheit und die Nachrichtensicherheit verwendet werden, muss das auf der Transportebene zum Sichern der Nachricht verwendete Zertifikat mit dem auf der SOAP-Nachrichtenebene verwendeten Zertifikat identisch sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von Nachrichten mit Transportsicherheit](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 [Nachrichtensicherheit über Message Queuing](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)  
 [Begriffe der Sicherheit](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
