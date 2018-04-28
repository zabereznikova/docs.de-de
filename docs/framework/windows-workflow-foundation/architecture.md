---
title: Architektur von Windows-Workflows
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d4c6495-d64a-46d0-896a-3a01fac90aa9
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a3a59369738ada0c6b770d272afa9c6c79c2ce01
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="windows-workflow-architecture"></a><span data-ttu-id="addad-102">Architektur von Windows-Workflows</span><span class="sxs-lookup"><span data-stu-id="addad-102">Windows Workflow Architecture</span></span>
<span data-ttu-id="addad-103">Windows Workflow Foundation (WF), löst die Abstraktionsebene zum Entwickeln von interaktiven Anwendungen mit langer aus.</span><span class="sxs-lookup"><span data-stu-id="addad-103">Windows Workflow Foundation (WF) raises the abstraction level for developing interactive long-running applications.</span></span> <span data-ttu-id="addad-104">Arbeitseinheiten werden als Aktivitäten gekapselt.</span><span class="sxs-lookup"><span data-stu-id="addad-104">Units of work are encapsulated as activities.</span></span> <span data-ttu-id="addad-105">Aktivitäten werden in einer Umgebung ausgeführt, die Funktionen für Flusssteuerung, Ausnahmebehandlung, Fehlerweitergabe, Persistenz von Zustandsdaten, Laden und Entladen von aktuell verarbeiteten Workflows aus dem Arbeitsspeicher, Nachverfolgung und Transaktionsfluss bietet.</span><span class="sxs-lookup"><span data-stu-id="addad-105">Activities run in an environment that provides facilities for flow control, exception handling, fault propagation, persistence of state data, loading and unloading of in-progress workflows from memory, tracking, and transaction flow.</span></span>  
  
## <a name="activity-architecture"></a><span data-ttu-id="addad-106">Aktivitätsarchitektur</span><span class="sxs-lookup"><span data-stu-id="addad-106">Activity Architecture</span></span>  
 <span data-ttu-id="addad-107">Aktivitäten werden als CLR-Typen entwickelt, die von <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> oder <xref:System.Activities.NativeActivity> abgeleitet werden oder aber von den entsprechenden Varianten, die einen Wert zurückgeben: <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601> oder <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="addad-107">Activities are developed as CLR types that derive from either <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>, or their variants that return a value, <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601>, or <xref:System.Activities.NativeActivity%601>.</span></span> <span data-ttu-id="addad-108">Das Entwickeln von Aktivitäten, die von <xref:System.Activities.Activity> abgeleitet werden, ermöglicht dem Benutzer, bereits vorhandene Aktivitäten zusammenzustellen, um so schnell Arbeitseinheiten zu erstellen, die in der Workflowumgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="addad-108">Developing activities that derive from <xref:System.Activities.Activity> allows the user to assemble pre-existing activities to quickly create units of work that execute in the workflow environment.</span></span> <span data-ttu-id="addad-109"><xref:System.Activities.CodeActivity> hingegen ermöglicht das Schreiben von Ausführungslogik in verwaltetem Code mit <xref:System.Activities.CodeActivityContext>, hauptsächlich für den Zugriff auf Aktivitätsargumente.</span><span class="sxs-lookup"><span data-stu-id="addad-109"><xref:System.Activities.CodeActivity>, on the other hand, enables execution logic to be authored in managed code using <xref:System.Activities.CodeActivityContext> primarily for access to activity arguments.</span></span> <span data-ttu-id="addad-110"><xref:System.Activities.AsyncCodeActivity> ist mit <xref:System.Activities.CodeActivity> vergleichbar, außer dass sie verwendet werden kann, um asynchrone Aufgaben zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="addad-110"><xref:System.Activities.AsyncCodeActivity> is similar to <xref:System.Activities.CodeActivity> except that it can be used to implement asynchronous tasks.</span></span> <span data-ttu-id="addad-111">Das Entwickeln von Aktivitäten, die von <xref:System.Activities.NativeActivity> abgeleitet werden, ermöglicht Benutzern, über den <xref:System.Activities.NativeActivityContext> auf die Laufzeit zuzugreifen, um Funktionen wie die Planung untergeordneter Elemente, das Erstellen von Lesezeichen, das Aufrufen asynchroner Arbeit, das Registrieren von Transaktionen und viele mehr zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="addad-111">Developing activities that derive from <xref:System.Activities.NativeActivity> allows users to access the runtime through the <xref:System.Activities.NativeActivityContext> for functionality like scheduling children, creating bookmarks, invoking asynchronous work, registering transactions, and more.</span></span>  
  
 <span data-ttu-id="addad-112">Das Entwickeln von Aktivitäten, die von <xref:System.Activities.Activity> abgeleitet werden, ist deklarativ. Diese Aktivitäten können in XAML erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="addad-112">Authoring activities that derive from <xref:System.Activities.Activity> is declarative and these activities can be authored in XAML.</span></span> <span data-ttu-id="addad-113">Im folgenden Beispiel wird eine Aktivität mit dem Namen `Prompt` erstellt, wobei andere Aktivitäten für den Ausführungstext verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="addad-113">In the following example, an activity called `Prompt` is created using other activities for the execution body.</span></span>  
  
