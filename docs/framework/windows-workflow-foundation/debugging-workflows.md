---
title: Debuggen von Workflows
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 17cee1f1b509e777edd3f08c55d473d768b19b55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945872"
---
# <a name="debugging-workflows"></a>Debuggen von Workflows
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] bietet mehrere Optionen für das Debuggen ausgeführter Workflows über die Entwicklungsumgebung. Das Debugging von Workflows kann im Designer, in XAML und in Code erfolgen.  
  
## <a name="debugging-in-the-workflow-designer"></a>Debuggen des Workflow-Designers  
 Haltepunkte können für die Aktivitäten im Workflow-Designer festgelegt werden, indem Sie entweder die Aktivität markiert, und drücken **F9** oder mithilfe der Aktivität Kontextmenü. Die Ausführung des Workflows wird daraufhin unterbrochen, wenn der Workflowhost im Debugmodus ausgeführt wird. In der folgenden Bildschirmabbildung wird die Ausführung des Workflows an einem Haltepunkt angehalten. Weitere Informationen finden Sie unter [Debuggen von Workflows mit Workflow-Designer](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).  
  
## <a name="debugging-in-xaml"></a>Debugging in XAML  
 Wenn ein Workflow an einem Haltepunkt im Designer angehalten wird, kann das Debugging des Workflows auch in XAML erfolgen. Wählen Sie zum Anzeigen des Ausführungspunkts in XAML **XAML-Ansicht** im Workflow-Designer bei Ausführung des Workflows angehalten wird. Das Debugging kann erneut vom Designer übernommen werden, indem der Workflow aus dem Projektmappen-Explorer erneut im Designer geöffnet wird. Weitere Informationen finden Sie unter [Vorgehensweise: Debuggen von XAML mit dem Workflowdesigner](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).  
  
## <a name="debugging-in-code"></a>Debugging in Code  
 Codehaltepunkte können in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] auf die gleiche Weise verwendet werden wie in anderen imperativen Anwendungen. Klicken Sie auf den linken Rand des Bereichs Code, um einen codehaltepunkt zu erstellen, oder drücken Sie **F9** um einen Haltepunkt an der Cursorposition zu platzieren.  
  
## <a name="attaching-to-a-workflow-process"></a>Anfügen an einen Workflowprozess  
 Das Debugging von Workflows unterstützt auch die Verwendung der Visual Studio-Infrastruktur zum Anfügen an einen Prozess. Dies ermöglicht es dem Workflowautor, einen Workflow zu debuggen, der in einer anderen Hostumgebung ausgeführt wird, z. B. in Internetinformationsdienste (IIS) 7.0.  
  
## <a name="remote-debugging"></a>Remote Debugging  
 Remotedebuggen von Windows Workflow Foundation (WF), funktioniert genauso wie das Remotedebuggen für andere Visual Studio-Komponenten. Weitere Informationen zur Verwendung des Remotedebuggens finden Sie unter [Vorgehensweise: Aktivieren des Remotedebuggens](https://go.microsoft.com/fwlink/?LinkId=196257).  
  
> [!NOTE]
>  Wenn die workflowanwendung die X86 abzielt Architektur und gehostet wird, auf einem Computer unter einem 64-Bit-Betriebssystem, das Remotedebuggen nicht funktionieren, es sei denn, die Visual Studio auf dem Remotecomputer installiert ist, oder das Ziel für die workflowanwendung in geändert wird **Beliebige CPU**.  
  
## <a name="extending-the-workflow-debugging-service"></a>Erweitern der Debugdienste für Workflows  
 Der Debugdienst für Workflows ist jetzt öffentlich und kann zum Erstellen benutzerdefinierter Anwendungen wie Überwachung, Simulation und Debugging in einem erneut gehosteten Designer verwendet werden. Weitere Informationen finden Sie im Thema <xref:System.Activities.Presentation.Debug.DebuggerService>.
