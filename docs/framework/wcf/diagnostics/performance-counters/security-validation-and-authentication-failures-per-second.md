---
title: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: c64c121550043127db674fac6287a870449d789d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253120"
---
# <a name="security-validation-and-authentication-failures-per-second"></a>Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde

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
  
 Dieser Leistungs Bewert ist vom Typ [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))des Leistungs Zählers, dessen Wert mit der folgenden Formel berechnet wird:  
  
 (N1-N0)/((D1-D0)/F)
