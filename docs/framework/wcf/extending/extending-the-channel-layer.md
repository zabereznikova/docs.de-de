---
title: "Erweitern der Kanalschicht | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Erweitern von Kanälen [WCF]"
ms.assetid: 4238db74-2fb6-4dc8-a326-f58527230810
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Erweitern der Kanalschicht
Die Kanalschicht ist für den Nachrichtenaustausch zwischen Clients und Diensten verantwortlich.Durch Kanalerweiterungen können neue Protokollfunktionen implementiert werden, wie beispielsweise Sicherheits\- oder Transportfunktionen. So kann zum Beispiel ein neuer Netzwerktransport für die Übermittlung von SOAP\-Nachrichten implementiert werden.  
  
## In diesem Abschnitt  
 [Übersicht über das Kanalmodell](../../../../docs/framework/wcf/extending/channel-model-overview.md)  
 Gibt einen Überblick über Kanäle, die von ihnen bereitgestellten Funktionen und ihre Funktionsweise in Dienst\- und Clientanwendungen.  
  
 [Entwickeln von Kanälen](../../../../docs/framework/wcf/extending/developing-channels.md)  
 Beschreibt detailliert, welche Rolle die einzelnen Kanalinfrastrukturtypen spielen, wie das Statusmodul und der Statuslebenszyklus funktionieren, wie Ausnahmen und Fehler verarbeitet werden, wie die Unterstützung von Metadaten implementiert wird und wie Kanäle mit Nachrichtenencodern zusammenarbeiten.  
  
 [Benutzerdefinierte Encoder](../../../../docs/framework/wcf/extending/custom-encoders.md)  
 Beschreibt die Rolle der Nachrichtenencoder in Kanälen und ihre Erstellung.  
  
 [Benutzerdefinierte Stream\-Upgrades](../../../../docs/framework/wcf/extending/custom-stream-upgrades.md)  
 Beschreibt, wie Datenströme aktualisiert werden, die von datenstromorientierten Transporten bereitgestellt werden.