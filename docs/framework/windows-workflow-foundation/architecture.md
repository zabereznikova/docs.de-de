---
title: Architektur von Windows-Workflows
ms.date: 03/30/2017
ms.assetid: 1d4c6495-d64a-46d0-896a-3a01fac90aa9
ms.openlocfilehash: 5d6e1ead9184bfb61eb466389671ca2e74264ae3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945924"
---
# <a name="windows-workflow-architecture"></a>Architektur von Windows-Workflows
Windows Workflow Foundation (WF), löst die Abstraktionsebene zum Entwickeln von interaktiven lang andauernden Anwendungen aus. Arbeitseinheiten werden als Aktivitäten gekapselt. Aktivitäten werden in einer Umgebung ausgeführt, die Funktionen für Flusssteuerung, Ausnahmebehandlung, Fehlerweitergabe, Persistenz von Zustandsdaten, Laden und Entladen von aktuell verarbeiteten Workflows aus dem Arbeitsspeicher, Nachverfolgung und Transaktionsfluss bietet.  
  
## <a name="activity-architecture"></a>Aktivitätsarchitektur  
 Aktivitäten werden als CLR-Typen entwickelt, die von <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> oder <xref:System.Activities.NativeActivity> abgeleitet werden oder aber von den entsprechenden Varianten, die einen Wert zurückgeben: <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601> oder <xref:System.Activities.NativeActivity%601>. Das Entwickeln von Aktivitäten, die von <xref:System.Activities.Activity> abgeleitet werden, ermöglicht dem Benutzer, bereits vorhandene Aktivitäten zusammenzustellen, um so schnell Arbeitseinheiten zu erstellen, die in der Workflowumgebung ausgeführt werden. <xref:System.Activities.CodeActivity> hingegen ermöglicht das Schreiben von Ausführungslogik in verwaltetem Code mit <xref:System.Activities.CodeActivityContext>, hauptsächlich für den Zugriff auf Aktivitätsargumente. <xref:System.Activities.AsyncCodeActivity> ist mit <xref:System.Activities.CodeActivity> vergleichbar, außer dass sie verwendet werden kann, um asynchrone Aufgaben zu implementieren. Das Entwickeln von Aktivitäten, die von <xref:System.Activities.NativeActivity> abgeleitet werden, ermöglicht Benutzern, über den <xref:System.Activities.NativeActivityContext> auf die Laufzeit zuzugreifen, um Funktionen wie die Planung untergeordneter Elemente, das Erstellen von Lesezeichen, das Aufrufen asynchroner Arbeit, das Registrieren von Transaktionen und viele mehr zu nutzen.  
  
 Das Entwickeln von Aktivitäten, die von <xref:System.Activities.Activity> abgeleitet werden, ist deklarativ. Diese Aktivitäten können in XAML erstellt werden. Im folgenden Beispiel wird eine Aktivität mit dem Namen `Prompt` erstellt, wobei andere Aktivitäten für den Ausführungstext verwendet werden.  
  
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
  
## <a name="activity-context"></a>Aktivitätskontext  
 Das <xref:System.Activities.ActivityContext>-Objekt ist für den Ersteller der Aktivität die Schnittstelle zur Workflowlaufzeit und bietet Zugriff auf die zahlreichen Funktionen der Laufzeit. Im folgenden Beispiel wird eine Aktivität definiert, die mit dem Ausführungskontext ein Lesezeichen erstellt (der Mechanismus, der es einer Aktivität ermöglicht, in der Ausführung einen Fortsetzungspunkt zu registrieren, sodass die Fortsetzung erfolgt, wenn ein Host Daten an die Aktivität übergibt).  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
## <a name="activity-life-cycle"></a>Aktivitätslebenszyklus  
 Eine Instanz einer Aktivität startet mit dem <xref:System.Activities.ActivityInstanceState.Executing>-Zustand. Wenn keine Ausnahmen auftreten, verbleibt die Instanz in diesem Zustand, bis die Ausführung aller untergeordneten Aktivitäten beendet wurde und alle weiteren ausstehenden Arbeitsvorgänge (z. B. <xref:System.Activities.Bookmark>-Objekte) abgeschlossen sind. An diesem Punkt geht die Instanz in den <xref:System.Activities.ActivityInstanceState.Closed>-Zustand über. Das übergeordnete Element einer Aktivitätsinstanz kann den Abbruch eines untergeordneten Elements anfordern. Wenn das untergeordnete Element abgebrochen werden kann, wird es mit dem <xref:System.Activities.ActivityInstanceState.Canceled>-Zustand abgeschlossen. Wenn während der Ausführung eine Ausnahme ausgelöst wird, versetzt die Laufzeit die Aktivität in den <xref:System.Activities.ActivityInstanceState.Faulted>-Zustand und gibt die Ausnahme an die Kette übergeordneter Aktivitäten weiter. Dies sind die drei Abschlusszustände einer Aktivität:  
  
- **Geschlossen:** Die Aktivität hat alle Arbeitsvorgänge abgeschlossen und wurde beendet.  
  
- **Abgebrochen:** Die Aktivität wurde ordnungsgemäß seine Arbeit abgebrochen und beendet. Für die Arbeit wird kein expliziter Rollback ausgeführt, wenn dieser Zustand eintritt.  
  
- **Fehler:** Die Aktivität hat einen Fehler festgestellt und wurde ohne Abschließen der Arbeit beendet.  
  
 Beim dauerhaften Speichern und Entladen verbleiben Aktivitäten im <xref:System.Activities.ActivityInstanceState.Executing>-Zustand.
