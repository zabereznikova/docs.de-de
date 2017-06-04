---
title: "Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde
Indikatorname: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde  
  
## Beschreibung  
 Dieser Indikator wird jedes Mal inkrementiert, wenn eine Nachricht wegen eines Sicherheitsproblems abgelehnt wird, das nicht von dem Indikator "Nicht authorisierte Sicherheitsaufrufe" abgedeckt wird.Zu derartigen Problemen gehören:  
  
-   Clienttoken kann nicht von der Nachricht gelesen werden.  
  
-   Clienttoken hat die Authentifizierung \(z. B. ungültiges Kennwort\) nicht bestanden.  
  
-   Signaturüberprüfung ist fehlgeschlagen \(die Nachricht wurde z. B. manipuliert\).  
  
-   Die Nachricht ist ein Duplikat einer vorherigen, die während eines Wiederholungsangriffs vorkommen kann.  
  
-   Ein Entschlüsselungsfehler ist aufgetreten.  
  
-   Einige erforderliche Elemente \(z. B. fehlender Timestamp oder verschlüsselter Datenblock\) fehlen in der Nachricht.  
  
-   Während des TLSNEGO\-\/SPNEGO\-Handshakes sind Fehler aufgetreten.  
  
 Bei diesem Zähler handelt es sich um einen Leistungsindikator vom Typ [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), dessen Wert anhand der folgenden Formel berechnet wird:  
  
 \(N1\-N0\)\/\(\(D1\-D0\)\/F\)