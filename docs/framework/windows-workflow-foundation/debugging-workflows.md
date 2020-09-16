---
title: Debuggen von Workflows
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 31c688f5f45b41f337176108486ec2074e1915a7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543835"
---
# <a name="debugging-workflows"></a>Debuggen von Workflows

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] bietet mehrere Optionen für das Debuggen ausgeführter Workflows über die Entwicklungsumgebung. Das Debugging von Workflows kann im Designer, in XAML und in Code erfolgen.

## <a name="debugging-in-the-workflow-designer"></a>Debuggen des Workflow-Designers

Haltepunkte können für Aktivitäten im Workflow-Designer festgelegt werden, indem die Aktivität hervorgehoben und <kbd>F9</kbd> oder das Kontextmenü der Aktivität gedrückt wird. Die Ausführung des Workflows wird daraufhin unterbrochen, wenn der Workflowhost im Debugmodus ausgeführt wird. In der folgenden Bildschirmabbildung wird die Ausführung des Workflows an einem Haltepunkt angehalten. Weitere Informationen finden Sie unter [Debuggen von Workflows mit dem Workflow-Designer](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).

## <a name="debugging-in-xaml"></a>Debugging in XAML

Wenn ein Workflow an einem Haltepunkt im Designer angehalten wird, kann das Debugging des Workflows auch in XAML erfolgen. Um den Ausführungs Punkt in XAML anzuzeigen, wählen Sie **XAML-Ansicht** im Workflow-Designer aus, wenn die Workflow Ausführung angehalten wird. Das Debugging kann erneut vom Designer übernommen werden, indem der Workflow aus dem Projektmappen-Explorer erneut im Designer geöffnet wird. Weitere Informationen finden Sie unter Gewusst [wie: Debuggen von XAML mit dem Workflow-Designer](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).

## <a name="debugging-in-code"></a>Debugging in Code

Um einen Haltepunkt festzulegen, klicken Sie auf den linken Rand des Code Bereichs, oder drücken Sie <kbd>F9</kbd> mit dem Cursor an der Zeile, in der Sie ihn festlegen möchten.

## <a name="attaching-to-a-workflow-process"></a>Anfügen an einen Workflowprozess

Das Debugging von Workflows unterstützt auch die Verwendung der Visual Studio-Infrastruktur zum Anfügen an einen Prozess. Dies ermöglicht es dem Workflowautor, einen Workflow zu debuggen, der in einer anderen Hostumgebung ausgeführt wird, z. B. in Internetinformationsdienste (IIS) 7.0.

## <a name="remote-debugging"></a>Remote Debugging

Das Remote Debuggen von Windows Workflow Foundation (WF) funktioniert genauso wie das Remote Debuggen für andere Visual Studio-Komponenten. Weitere Informationen zur Verwendung des Remote Debuggens finden Sie unter Gewusst [wie: Aktivieren des Remote Debuggens](/previous-versions/visualstudio/visual-studio-2010/febz73k0(v=vs.100)).

> [!NOTE]
> Wenn die Workflow Anwendung die x86-Architektur als Ziel verwendet und auf einem Computer gehostet wird, auf dem ein 64-Bit-Betriebssystem ausgeführt wird, funktioniert das Remote Debuggen nur dann, wenn Visual Studio auf dem Remote Computer installiert ist oder das Ziel für die Workflow Anwendung in eine **beliebige CPU**geändert wird.

## <a name="extending-the-workflow-debugging-service"></a>Erweitern der Debugdienste für Workflows

Der Debugdienst für Workflows ist jetzt öffentlich und kann zum Erstellen benutzerdefinierter Anwendungen wie Überwachung, Simulation und Debugging in einem erneut gehosteten Designer verwendet werden. Weitere Informationen finden Sie im Artikel <xref:System.Activities.Presentation.Debug.DebuggerService>.
