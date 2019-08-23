---
title: Debuggen von Workflows
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 12b85260f8eab87fc9b98a99ca1192fd307313d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915413"
---
# <a name="debugging-workflows"></a>Debuggen von Workflows
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] bietet mehrere Optionen für das Debuggen ausgeführter Workflows über die Entwicklungsumgebung. Das Debugging von Workflows kann im Designer, in XAML und in Code erfolgen.  
  
## <a name="debugging-in-the-workflow-designer"></a>Debuggen des Workflow-Designers  
 Haltepunkte können für Aktivitäten im Workflow-Designer festgelegt werden, indem die Aktivität hervorgehoben und **F9** oder das Kontextmenü der Aktivität gedrückt wird. Die Ausführung des Workflows wird daraufhin unterbrochen, wenn der Workflowhost im Debugmodus ausgeführt wird. In der folgenden Bildschirmabbildung wird die Ausführung des Workflows an einem Haltepunkt angehalten. Weitere Informationen finden Sie unter [Debuggen von Workflows mit dem Workflow-Designer](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).  
  
## <a name="debugging-in-xaml"></a>Debugging in XAML  
 Wenn ein Workflow an einem Haltepunkt im Designer angehalten wird, kann das Debugging des Workflows auch in XAML erfolgen. Um den Ausführungs Punkt in XAML anzuzeigen, wählen Sie **XAML-Ansicht** im Workflow-Designer aus, wenn die Workflow Ausführung angehalten wird. Das Debugging kann erneut vom Designer übernommen werden, indem der Workflow aus dem Projektmappen-Explorer erneut im Designer geöffnet wird. Weitere Informationen finden Sie unter [Vorgehensweise: Debuggen Sie XAML](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer)mit dem Workflow-Designer.  
  
## <a name="debugging-in-code"></a>Debugging in Code  
 Codehaltepunkte können in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] auf die gleiche Weise verwendet werden wie in anderen imperativen Anwendungen. Klicken Sie auf den linken Rand des Code Bereichs, um einen Code Breakpoint zu erstellen, oder drücken Sie **F9** , um einen Haltepunkt an der Cursorposition zu platzieren.  
  
## <a name="attaching-to-a-workflow-process"></a>Anfügen an einen Workflowprozess  
 Das Debugging von Workflows unterstützt auch die Verwendung der Visual Studio-Infrastruktur zum Anfügen an einen Prozess. Dies ermöglicht es dem Workflowautor, einen Workflow zu debuggen, der in einer anderen Hostumgebung ausgeführt wird, z. B. in Internetinformationsdienste (IIS) 7.0.  
  
## <a name="remote-debugging"></a>Remote Debugging  
 Das Remote Debuggen von Windows Workflow Foundation (WF) funktioniert genauso wie das Remote Debuggen für andere Visual Studio-Komponenten. Weitere Informationen zur Verwendung des Remote Debuggens finden [Sie unter Gewusst wie: Aktivieren Sie das](https://go.microsoft.com/fwlink/?LinkId=196257)Remote Debugging.  
  
> [!NOTE]
> Wenn die Workflow Anwendung die x86-Architektur als Ziel verwendet und auf einem Computer gehostet wird, auf dem ein 64-Bit-Betriebssystem ausgeführt wird, funktioniert das Remote Debuggen nur dann, wenn Visual Studio auf dem Remote Computer installiert ist oder das Ziel für die Workflow Anwendung in geändert wird. **Beliebige CPU**.  
  
## <a name="extending-the-workflow-debugging-service"></a>Erweitern der Debugdienste für Workflows  
 Der Debugdienst für Workflows ist jetzt öffentlich und kann zum Erstellen benutzerdefinierter Anwendungen wie Überwachung, Simulation und Debugging in einem erneut gehosteten Designer verwendet werden. Weitere Informationen finden Sie im Thema <xref:System.Activities.Presentation.Debug.DebuggerService>.
