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
ms.openlocfilehash: 9a2cd06c4c5a73d9fb5c4c7f09632e10c3eb0d87
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991158"
---
# <a name="reliable-sessions"></a>Zuverlässige Sitzungen

In diesem Abschnitt wird beschrieben, welche eines Windows Communication Foundation (WCF) zuverlässige Sitzung ist, wofür sie, wie verwendet wird und wenn eine solche welche hierfür Bindungskonfiguration und Verweise auf Practices Best. In der folgenden Tabelle werden Details über die wesentlichen Punkte und verwandte Themen in diesem Abschnitt zusammengefasst.

Die zuverlässige Sitzung WCF bietet Funktionen, die sicherstellen, dass zwischen Endpunkten gesendete Nachrichten über SOAP oder transportvermittler übertragen übertragen werden und werden nur einmal und optional in der gleichen Reihenfolge, in der sie gesendet wurden, bereitgestellt.

Um eine zuverlässige Sitzung mit einer WCF-Anwendung verwenden möchten, verwenden Sie eine der vom System bereitgestellten Bindungen in WCF, die eine zuverlässige Sitzung standardmäßig oder als Option unterstützen, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die die Sitzung unterstützt.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md) beschreibt zuverlässige Sitzungen, wann sie zu, die verschiedenen Bindungen verwenden, die zuverlässige Sitzungen unterstützen und zu deren Funktionsweise.

[Vorgehensweise: Exchange-Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) enthält Informationen zum Erstellen einer zuverlässigen Sitzungs über HTTP unter Verwendung einer benutzerdefinierten Bindung, die in der Konfiguration angegeben.

[Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md) wird beschrieben, wie eine zuverlässige Sitzung geschützt.

[Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzung Bindungen mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md) wird beschrieben, wie eine zuverlässige Sitzung über HTTPS zu erstellen.

[Bewährte Methoden für zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md) beschreibt einige bewährte Methoden für die Verwendung einer zuverlässigen Sitzungs.

## <a name="reference"></a>Referenz

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Siehe auch

- [Warteschlangen und zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [Sitzungen, Instanzerstellung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
