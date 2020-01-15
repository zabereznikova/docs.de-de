---
title: Häufige Sicherheitsszenarien
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: 578ec2d7d5abe1285007ad22d8bacd69e695b1d3
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964285"
---
# <a name="common-security-scenarios"></a>Häufige Sicherheitsszenarien
Die Themen in diesem Abschnitt katalogisieren eine Anzahl möglicher Client- und Dienstsicherheitskonfigurationen. Die Konfigurationen ändern sich aufgrund verschiedenster Faktoren. Zum Beispiel ob sich ein Dienst oder Client im Intranet befindet oder ob die Sicherheit von Windows oder vom Transport (wie HTTPS) gewährleistet wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Internet: Ungesicherter Client und Dienst](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 Ein Beispiel eines öffentlichen, ungesicherten Clients und Diensts.  
  
 [Intranet: Ungesicherter Client und Dienst](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 Ein grundlegender Windows Communication Foundation (WCF)-Dienst, der entwickelt wurde, um Informationen zu einem sicheren privaten Netzwerk für eine WCF-Anwendung bereitzustellen.  
  
 [Transportsicherheit mit Standardauthentifizierung](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 Mit dieser Anwendung können sich Clients anhand einer benutzerdefinierten Authentifizierung anmelden.  
  
 [Transportsicherheit mit Windows-Authentifizierung](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 Zeigt einen von der Windows-Sicherheit gesicherten Client und Dienst.  
  
 [Transportsicherheit mit einem anonymen Client](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 Dieses Szenario verwendet die Transportsicherheit (wie HTTPS), um Vertraulichkeit und Integrität sicherzustellen.  
  
 [Transportsicherheit mit Zertifikatauthentifizierung](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 Zeigt einen mit einem Zertifikat gesicherten Client und Dienst.  
  
 [Nachrichtensicherheit mit einem anonymen Client](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 Zeigt einen von der WCF-Nachrichten Sicherheit gesicherten Client und Dienst.  
  
 [Nachrichtensicherheit mit einem Benutzernamenclient](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 Der Client ist eine Windows Forms-Anwendung, mit der sich die Clients mithilfe eines Domänenbenutzernamens und -Kennworts anmelden können.  
  
 [Nachrichtensicherheit mit einem Zertifikatclient](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 Server haben Zertifikate, und jeder Client hat ein Zertifikat. Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.  
  
 [Nachrichtensicherheit mit einem Windows-Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 Eine Variante des Zertifikatsclients. Server haben Zertifikate, und jeder Client hat ein Zertifikat. Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.  
  
 [Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationenaushandlung](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 Zeigt einen von einer Kerberos-Domäne gesicherten Client und Dienst.  
  
 [Nachrichtensicherheit mit gegenseitigen Zertifikaten](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 Server haben Zertifikate, und jeder Client hat ein Zertifikat. Das Serverzertifikat wird mit der Anwendung verteilt und steht außerhalb des Bereichs zur Verfügung.  
  
 [Nachrichtensicherheit durch ausgestellte Token](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 Verbundsicherheit, die Vertrauenswürdigkeit zwischen unabhängigen Domänen ermöglicht.  
  
 [Vertrauenswürdiges Subsystem](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 Ein Client greift auf einen oder mehrere Webdienste zu, die über das Netzwerk verteilt werden. Die Webdienste greifen auf zusätzliche Ressourcen (z. B. Datenbanken oder andere Webdienste) zu, die gesichert werden müssen.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Bindungen und Sicherheit](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [Authentifizierung](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a>Siehe auch

- [Sicherheitsleitfaden und bewährte Methoden](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)
- [Sicherheitsmodell für Windows Server-App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
