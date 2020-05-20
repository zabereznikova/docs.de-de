---
title: Übersicht über Windows-Workflow
description: In diesem Artikel werden Workflow Foundation-Workflows beschrieben, bei denen es sich um Modelle handelt, die reale Prozesse beschreiben.
ms.date: 03/30/2017
ms.assetid: fc44adbe-1412-49ae-81af-0298be44aae6
ms.openlocfilehash: ec1a00b37abe2cb842735fb98e1c113a97943758
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421474"
---
# <a name="windows-workflow-overview"></a>Übersicht über Windows-Workflow
Bei einem Workflow handelt es sich um einen Satz von elementaren Einheiten, die als ein Modell gespeichert *werden, das* einen realen Prozess beschreibt. Mit Workflows können die Reihenfolge der Ausführung sowie abhängige Beziehungen zwischen kurz- und langfristiger Arbeit beschrieben werden. Diese Arbeit durchläuft das Modell vom Anfang bis zum Ende, und Aktivitäten werden unter Umständen von Personen oder Systemfunktionen ausgeführt.  
  
## <a name="workflow-run-time-engine"></a>Workflowruntime-Engine  
 Jede ausgeführte Workflowinstanz wird von einer prozessinternen Runtime-Engine erstellt und verwaltet, mit dem der Hostprozess durch eines der folgenden Objekte interagiert:  
  
- Ein <xref:System.Activities.WorkflowInvoker>-Objekt, der den Workflow wie eine Methode aufruft.  
  
- Ein <xref:System.Activities.WorkflowApplication>-Objekt für die explizite Kontrolle über die Ausführung einer einzelnen Workflowinstanz.  
  
- Ein <xref:System.ServiceModel.WorkflowServiceHost>-Objekt für meldungsbasierte Interaktionen in Szenarien mit mehreren Instanzen.  
  
 Jede dieser Klassen umschließt die Kernaktivitätslaufzeit, die als <xref:System.Activities.ActivityInstance> dargestellt wird und für die Aktivitätsausführung zuständig ist. Es kann mehrere <xref:System.Activities.ActivityInstance>-Objekte innerhalb einer Anwendungsdomäne geben, die gleichzeitig ausgeführt werden.  
  
 Jede der vorausgehenden drei Hostinteraktionsobjekte wird aus einer Aktivitätsstruktur erstellt, die als Workflowprogramm bezeichnet wird. Mithilfe dieser Typen oder eines benutzerdefinierten Hosts, der umschließt <xref:System.Activities.ActivityInstance> , können Workflows in jedem beliebigen Windows-Prozess ausgeführt werden, einschließlich Konsolen Anwendungen, Formular basierten Anwendungen, Windows-Diensten, ASP.NET-Websites und Windows Communication Foundation (WCF)-Diensten.  
  
 ![Workflowkomponenten im Hostprozess](./media/44c79d1d-178b-4487-87ed-3e33015a3842.gif "44c79d1d-178b-4487-87ed-3e33015a3842")  
Workflowkomponenten im Hostprozess  
  
## <a name="interaction-between-workflow-components"></a>Interaktion zwischen Workflowkomponenten  
 Im folgenden Diagramm wird dargestellt, wie Workflowkomponenten miteinander interagieren.  
  
 ![Diagramm, das zeigt, wie Workflow Komponenten interagieren.](./media/overview/workflow-component-interatction.gif)  
  
 Im vorangehenden Diagramm wird die <xref:System.Activities.WorkflowInvoker.Invoke%2A>-Methode der <xref:System.Activities.WorkflowInvoker>-Klasse verwendet, um mehrere Instanzen eines Workflows aufzurufen. <xref:System.Activities.WorkflowInvoker> wird für einfache Workflows verwendet, die keine Verwaltung durch den Host benötigen. Workflows, die eine Verwaltung durch den Host erfordern (z. B. eine <xref:System.Activities.Bookmark>-Wiederaufnahme), müssen stattdessen mithilfe von <xref:System.Activities.WorkflowApplication.Run%2A> ausgeführt werden. Es ist nicht erforderlich, auf den Abschluss einer Workflowinstanz zu warten, bevor ein weiterer Workflow aufgerufen wird. Die Runtime-Engine unterstützt die Ausführung mehrerer Workflowinstanzen gleichzeitig.  Die aufgerufenen Workflows sind:  
  
- Eine <xref:System.Activities.Statements.Sequence>-Aktivität, die eine untergeordnete <xref:System.Activities.Statements.WriteLine>-Aktivität enthält. <xref:System.Activities.Variable> der übergeordneten Aktivität wird an <xref:System.Activities.InArgument> der untergeordneten Aktivität gebunden. Weitere Informationen zu Variablen, Argumenten und Bindungen finden Sie unter [Variablen und Argumente](variables-and-arguments.md).  
  
- Eine benutzerdefinierte Aktivität mit dem Namen `ReadLine`. Ein <xref:System.Activities.OutArgument> der `ReadLine`-Aktivität wird an die aufrufende <xref:System.Activities.WorkflowInvoker.Invoke%2A>-Methode zurückgegeben.  
  
- Eine benutzerdefinierte Aktivität, die von der abstrakten <xref:System.Activities.CodeActivity>-Klasse abgeleitet wird. <xref:System.Activities.CodeActivity> kann auf Laufzeitfunktionen (z. B. Nachverfolgung und Eigenschaften) mit dem <xref:System.Activities.CodeActivityContext> zugreifen, der als Parameter über die <xref:System.Activities.CodeActivity.Execute%2A>-Methode verfügbar ist. Weitere Informationen zu diesen Lauf Zeitfunktionen finden Sie unter [Workflow Verfolgung und Ablauf Verfolgung](workflow-tracking-and-tracing.md) und [Workflow Ausführungs Eigenschaften](workflow-execution-properties.md).  
  
## <a name="see-also"></a>Siehe auch

- [BizTalk Server 2006 oder WF? Auswählen des richtigen Workflow Tools für Ihr Projekt](https://docs.microsoft.com/previous-versions/dotnet/articles/cc303238(v=msdn.10))
