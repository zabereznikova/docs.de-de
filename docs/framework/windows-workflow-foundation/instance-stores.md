---
title: Instanzspeicher
ms.date: 03/30/2017
ms.assetid: f2629668-0923-4987-b943-67477131c1e0
ms.openlocfilehash: 69b50942c36406bd29147d243e0501b8048d56dc
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802556"
---
# <a name="instance-stores"></a>Instanzspeicher
Ein Instanzspeicher ist ein logischer Container für Instanzen. An diesem Ort werden die Instanzdaten und die Metadaten gespeichert. Ein Instanzspeicher bedeutet keine dedizierte physische Speicherung. Ein Instanzspeicher kann permanente Informationen in einer SQL Server-Datenbank oder nicht permanente Zustandsinformationen in einem Arbeitsspeicher enthalten. Im Lieferumfang von [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ist der SQL-Workflowinstanzspeicher enthalten. Dabei handelt es sich um eine konkrete Implementierung eines Instanzspeichers, der Workflows das Beibehalten von Instanzdaten und Metadaten in einer SQL Server 2005- oder SQL Server 2008-Datenbank ermöglicht. Außerdem bietet Windows Server AppFabric auch eine konkrete Implementierung eines Instanzspeichers. Weitere Informationen finden Sie unter [Windows Server App Fabric-Instanzspeicher, Abfrage und Steuerelement Anbieter](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10)).  
  
 Die Persistenz-API ist die Schnittstelle zwischen einem Host und einem Instanzspeicher, die dem Host das Senden von Befehlsanforderungen (z. B. <xref:System.Activities.DurableInstancing.LoadWorkflowCommand> und <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>) an den Instanzspeicher ermöglicht. Die konkrete Implementierung dieser API wird als Persistenzanbieter bezeichnet. Der Persistenzanbieter empfängt Anforderungen von einem Host und ändert den Instanzspeicher.  
  
 Hosts und Instanzspeicher sind austauschbar, sodass ein Host mit vielen Instanzspeichern und ein Instanzspeicher auch mit vielen Hosts verwendet werden kann. Ein Instanzspeicher ist normalerweise für die Verwendungsmuster eines bestimmten Hosts optimiert, obwohl für den Instanzspeicher und den Host möglicherweise voneinander unabhängige Lebenszyklen gelten. Beispielsweise sind **Workflow Service Host** und **SqlWorkflowInstanceStore** für eine gute Zusammenarbeit konzipiert. Sie können einen eigenen Instanzspeicher zum Speichern von Daten und Metadaten von Workflow Dienst Instanzen erstellen und diesen Instanzspeicher mit dem Workflow Service **Host**verwenden. Beispielsweise können Sie ein OracleWorkflowInstanceStore-Objekt erstellen, bei dem Workflows Informationen in eine Oracle-Datenbank beibehalten können, anstatt diese in einer SQL Server-Datenbank zu speichern.  
  
 Hosts werden häufig mit zusätzlicher Funktionalität erweitert, die die beibehaltenen Objekte ändert. Beispielsweise kann ein instanzpersistenzsystem einen Workflow Host, eine Erweiterung, die den Vorgang "Suspend" unterstützt, und einen SQL-Instanzspeicher aufweisen.  Der Workflowhost kann einen Standardbefehl wie Speichern oder Laden senden, um einen Workflow aus einem Instanzspeicher zu speichern oder zu laden oder um einen Workflow in einem Instanzspeicher zu speichern. Die Suspend-Erweiterung kann den Befehlen zusätzliche Semantik zum Speichern und Laden von Workflowinstanzen hinzufügen, sodass eine angehaltene Workflowinstanz nicht geladen werden kann. Der Persistenzanbieter für den SQL-Instanzspeicher versteht die Befehle zum Speichern und Laden von Workflowinstanzen und implementiert die Befehle durch das Aufrufen geeigneter gespeicherter Prozeduren, mit denen die Tabellen persistenter Objekte in einer SQL Server-Datenbank geändert werden.  
  
 Ein Host fungiert als Instanzbesitzer innerhalb eines Instanzspeichers. Ein Host kann gleichzeitig als mehr als ein Instanzbesitzer und mit mehr als einem Instanzspeicher fungieren. Der Host stellt GUIDs für Instanzschlüssel bereit, die den Instanzen zugeordnet sind. Ein Instanzschlüssel ist ein eindeutiger Alias, der eine Instanz identifiziert. Das Persistenzsystem erstellt, aktualisiert und löscht Instanzbesitzerinformationen, während es die von Hosts angeforderten Befehle ausführt.  
  
 Die folgende Liste enthält die wichtigen Schritte für die Interaktion des Hosts mit dem Instanzspeicher:  
  
1. Abrufen eines **InstanceStore** von einem Persistenzanbieter.  

2. Rufen Sie das Handle für eine-Instanz ab, indem Sie die <xref:System.Runtime.DurableInstancing.InstanceStore.CreateInstanceHandle%2A>-Methode für den **InstanceStore**aufrufen.  
  
3. Rufen Sie Befehle für das Instanzhandle auf, indem Sie die <xref:System.Runtime.DurableInstancing.InstanceStore.Execute%2A>-Methode für den **InstanceStore**aufrufen.  
  
4. Überprüfen Sie die von **InstanceStore. Execute** zurückgegebenen <xref:System.Runtime.DurableInstancing.InstanceView>, um die Ergebnisse der Befehle zu bestimmen.
