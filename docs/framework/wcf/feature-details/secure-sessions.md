---
title: "Sichere Sitzungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# Sichere Sitzungen
Eine Funktion von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sind zuverlässige Sitzungen, die garantieren, dass Meldungen in der Reihenfolge empfangen werden, in der sie gesendet wurden.Die Themen in diesem Abschnitt erläutern die Sicherheitsaspekte, die bei der Erstellung einer zuverlässigen Sitzung beachtet werden sollten.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu zuverlässigen Sitzungen finden Sie unter [Verwenden von Sitzungen](../../../../docs/framework/wcf/using-sessions.md).  
  
> [!NOTE]
>  Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne Token für den Sicherheitszustandskontext \(SCT\).Wenn Token für den Sicherheitszustandskontext \(SCTs\) mit einem Identitätswechsel verwendet werden, wird ein <xref:System.InvalidOperationException> ausgelöst.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## In diesem Abschnitt  
  
|||  
|-|-|  
|[Sichere Unterhaltungen und sichere Sitzungen.](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|Sichere Konversationen und sichere Sitzungen werden synonym verwendet.In diesem Thema wird erläutert, wie eine sichere Konversation funktioniert und wann und warum das Muster verwendet wird.|  
|[Vorgehensweise: Erstellen einer sicheren Sitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|Stellt exemplarisch die Grundlagen der Erstellung einer sicheren Sitzung vor.|  
|[Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|Stellt exemplarisch die Schritte der Erstellung einer Webfarm vor, die den Zustand und Sitzungen mit Clients beibehält.|  
|[Sicherheitsüberlegungen für Sicherheitssitzungen](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|Beschreibt besondere Überlegungen für sichere Sitzungen.|  
  
## Referenz  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## Verwandte Abschnitte  
 [Sitzungen, Instanziierung und Parallelität](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [Entwerfen und Implementieren von Diensten](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## Siehe auch  
 [Vorgehensweise: Aktivieren der Nachrichtenreplay\-Erkennung](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)   
 [Wiederholungsangriffe](../../../../docs/framework/wcf/feature-details/replay-attacks.md)   
 [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)