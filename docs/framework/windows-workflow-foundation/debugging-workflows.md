---
title: "Debuggen von Workflows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Debuggen von Workflows
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] bietet mehrere Optionen für das Debuggen ausgeführter Workflows über die Entwicklungsumgebung.  Das Debugging von Workflows kann im Designer, in XAML und in Code erfolgen.  
  
## Debuggen des Workflow\-Designers  
 Haltepunkte können im Workflow\-Designer für Aktivitäten festgelegt werden, indem entweder die Aktivität markiert und **F9** gedrückt wird oder das Kontextmenü der Aktivität verwendet wird.  Die Ausführung des Workflows wird daraufhin unterbrochen, wenn der Workflowhost im Debugmodus ausgeführt wird.  In der folgenden Bildschirmabbildung wird die Ausführung des Workflows an einem Haltepunkt angehalten.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Debuggen von Workflows mit dem Workflow\-Designer](../Topic/Debugging%20Workflows%20with%20the%20Workflow%20Designer.md).  
  
## Debugging in XAML  
 Wenn ein Workflow an einem Haltepunkt im Designer angehalten wird, kann das Debugging des Workflows auch in XAML erfolgen.  Wählen Sie zum Anzeigen des Ausführungspunkts in XAML die Option **XAML\-Ansicht** im Workflow\-Designer aus, wenn die Ausführung des Workflows angehalten wird.  Das Debugging kann erneut vom Designer übernommen werden, indem der Workflow aus dem Projektmappen\-Explorer erneut im Designer geöffnet wird.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Vorgehensweise: Debuggen von XAML mit dem Workflow\-Designer](../Topic/How%20to:%20Debug%20XAML%20with%20the%20Workflow%20Designer.md).  
  
## Debugging in Code  
 Codehaltepunkte können in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] auf die gleiche Weise verwendet werden wie in anderen imperativen Anwendungen.  Klicken Sie im Codebereich auf den linken Rand, um einen Codehaltepunkt zu erstellen, oder drücken Sie **F9**, um einen Haltepunkt an der Cursorposition zu platzieren.  
  
## Anfügen an einen Workflowprozess  
 Das Debugging von Workflows unterstützt auch die Verwendung der Visual Studio\-Infrastruktur zum Anfügen an einen Prozess.  Dies ermöglicht es dem Workflowautor, einen Workflow zu debuggen, der in einer anderen Hostumgebung ausgeführt wird, z. B. in Internetinformationsdienste \(IIS\) 7.0.  
  
## Remotedebuggen  
 Das Remotedebugging in [!INCLUDE[wf](../../../includes/wf-md.md)] funktioniert genauso wie das Remotedebugging for andere [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]\-Komponenten.  Weitere Informationen über die Verwendung des Remotedebuggens finden Sie unter [Gewusst wie: Aktivieren von Remotedebuggen](http://go.microsoft.com/fwlink/?LinkId=196257).  
  
> [!NOTE]
>  Wenn die Workflowanwendung für die x86\-Architektur konzipiert ist und auf einem Computer gehostet wird, auf dem ein 64\-Bit\-Betriebssystem ausgeführt wird, funktioniert das Remotedebuggen nur, wenn [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] auf dem Remotecomputer installiert wird oder das Ziel für die Workflowanwendung in **Any CPU** geändert wird.  
  
## Erweitern der Debugdienste für Workflows  
 Der Debugdienst für Workflows ist jetzt öffentlich und kann zum Erstellen benutzerdefinierter Anwendungen wie Überwachung, Simulation und Debugging in einem erneut gehosteten Designer verwendet werden.  [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] dem folgenden Thema: <xref:System.Activities.Presentation.Debug.DebuggerService>.