```xml  
<Activity x:Class='Prompt'  
  xmlns:x='http://schemas.microsoft.com/winfx/2006/xaml'  
    xmlns:z='http://schemas.microsoft.com/netfx/2008/xaml/schema'  
xmlns:my='clr-namespace:XAMLActivityDefinition;assembly=XAMLActivityDefinition'  
xmlns:s="clr-namespace:System;assembly=mscorlib"  
xmlns="http://schemas.microsoft.com/2009/workflow">  
<z:SchemaType.Members>  
    <z:SchemaType.SchemaProperty Name='Text' Type=' InArgument(s:String)' />  
  <z:SchemaType.SchemaProperty Name='Response' Type='OutArgument(s:String)' />  
</z:SchemaType.Members>  
  <Sequence>  
    <my:WriteLine Text='[Text]' />  
    <my:ReadLine BookmarkName='r1' Result='[Response]' />  
  </Sequence>  
</Activity>  
```  
  
## <a name="activity-context"></a><span data-ttu-id="addad-114">Aktivitätskontext</span><span class="sxs-lookup"><span data-stu-id="addad-114">Activity Context</span></span>  
 <span data-ttu-id="addad-115">Das <xref:System.Activities.ActivityContext>-Objekt ist für den Ersteller der Aktivität die Schnittstelle zur Workflowlaufzeit und bietet Zugriff auf die zahlreichen Funktionen der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="addad-115">The <xref:System.Activities.ActivityContext> is the activity author's interface to the workflow runtime and provides access to the runtime's wealth of features.</span></span> <span data-ttu-id="addad-116">Im folgenden Beispiel wird eine Aktivität definiert, die mit dem Ausführungskontext ein Lesezeichen erstellt (der Mechanismus, der es einer Aktivität ermöglicht, in der Ausführung einen Fortsetzungspunkt zu registrieren, sodass die Fortsetzung erfolgt, wenn ein Host Daten an die Aktivität übergibt).</span><span class="sxs-lookup"><span data-stu-id="addad-116">In the following example, an activity is defined that uses the execution context to create a bookmark (the mechanism that allows an activity to register a continuation point in its execution that can be resumed by a host passing data into the activity).</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
