---
title: "Zuverlässige Sitzungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53bb63fbbcf92650085514118a5e9464ab2dea30
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-sessions"></a>Zuverlässige Sitzungen

In diesem Abschnitt wird beschrieben, was eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zuverlässige Sitzung ist, wie Verwendungsweise ist und wenn ein verwenden möchten, welche Bindungskonfiguration hierfür erforderlich, und Verweise auf Practices Best. In der folgenden Tabelle werden Details über die wesentlichen Punkte und verwandte Themen in diesem Abschnitt zusammengefasst.

Die zuverlässige Sitzung [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet Featrues sicherstellen, dass zwischen Endpunkten gesendete Nachrichten über SOAP oder transportvermittler übertragen übertragen werden und werden nur einmal und optional in der gleichen Reihenfolge, in der sie gesendet wurden.

Um eine zuverlässige Sitzung mit einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendung zu verwenden, nutzen Sie entweder eine der vom System bereitgestellten Bindungen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], die eine zuverlässige Sitzung standardmäßig oder als Option unterstützen, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die diese Sitzung unterstützt.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
Beschreibt zuverlässige Sitzungen, wann diese verwendet werden sollten, die verschiedenen Bindungen, die zuverlässige Sitzungen unterstützen, und deren Funktionsweise.

[Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)   
Beschreibt, wie eine zuverlässige Sitzung über HTTP mit einer benutzerdefinierten in der Konfiguration angegebenen Bindung erstellt wird.

[Vorgehensweise: Sichern von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)   
Beschreibt, wie eine zuverlässige Sitzung geschützt wird.

[Vorgehensweise: erstellen eine benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)   
Beschreibt, wie eine zuverlässige Sitzung über HTTPS erstellt wird.

[Bewährte Vorgehensweisen für zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)   
Beschreibt einige der Best Practices in Verbindung mit der Verwendung einer zuverlässigen Sitzung.

## <a name="reference"></a>Verweis

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Siehe auch

[Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)   
[Sitzungen, Instanziierung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
