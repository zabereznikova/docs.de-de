---
title: "System.ServiceModel.Channels.PeerMaintainerActivity | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# System.ServiceModel.Channels.PeerMaintainerActivity
Das PeerMaintainer\-Modul führt einen bestimmten Vorgang \(Details innerhalb des Ablaufverfolgungsnachrichtentexts\) aus.  
  
## Beschreibung  
 Diese Ablaufverfolgung tritt während verschiedener PeerMaintainer\-Vorgänge auf.  
  
 PeerMaintainer ist eine interne Komponente von PeerNode.  Jede Minute &\#8211; oder nach 32&\#160;empfangenen Nachrichten &\#8211; wird eine LinkUtility\-Nachricht an die Nachbarn gesendet. Diese Nachricht enthält eine Statistik mit der Anzahl der ausgetauschten Nachrichten sowie mit Informationen dazu, wie viele der Nachrichten nützlich waren \(also keine Duplikate und nicht manipuliert\).  Dadurch lässt sich das Verknüpfungsprogramm eines bestimmten Nachbarn ermitteln.  Etwa alle fünf Minuten überprüft der Maintainer die Integrität der Nachbarverbindungen.  Übersteigt die Anzahl von Nachbarverbindungen die Idealmenge, werden die am wenigsten nützlichen Verbindungen entfernt.  Sind nicht genügend Verbindungen verfügbar, werden vom Maintainer neue Verbindungen eingerichtet.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)