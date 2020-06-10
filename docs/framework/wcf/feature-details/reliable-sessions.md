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
ms.openlocfilehash: 910ad952192243c6aa8a79417ad711d8c2a4ba2e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590539"
---
# <a name="reliable-sessions"></a>Zuverlässige Sitzungen

In diesem Abschnitt wird beschrieben, was eine zuverlässige Windows Communication Foundation (WCF)-Sitzung ist, wofür Sie verwendet wird, wie und wann Sie verwendet wird, welche Bindungs Konfigurationen Sie unterstützen, und wie Sie auf bewährte Methoden hinweisen. In der folgenden Tabelle werden Details über die wesentlichen Punkte und verwandte Themen in diesem Abschnitt zusammengefasst.

Die zuverlässige Sitzung WCF stellt Features bereit, die sicherstellen, dass zwischen Endpunkten gesendete Nachrichten über SOAP-oder Transportvermittler übertragen werden und nur einmal und optional in derselben Reihenfolge übermittelt werden, in der Sie gesendet wurden.

Um eine zuverlässige Sitzung mit einer WCF-Anwendung zu verwenden, verwenden Sie entweder eine der vom System bereitgestellten Bindungen in WCF, die eine zuverlässige Sitzung standardmäßig oder als Option unterstützen, oder erstellen Sie eine eigene benutzerdefinierte Bindung, die die Sitzung unterstützt.

## <a name="in-this-section"></a>In diesem Abschnitt

[Übersicht über zuverlässige Sitzungen](reliable-sessions-overview.md) Beschreibt zuverlässige Sitzungen, wann Sie verwendet werden sollen, die verschiedenen Bindungen, die zuverlässige Sitzungen unterstützen, und wie Sie funktionieren.

Vorgehens [Weise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](how-to-exchange-messages-within-a-reliable-session.md) Beschreibt, wie eine zuverlässige Sitzung über HTTP mithilfe einer benutzerdefinierten Bindung erstellt wird, die in der Konfiguration angegeben ist.

Vorgehens [Weise: Sichern von Nachrichten innerhalb zuverlässiger Sitzungen](how-to-secure-messages-within-reliable-sessions.md) Hier wird beschrieben, wie eine zuverlässige Sitzung geschützt wird.

Gewusst [wie: Erstellen einer benutzerdefinierten zuverlässigen Sitzungs Bindung mit HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md) Hier wird beschrieben, wie eine zuverlässige Sitzung über HTTPS erstellt wird.

[Bewährte Methoden für zuverlässige Sitzungen](best-practices-for-reliable-sessions.md) Beschreibt einige bewährte Methoden für die Verwendung einer zuverlässigen Sitzung.

## <a name="reference"></a>Referenz

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>Siehe auch

- [Warteschlangen und zuverlässige Sitzungen](queues-and-reliable-sessions.md)
- [Sitzungen, Instanziierung und Parallelität](sessions-instancing-and-concurrency.md)
