---
title: Zuverlässige Sitzungen
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 1d87f6f4d94763dc8f6ac7e929c22b17940097ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735424"
---
# <a name="reliable-sessions"></a>Zuverlässige Sitzungen

In diesem Abschnitt wird beschrieben, welche eines Windows Communication Foundation (WCF) zuverlässige Sitzung ist, wofür sie, wie verwendet wird und wenn eine solche welche hierfür Bindungskonfiguration und Verweise auf Practices Best. In der folgenden Tabelle werden Details über die wesentlichen Punkte und verwandte Themen in diesem Abschnitt zusammengefasst.

Die zuverlässige Sitzung WCF bietet integrierten Funktionen zur sicherzustellen, dass zwischen Endpunkten gesendete Nachrichten über SOAP oder transportvermittler übertragen übertragen werden und werden nur einmal und optional in der gleichen Reihenfolge, in der sie gesendet wurden, bereitgestellt.

Um eine zuverlässige Sitzung mit einer WCF-Anwendung verwenden möchten, verwenden Sie eine der vom System bereitgestellten Bindungen in WCF, die eine zuverlässige Sitzung standardmäßig oder als Option unterstützen, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die die Sitzung unterstützt.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
Beschreibt zuverlässige Sitzungen, wann diese verwendet werden sollten, die verschiedenen Bindungen, die zuverlässige Sitzungen unterstützen, und deren Funktionsweise.

[Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)   
Beschreibt, wie eine zuverlässige Sitzung über HTTP mit einer benutzerdefinierten in der Konfiguration angegebenen Bindung erstellt wird.

[Vorgehensweise: Sichern von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)   
Beschreibt, wie eine zuverlässige Sitzung geschützt wird.

[Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)   
Beschreibt, wie eine zuverlässige Sitzung über HTTPS erstellt wird.

[Bewährte Methoden für zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)   
Beschreibt einige der Best Practices in Verbindung mit der Verwendung einer zuverlässigen Sitzung.

## <a name="reference"></a>Referenz

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Siehe auch

- [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [Sitzungen, Instanzerstellung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
