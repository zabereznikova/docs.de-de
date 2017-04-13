---
title: "Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# Endpunkt: Sicherheitsvalidierung und Authentifizierungsfehler
Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler  
  
## Beschreibung  
 Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Indikator "Nicht autorisierte Sicherheitsaufrufe" abgedeckt wird.Zu derartigen Problemen gehören:  
  
-   Clienttoken kann nicht aus der Nachricht gelesen werden.  
  
-   Clienttoken hat die Authentifizierung \(ungültiges Kennwort\) nicht bestanden.  
  
-   Signaturprüfung ist fehlgeschlagen \(die Nachricht wurde manipuliert\).  
  
-   Die Nachricht ist ein Duplikat von einer vorherigen; dies kann während eines Replay\-Angriffes geschehen.  
  
-   Ein Entschlüsselungsfehler ist aufgetreten.  
  
-   Einige erforderliche Elemente \(fehlender Timestamp oder verschlüsselter Datenblock\) fehlen in der Nachricht.  
  
-   Während des TLSNEGO\-\/SPNEGO\-Handshakes sind Fehler aufgetreten.