---
title: "System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
Die Empfangsrate eingehender Nachrichten ist zu hoch.  
  
## Beschreibung  
 Diese Ablaufverfolgung tritt auf, wenn versucht wird, eingehende Nachrichten zu verarbeiten.  Eine Nachricht konnte nicht an einen bestimmten Nachbarn weitergeleitet werden, da das festgelegte Kontingent für diesen Nachbarn überschritten wurde.  Dies tritt auf, wenn ein nicht reagierender Nachbar das Backlog der anstehenden Nachrichten für diesen Nachbarn nicht löst.  
  
## Problembehandlung  
 Reduzieren Sie die Rate, mit der Nachrichten innerhalb des Mesh gesendet werden.  
  
## Siehe auch  
 [Ablaufverfolgung](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Verwaltung und Diagnose](../../../../../docs/framework/wcf/diagnostics/index.md)