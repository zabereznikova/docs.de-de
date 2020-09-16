---
title: Häufige Sicherheitsszenarien
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: cfd29f8cae8ac362a5fa1709864dce4ae11b5af6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558887"
---
# <a name="common-security-scenarios"></a>Häufige Sicherheitsszenarien
Die Themen in diesem Abschnitt katalogisieren eine Anzahl möglicher Client- und Dienstsicherheitskonfigurationen. Die Konfigurationen ändern sich aufgrund verschiedenster Faktoren. Zum Beispiel ob sich ein Dienst oder Client im Intranet befindet oder ob die Sicherheit von Windows oder vom Transport (wie HTTPS) gewährleistet wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Internet: Ungesicherter Client und Dienst](internet-unsecured-client-and-service.md)  
 Ein Beispiel eines öffentlichen, ungesicherten Clients und Diensts.  
  
 [Intranet: Ungesicherter Client und Dienst](intranet-unsecured-client-and-service.md)  
 Ein grundlegender Windows Communication Foundation (WCF)-Dienst, der entwickelt wurde, um Informationen zu einem sicheren privaten Netzwerk für eine WCF-Anwendung bereitzustellen.  
  
 [Transportsicherheit mit Standardauthentifizierung](transport-security-with-basic-authentication.md)  
 Mit dieser Anwendung können sich Clients anhand einer benutzerdefinierten Authentifizierung anmelden.  
  
 [Transportsicherheit mit Windows-Authentifizierung](transport-security-with-windows-authentication.md)  
 Zeigt einen von der Windows-Sicherheit gesicherten Client und Dienst.  
  
 [Transportsicherheit mit einem anonymen Client](transport-security-with-an-anonymous-client.md)  
 Dieses Szenario verwendet die Transportsicherheit (wie HTTPS), um Vertraulichkeit und Integrität sicherzustellen.  
  
 [Transportsicherheit mit Zertifikatauthentifizierung](transport-security-with-certificate-authentication.md)  
 Zeigt einen mit einem Zertifikat gesicherten Client und Dienst.  
  
 [Nachrichtensicherheit mit einem anonymen Client](message-security-with-an-anonymous-client.md)  
 Zeigt einen von der WCF-Nachrichten Sicherheit gesicherten Client und Dienst.  
  
 [Nachrichtensicherheit über einen Benutzernamenclient](message-security-with-a-user-name-client.md)  
 Der Client ist eine Windows Forms-Anwendung, mit der sich die Clients mithilfe eines Domänenbenutzernamens und -Kennworts anmelden können.  
  
 [Nachrichtensicherheit durch einem Zertifikatclient](message-security-with-a-certificate-client.md)  
 Server haben Zertifikate, und jeder Client hat ein Zertifikat. Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.  
  
 [Nachrichtensicherheit über einen Windows-Client](message-security-with-a-windows-client.md)  
 Eine Variante des Zertifikatsclients. Server haben Zertifikate, und jeder Client hat ein Zertifikat. Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.  
  
 [Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationen-Aushandlung](message-security-with-a-windows-client-without-credential-negotiation.md)  
 Zeigt einen von einer Kerberos-Domäne gesicherten Client und Dienst.  
  
 [Nachrichtensicherheit durch gegenseitige Zertifikate](message-security-with-mutual-certificates.md)  
 Server haben Zertifikate, und jeder Client hat ein Zertifikat. Das Serverzertifikat wird mit der Anwendung verteilt und steht außerhalb des Bereichs zur Verfügung.  
  
 [Nachrichtensicherheit durch ausgestellte Token](message-security-with-issued-tokens.md)  
 Verbundsicherheit, die Vertrauenswürdigkeit zwischen unabhängigen Domänen ermöglicht.  
  
 [Vertrauenswürdiges Subsystem](trusted-subsystem.md)  
 Ein Client greift auf einen oder mehrere Webdienste zu, die über das Netzwerk verteilt werden. Die Webdienste greifen auf zusätzliche Ressourcen (z. B. Datenbanken oder andere Webdienste) zu, die gesichert werden müssen.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Autorisierung](authorization-in-wcf.md)  
  
 [Sicherheitsübersicht](security-overview.md)  
  
 [Security](security.md)  
  
 [Bindungen und Sicherheit](bindings-and-security.md)  
  
 [Sichern von Diensten und Clients](securing-services-and-clients.md)  
  
 [Authentifizierung](authentication-in-wcf.md)  
  
 [Autorisierung](authorization-in-wcf.md)  
  
 [Verbund und ausgestellte Token](federation-and-issued-tokens.md)  
  
 [Überwachung](auditing-security-events.md)  
  
## <a name="see-also"></a>Siehe auch

- [Sicherheitsleitfaden und empfohlene Vorgehensweisen](security-guidance-and-best-practices.md)
- [Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))