## <a name="activity-life-cycle"></a><span data-ttu-id="addad-117">Aktivitätslebenszyklus</span><span class="sxs-lookup"><span data-stu-id="addad-117">Activity Life Cycle</span></span>  
 <span data-ttu-id="addad-118">Eine Instanz einer Aktivität startet mit dem <xref:System.Activities.ActivityInstanceState.Executing>-Zustand.</span><span class="sxs-lookup"><span data-stu-id="addad-118">An instance of an activity starts out in the <xref:System.Activities.ActivityInstanceState.Executing> state.</span></span> <span data-ttu-id="addad-119">Wenn keine Ausnahmen auftreten, verbleibt die Instanz in diesem Zustand, bis die Ausführung aller untergeordneten Aktivitäten beendet wurde und alle weiteren ausstehenden Arbeitsvorgänge (z. B. <xref:System.Activities.Bookmark>-Objekte) abgeschlossen sind. An diesem Punkt geht die Instanz in den <xref:System.Activities.ActivityInstanceState.Closed>-Zustand über.</span><span class="sxs-lookup"><span data-stu-id="addad-119">Unless exceptions are encountered, it remains in this state until all child activities are finished executing and any other pending work (<xref:System.Activities.Bookmark> objects, for instance) is completed, at which point it transitions to the <xref:System.Activities.ActivityInstanceState.Closed> state.</span></span> <span data-ttu-id="addad-120">Das übergeordnete Element einer Aktivitätsinstanz kann den Abbruch eines untergeordneten Elements anfordern. Wenn das untergeordnete Element abgebrochen werden kann, wird es mit dem <xref:System.Activities.ActivityInstanceState.Canceled>-Zustand abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="addad-120">The parent of an activity instance can request a child to cancel; if the child is able to be canceled it completes in the <xref:System.Activities.ActivityInstanceState.Canceled> state.</span></span> <span data-ttu-id="addad-121">Wenn während der Ausführung eine Ausnahme ausgelöst wird, versetzt die Laufzeit die Aktivität in den <xref:System.Activities.ActivityInstanceState.Faulted>-Zustand und gibt die Ausnahme an die Kette übergeordneter Aktivitäten weiter.</span><span class="sxs-lookup"><span data-stu-id="addad-121">If an exception is thrown during execution, the runtime puts the activity into the <xref:System.Activities.ActivityInstanceState.Faulted> state and propagates the exception up the parent chain of activities.</span></span> <span data-ttu-id="addad-122">Dies sind die drei Abschlusszustände einer Aktivität:</span><span class="sxs-lookup"><span data-stu-id="addad-122">Following are the three completion states of an activity:</span></span>  
  
-   <span data-ttu-id="addad-123">**Geschlossen:** die Aktivität hat alle Arbeitsvorgänge abgeschlossen und wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="addad-123">**Closed:** The activity has completed its work and exited.</span></span>  
  
-   <span data-ttu-id="addad-124">**Abgebrochen:** und die Aktivität wurde ordnungsgemäß abgebrochen seine Arbeit beendet.</span><span class="sxs-lookup"><span data-stu-id="addad-124">**Canceled:** The activity has gracefully abandoned its work and exited.</span></span> <span data-ttu-id="addad-125">Für die Arbeit wird kein expliziter Rollback ausgeführt, wenn dieser Zustand eintritt.</span><span class="sxs-lookup"><span data-stu-id="addad-125">Work is not explicitly rolled back when this state is entered.</span></span>  
  
-   <span data-ttu-id="addad-126">**Faulted:** ein Fehler aufgetreten, und die Aktivität wurde ohne Abschließen der Arbeit beendet.</span><span class="sxs-lookup"><span data-stu-id="addad-126">**Faulted:** The activity has encountered an error and has exited without completing its work.</span></span>  
  
 <span data-ttu-id="addad-127">Beim dauerhaften Speichern und Entladen verbleiben Aktivitäten im <xref:System.Activities.ActivityInstanceState.Executing>-Zustand.</span><span class="sxs-lookup"><span data-stu-id="addad-127">Activities remain in the <xref:System.Activities.ActivityInstanceState.Executing> state when they are persisted or unloaded.</span></span>
