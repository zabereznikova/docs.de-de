---
title: "Automatische IPv6-Konfiguration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 581c1d21-1013-43a3-bf3e-2d9ead62b79c
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# Automatische IPv6-Konfiguration
Ein wichtiges Ziel für IPv6 ist, Knoten Plug & Wiedergabe zu unterstützen.  Das heißt, sollte es möglich sein, einen Knoten in einem Netzwerk IPv6 verbinden und ihn ohne menschliche Intervention automatisch konfigurieren zu können.  
  
## Typ der automatische Konfiguration  
 IPv6 unterstützt die folgenden Typen von automatischer Konfiguration:  
  
-   **Zustandsbehaftete automatische Konfiguration**.  Diese Konfiguration erfordert eine bestimmte Ebene der menschliche Intervention, da er Dynamic Host Configuration\-Protokoll für Server IPv6 \(DHCPv6\) für die Installation und Verwaltung der Knoten erfordert.  Der Server DHCPv6 verwaltet eine Liste der Knoten, an die sie Konfigurationsinformationen bereitstellt.  Es wird auch Zustandsinformationen beibehalten, sodass der Server weiß, wie lange jede Adresse verwendet wird und wann sie für die erneute Zuweisung möglicherweise verfügbar ist.  
  
-   **Zustandslose automatische Konfiguration**.  Diese Konfiguration ist für kleine Organisationen und Einzelpersonen geeignet.  In diesem Fall bestimmt jeder Host die Adressen vom Inhalt der empfangenen Routerankündigungen.  Verwenden des Standards IEEE EUI\-64, um das Netzwerk ID\-Teils der Adresse zu definieren, ist es sinnvoll, die Eindeutigkeit der Hostadressen auf den Link.  
  
 Unabhängig davon, wie die Adresse bestimmt wird, muss der Knoten überprüfen, ob die mögliche Adresse des lokalen Link eindeutig ist.  Dies geschieht, indem eine Nachbaranfragenmeldung zur möglichen Adresse sendet.  Wenn der Knoten eine Antwort empfängt, weiß er, dass die Adresse bereits verwendet wird und eine andere Adresse bestimmen muss.  
  
## Mobilität IPv6  
 Die Anhäufung von mobilen Geräten verfügt über eine neue Anforderung eingeführt: Ein Gerät muss in der Lage sein, Speicherorte auf dem Internet IPv6 beliebig ändern und vorhandene Verbindungen weiterhin beizubehalten.  Um diese Funktion bereitzustellen, wird ein mobiler Knoten eine Privatadresse zugewiesen an der er immer erreicht werden kann.  Wenn der mobile Knoten zu Hause liegt, wird er mit den Ausgangslink an und verwendet eine Privatadresse.  Wenn der mobile Knoten vom Haus, ein Hauptagent ist, der normalerweise ein Router, Relaymeldungen zwischen dem mobilen Knoten und Knoten ist, die es ist.  
  
## Siehe auch  
 [Internetprotokoll Version 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)