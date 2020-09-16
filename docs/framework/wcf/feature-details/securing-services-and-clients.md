---
title: Sichern von Diensten und Clients
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: 713737b129771967958fddf44e9ef28583d49422
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554077"
---
# <a name="securing-services-and-clients"></a>Sichern von Diensten und Clients
Die Informationen in diesem Abschnitt konzentrieren sich auf die Programmier Sicherheit in Windows Communication Foundation (WCF). Hierzu zählt im Allgemeinen das Auswählen einer geeigneten vom System bereitgestellten Bindung, das Festlegen der Eigenschaften des Sicherheitselements sowie das anschließende Festlegen von Eigenschaften für das Dienstverhalten, mit denen gesteuert wird, wie Anmeldeinformationen für die Verwendung durch den Dienst oder den Client abgerufen werden. Diese Verfahren decken die Sicherheitsanforderungen der meisten Benutzer für die meisten Szenarien ab, wie in [allgemeinen Sicherheits Szenarios](common-security-scenarios.md)dargestellt. Wenn Ihr Szenario mehr Funktionen erfordert, sehen Sie sich zuerst die [Sicherheitsfunktionen mit benutzerdefinierten Bindungen an](security-capabilities-with-custom-bindings.md). Wenn eine Lösung nicht ersichtlich ist, finden Sie weitere Informationen unter [Erweitern der Sicherheit](../extending/extending-security.md). Wenn Sie ein System erstellen (oder mit diesem zusammenarbeiten), das umfangreiche Ansprüche verwendet, lesen Sie die Themen unter [Autorisierung](authorization-in-wcf.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Programmieren der WCF-Sicherheit](programming-wcf-security.md)  
 Eine Übersicht über das Programmiermodell, das zum Sichern von Nachrichten verwendet wird.  
  
 [Übersicht über die Transportsicherheit](transport-security-overview.md)  
 Eine Übersicht über das Sichern von Nachrichten mithilfe der Transportschicht.  
  
 [Nachrichtensicherheit](message-security-in-wcf.md)  
 Fasst die Gründe für die Verwendung der Sicherheit auf Nachrichten Ebene in Windows Communication Foundation (WCF) zusammen.  
  
 [Sichere Sitzungen](secure-sessions.md)  
 Eine Erläuterung der Punkte, die beim Sichern einer WCF-Sitzung erforderlich sind.  
  
 [Verwenden von Zertifikaten](working-with-certificates.md)  
 Eine Erläuterung einiger der allgemeinen Aufgaben, die bei Verwendung von X.509-Zertifikaten erforderlich sind.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Sicherheitskonzepte](security-concepts.md)  
  
 [Erweitern der Sicherheit](../extending/extending-security.md)  
  
 [Häufige Sicherheitsszenarien](common-security-scenarios.md)  
  
 [Bindungen und Sicherheit](bindings-and-security.md)  
  
 [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](security-capabilities-with-custom-bindings.md)  
  
 [Erweitern der Sicherheit](../extending/extending-security.md)  
  
 [Autorisierung](authorization-in-wcf.md)  
  
## <a name="see-also"></a>Siehe auch

- [Einfache WCF-Programmierung](../basic-wcf-programming.md)
- [Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))
