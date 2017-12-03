---
title: Instanzspeicher
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2629668-0923-4987-b943-67477131c1e0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c794c6e20b479ea4686caba29704f8851d108432
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="instance-stores"></a>Instanzspeicher
Ein Instanzspeicher ist ein logischer Container für Instanzen. An diesem Ort werden die Instanzdaten und die Metadaten gespeichert. Ein Instanzspeicher bedeutet keine dedizierte physische Speicherung. Ein Instanzspeicher kann permanente Informationen in einer SQL Server-Datenbank oder nicht permanente Zustandsinformationen in einem Arbeitsspeicher enthalten. Im Lieferumfang von [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ist der SQL-Workflowinstanzspeicher enthalten. Dabei handelt es sich um eine konkrete Implementierung eines Instanzspeichers, der Workflows das Beibehalten von Instanzdaten und Metadaten in einer SQL Server 2005- oder SQL Server 2008-Datenbank ermöglicht. Außerdem bietet Windows Server AppFabric auch eine konkrete Implementierung eines Instanzspeichers. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Windows Server AppFabric-Instanzspeicher, Abfrage und Anbietern der Quellcodeverwaltung](http://go.microsoft.com/fwlink/?LinkID=201201&clcid=0x409).  
  
 Die Persistenz-API ist die Schnittstelle zwischen einem Host und einem Instanzspeicher, die dem Host das Senden von Befehlsanforderungen (z. B. <xref:System.Activities.DurableInstancing.LoadWorkflowCommand> und <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>) an den Instanzspeicher ermöglicht. Die konkrete Implementierung dieser API wird als Persistenzanbieter bezeichnet. Der Persistenzanbieter empfängt Anforderungen von einem Host und ändert den Instanzspeicher.  
  
 Hosts und Instanzspeicher sind austauschbar, sodass ein Host mit vielen Instanzspeichern und ein Instanzspeicher auch mit vielen Hosts verwendet werden kann. Ein Instanzspeicher ist normalerweise für die Verwendungsmuster eines bestimmten Hosts optimiert, obwohl für den Instanzspeicher und den Host möglicherweise voneinander unabhängige Lebenszyklen gelten. Z. B. die **WorkflowServiceHost** und **SqlWorkflowInstanceStore** gut miteinander funktionieren. Sie können einen eigenen Instanzspeicher zum Beibehalten von Daten und Metadaten von workflowdienstinstanzen und diesen Instanzspeicher mit Erstellen der **WorkflowServiceHost**. Beispielsweise können Sie ein OracleWorkflowInstanceStore-Objekt erstellen, bei dem Workflows Informationen in eine Oracle-Datenbank beibehalten können, anstatt diese in einer SQL Server-Datenbank zu speichern.  
  
 Hosts werden häufig mit zusätzlicher Funktionalität erweitert, die die beibehaltenen Objekte ändert. Ein instanzpersistenzsystem kann z. B. einen Workflowhost, eine Erweiterung verfügen, die den "Suspend"-Vorgang und einen SQL-Instanzspeicher unterstützt.  Der Workflowhost kann einen Standardbefehl wie Speichern oder Laden senden, um einen Workflow aus einem Instanzspeicher zu speichern oder zu laden oder um einen Workflow in einem Instanzspeicher zu speichern. Die Suspend-Erweiterung kann den Befehlen zusätzliche Semantik zum Speichern und Laden von Workflowinstanzen hinzufügen, sodass eine angehaltene Workflowinstanz nicht geladen werden kann. Der Persistenzanbieter für den SQL-Instanzspeicher versteht die Befehle zum Speichern und Laden von Workflowinstanzen und implementiert die Befehle durch das Aufrufen geeigneter gespeicherter Prozeduren, mit denen die Tabellen persistenter Objekte in einer SQL Server-Datenbank geändert werden.  
  
 Ein Host fungiert als Instanzbesitzer innerhalb eines Instanzspeichers. Ein Host kann gleichzeitig als mehr als ein Instanzbesitzer und mit mehr als einem Instanzspeicher fungieren. Der Host stellt GUIDs für Instanzschlüssel bereit, die den Instanzen zugeordnet sind. Ein Instanzschlüssel ist ein eindeutiger Alias, der eine Instanz identifiziert. Das Persistenzsystem erstellt, aktualisiert und löscht Instanzbesitzerinformationen, während es die von Hosts angeforderten Befehle ausführt.  
  
 Die folgende Liste enthält die wichtigen Schritte für die Interaktion des Hosts mit dem Instanzspeicher:  
  
1.  Abrufen einer **InstanceStore** von Persistenz-Provider.  

2.  Das Handle für eine Instanz zu erhalten, durch Aufrufen der <xref:System.Runtime.DurableInstancing.InstanceStore.CreateInstanceHandle%2A> Methode für die **InstanceStore**.  
  
3.  Aufrufen von Befehlen für den Instanzhandle durch Aufrufen der <xref:System.Runtime.DurableInstancing.InstanceStore.Execute%2A> Methode für die **InstanceStore**.  
  
4.  Überprüfen Sie die <xref:System.Runtime.DurableInstancing.InstanceView> zurückgegebenes **InstanceStore.Execute** um die Ergebnisse der Befehle zu ermitteln.
