---
title: 'Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: a6d76a0d11c52d20aebd44a85862c802cc0a68f7
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912481"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a>Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde
Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde  
  
## <a name="description"></a>Beschreibung  
 Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird. Zu derartigen Problemen gehören:  
  
- Clienttoken kann nicht aus der Nachricht gelesen werden.  
  
- Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.  
  
- Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).  
  
- Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.  
  
- Ein Entschlüsselungsfehler ist aufgetreten.  
  
- Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.  
  
- Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.  
  
 Dieser Indikator wird der Leistungsindikator vom Typ [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 (N1-N0)/((D1-D0)/F)
