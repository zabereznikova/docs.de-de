---
title: Debuggen von Workflows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9304622ff4243f7f885de2175a66cfae1c192aeb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-workflows"></a>Debuggen von Workflows
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] bietet mehrere Optionen für das Debuggen ausgeführter Workflows über die Entwicklungsumgebung. Das Debugging von Workflows kann im Designer, in XAML und in Code erfolgen.  
  
## <a name="debugging-in-the-workflow-designer"></a>Debuggen des Workflow-Designers  
 Haltepunkte können für Aktivitäten im Workflow-Designer festgelegt werden, indem Sie entweder die Aktivität markiert, und drücken **F9** oder mithilfe der Aktivität-Kontextmenü. Die Ausführung des Workflows wird daraufhin unterbrochen, wenn der Workflowhost im Debugmodus ausgeführt wird. In der folgenden Bildschirmabbildung wird die Ausführung des Workflows an einem Haltepunkt angehalten. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Debuggen von Workflows mit dem Workflow-Designer](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).  
  
## <a name="debugging-in-xaml"></a>Debugging in XAML  
 Wenn ein Workflow an einem Haltepunkt im Designer angehalten wird, kann das Debugging des Workflows auch in XAML erfolgen. Wählen Sie zum Anzeigen des Ausführungspunkts in XAML **XAML-Ansicht** im Workflow-Designer bei der Ausführung des Workflows angehalten wird. Das Debugging kann erneut vom Designer übernommen werden, indem der Workflow aus dem Projektmappen-Explorer erneut im Designer geöffnet wird. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Vorgehensweise: Debuggen von XAML mit dem Workflow-Designer](/visualstudio/workflow-designer/how-to-debug-xaml-with-the-workflow-designer).  
  
## <a name="debugging-in-code"></a>Debugging in Code  
 Codehaltepunkte können in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] auf die gleiche Weise verwendet werden wie in anderen imperativen Anwendungen. Klicken Sie auf den linken Rand der Codebereich, um einen codehaltepunkt zu erstellen, oder drücken Sie **F9** um einen Haltepunkt an der Cursorposition zu platzieren.  
  
## <a name="attaching-to-a-workflow-process"></a>Anfügen an einen Workflowprozess  
 Das Debugging von Workflows unterstützt auch die Verwendung der Visual Studio-Infrastruktur zum Anfügen an einen Prozess. Dies ermöglicht es dem Workflowautor, einen Workflow zu debuggen, der in einer anderen Hostumgebung ausgeführt wird, z. B. in Internetinformationsdienste (IIS) 7.0.  
  
## <a name="remote-debugging"></a>Remotedebuggen  
 Das Remotedebugging in [!INCLUDE[wf](../../../includes/wf-md.md)] funktioniert genauso wie das Remotedebugging for andere [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]-Komponenten. Informationen zur Verwendung des Remotedebuggens finden Sie unter [Vorgehensweise: Aktivieren von Remotedebuggen](http://go.microsoft.com/fwlink/?LinkId=196257).  
  
> [!NOTE]
>  Wenn die workflowanwendung für die X86 diejenige Architektur und auf einem Computer unter einem 64-Bit-Betriebssystem gehostet wird, Remotedebuggen nicht funktioniert, wenn [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] auf dem Remotecomputer oder das Ziel installiert ist, für die workflowanwendung geändert wird um **beliebige CPU**.  
  
## <a name="extending-the-workflow-debugging-service"></a>Erweitern der Debugdienste für Workflows  
 Der Debugdienst für Workflows ist jetzt öffentlich und kann zum Erstellen benutzerdefinierter Anwendungen wie Überwachung, Simulation und Debugging in einem erneut gehosteten Designer verwendet werden. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] dem folgenden Thema: <xref:System.Activities.Presentation.Debug.DebuggerService>.
