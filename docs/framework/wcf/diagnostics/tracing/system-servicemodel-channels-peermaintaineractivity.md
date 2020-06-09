---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: ce97eaa2ad5c9dbd5f4d6f81186960c489eb4b85
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596076"
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a>System.ServiceModel.Channels.PeerMaintainerActivity
Das PeerMaintainer-Modul führt einen bestimmten Vorgang (Details innerhalb des Ablaufverfolgungsnachrichtentexts) aus.  
  
## <a name="description"></a>BESCHREIBUNG  
 Diese Ablaufverfolgung tritt während verschiedener PeerMaintainer-Vorgänge auf.  
  
 PeerMaintainer ist eine interne Komponente von PeerNode. Jede Minute &#8211; oder nach 32&#160;empfangenen Nachrichten &#8211; wird eine LinkUtility-Nachricht an die Nachbarn gesendet. Diese Nachricht enthält eine Statistik mit der Anzahl der ausgetauschten Nachrichten sowie mit Informationen dazu, wie viele der Nachrichten nützlich waren (also keine Duplikate und nicht manipuliert). Dadurch lässt sich das Verknüpfungsprogramm eines bestimmten Nachbarn ermitteln. Etwa alle fünf Minuten überprüft der Maintainer die Integrität der Nachbarverbindungen. Übersteigt die Anzahl von Nachbarverbindungen die Idealmenge, werden die am wenigsten nützlichen Verbindungen entfernt. Sind nicht genügend Verbindungen verfügbar, werden vom Maintainer neue Verbindungen eingerichtet.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ablaufverfolgung](index.md)
- [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](using-tracing-to-troubleshoot-your-application.md)
- [Verwaltung und Diagnose](../index.md)
