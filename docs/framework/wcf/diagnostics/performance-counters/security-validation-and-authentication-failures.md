---
title: Sicherheitsvalidierung und Authentifizierungsfehler
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 3bcc6111f322a3bd8169567e8f436871eb19f879
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253049"
---
# <a name="security-validation-and-authentication-failures"></a>Sicherheitsvalidierung und Authentifizierungsfehler

Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler  
  
## <a name="description"></a>BESCHREIBUNG  

 Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Zähler "Nicht autorisierte Sicherheitsanrufe" abgedeckt wird. Zu derartigen Problemen gehören:  
  
- Clienttoken kann nicht aus der Nachricht gelesen werden.  
  
- Clienttoken hat die Authentifizierung (z. B. ungültiges Kennwort) nicht bestanden.  
  
- Signaturüberprüfung ist fehlgeschlagen (die Nachricht wurde z. B. manipuliert).  
  
- Die Nachricht ist ein Duplikat einer vorherigen; dies kann während eines Replay-Angriffs geschehen.  
  
- Ein Entschlüsselungsfehler ist aufgetreten.  
  
- Einige erforderliche Elemente (z. B. fehlender Timestamp oder verschlüsselter Datenblock) fehlen in der Nachricht.  
  
- Während des TLSNEGO-/SPNEGO-Handshakes sind Fehler aufgetreten.
