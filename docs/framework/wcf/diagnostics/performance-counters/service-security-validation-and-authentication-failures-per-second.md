---
title: 'Dienst: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
ms.openlocfilehash: f66e6b90622cf181229938bc4fd877a98cd23a48
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236883"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a>Dienst: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde

Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird. Zu derartigen Problemen gehören:  
  
- Clienttoken kann nicht aus der Nachricht gelesen werden.  
  
- Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.  
  
- Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).  
  
- Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.  
  
- Ein Entschlüsselungsfehler ist aufgetreten.  
  
- Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.  
  
- Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.  
  
 Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird.  
  
 (N 1 - N 0)/( (D 1 - D 0)/F)
