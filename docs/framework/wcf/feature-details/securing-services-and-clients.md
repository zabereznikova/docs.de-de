---
title: Sichern von Diensten und Clients
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 52e07a83f5a1b84abc46f00e6fd6e80e4b9a2622
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="securing-services-and-clients"></a>Sichern von Diensten und Clients
Im Mittelpunkt dieses Abschnitts stehen Informationen zur Programmiersicherheit in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Hierzu zählt im Allgemeinen das Auswählen einer geeigneten vom System bereitgestellten Bindung, das Festlegen der Eigenschaften des Sicherheitselements sowie das anschließende Festlegen von Eigenschaften für das Dienstverhalten, mit denen gesteuert wird, wie Anmeldeinformationen für die Verwendung durch den Dienst oder den Client abgerufen werden. Diese Techniken die sicherheitsanforderungen der meisten Benutzer in den meisten Szenarien abzudecken, wie gezeigt in [häufige Sicherheitsszenarien](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Wenn Ihr Szenario mehr Funktionen erfordert, zuerst finden Sie unter [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); ist eine Lösung nicht offensichtlich, finden Sie unter [Erweitern der Sicherheit](../../../../docs/framework/wcf/extending/extending-security.md). Wenn Sie erstellen (oder Interoperabilität mit) ein Systems, die umfangreiche Ansprüche verwendet, finden Sie unter den Themen in [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Programmieren der WCF-Sicherheit](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 Eine Übersicht über das Programmiermodell, das zum Sichern von Nachrichten verwendet wird.  
  
 [Übersicht über die Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 Eine Übersicht über das Sichern von Nachrichten mithilfe der Transportschicht.  
  
 [Nachrichtensicherheit](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 Eine Zusammenfassung von Gründen für die Verwendung der Sicherheit auf Nachrichtenebene in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 [Sichere Sitzungen](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 Eine Diskussion der erforderlichen Überlegungen für das Sichern einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Sitzung.  
  
 [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 Eine Erläuterung einiger der allgemeinen Aufgaben, die bei Verwendung von X.509-Zertifikaten erforderlich sind.  
  
## <a name="reference"></a>Verweis  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Begriffe der Sicherheit](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [Erweitern der Sicherheit](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [Häufige Sicherheitsszenarien](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [Bindungen und Sicherheit](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [Erweitern der Sicherheit](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Einfache WCF-Programmierung](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
