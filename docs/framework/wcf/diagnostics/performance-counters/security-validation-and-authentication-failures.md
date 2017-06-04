---
title: "Sicherheitsvalidierung und Authentifizierungsfehler | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Sicherheitsvalidierung und Authentifizierungsfehler
Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler  
  
## Beschreibung  
 Dieser Zähler wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Indikator "Nicht autorisierte Sicherheitsaufrufe" abgedeckt wird.Zu derartigen Problemen gehören:  
  
-   Clienttoken kann nicht von der Nachricht gelesen werden.  
  
-   Clienttoken hat die Authentifizierung \(z. B. ungültiges Kennwort\) nicht bestanden.  
  
-   Signaturüberprüfung ist fehlgeschlagen \(die Nachricht wurde z. B. manipuliert\).  
  
-   Die Nachricht ist ein Duplikat einer vorherigen, die während eines Wiederholungsangriffs vorkommen kann.  
  
-   Ein Entschlüsselungsfehler ist aufgetreten.  
  
-   Einige erforderliche Elemente \(z. B. fehlender Timestamp oder verschlüsselter Datenblock\) fehlen in der Nachricht.  
  
-   Während des TLSNEGO\-\/SPNEGO\-Handshakes sind Fehler aufgetreten.