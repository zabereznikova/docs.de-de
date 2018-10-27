---
title: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: e3db8cb20399bdff9b73a428ea2a53909da4eee1
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50088766"
---
# <a name="security-validation-and-authentication-failures-per-second"></a>Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde
Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde  
  
## <a name="description"></a>Beschreibung  
 Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird. Zu derartigen Problemen gehören:  
  
-   Clienttoken kann nicht aus der Nachricht gelesen werden.  
  
-   Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.  
  
-   Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).  
  
-   Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.  
  
-   Ein Entschlüsselungsfehler ist aufgetreten.  
  
-   Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.  
  
-   Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 (N1-N0)/((D1-D0)/F)
