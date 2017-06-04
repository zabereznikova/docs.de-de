---
title: "Dienst: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# Dienst: Sicherheitsvalidierung und Authentifizierungsfehler pro Sekunde
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
  
 \(N 1 \- N 0\)\/\(\(D 1 \- D 0\)\/F\)