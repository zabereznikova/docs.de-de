---
title: "Bestimmen der Workflowausf&#252;hrungsdauer mithilfe der Ablaufverfolgung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Bestimmen der Workflowausf&#252;hrungsdauer mithilfe der Ablaufverfolgung
In diesem Thema wird veranschaulicht, wie mit der Workflowüberwachung der Zeitraum bestimmt werden kann, den ein erfolgreich abgeschlossener und selbst gehosteter Workflow zur Ausführung benötigt.  
  
### So bestimmen Sie die Ausführungsdauer der Workflowanwendung mit der Workflowüberwachung  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].Wählen Sie **Datei**, **Neu** und **Projekt** aus.Wählen Sie unter **C\#** den Knoten **Workflow** aus.Wählen Sie in der Liste der Vorlagen **Workflowkonsolenanwendung** aus.Nennen Sie das neue Projekt `WorkflowDurationTracing`, und klicken Sie auf **OK**.  
  
2.  Öffnen Sie Workflow1.xaml.Ziehen Sie eine <xref:System.Activities.Statements.Delay>\-Aktivität auf die Designeroberfläche.Weisen Sie der Duration\-Eigenschaft der Aktivität den Wert 00:00:10 \(zehn Sekunden\) zu.  
  
3.  Öffnen Sie die Ereignisanzeige, indem Sie auf **Start** und **Ausführen** klicken und dann `eventvwr.exe` eingeben.  
  
4.  Wenn Sie die Workflowüberwachung nicht aktiviert haben, erweitern Sie **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows** und **Anwendungsserver \- Anwendungen**.Wählen Sie **Ansicht** und **Analytische und Debugprotokolle einblenden** aus.Klicken Sie mit der rechten Maustaste auf **Debuggen**, und wählen Sie **Protokoll aktivieren**.Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Workflow ausgeführt wurde.  
  
5.  Führen Sie die Workflowanwendung aus, indem Sie STRG\+UMSCHALT\+B drücken.  
  
6.  Suchen Sie in der Ereignisanzeige ein aktuelles Ereignis mit der ID 1009 und einer Meldung ähnlich der folgenden.Notieren Sie sich den Zeitpunkt der Protokollierung der Meldung.  
  
 **Übergeordnete Aktivität '', DisplayName: '', InstanceId: '' geplante untergeordnete Aktivität 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**  
  
7.  Suchen Sie ein anderes aktuelles Ereignis mit der ID 1001 und einer Meldung ähnlich der folgenden.Subtrahieren Sie den Zeitpunkt der vorherigen Nachricht vom protokollierten Wert für diese Nachricht, um die Ausführungsdauer des Workflows zu bestimmen. Diese sollte sich im Bereich von 10 Sekunden bewegen.  
  
 **WorkflowInstanceId: '1bbac57b\-3322\-498e\-9e27\-8833fda3a5bf' wurde mit dem Status 'Closed' abgeschlossen.**  
  
## Siehe auch  
 [Workflowüberwachung](../../../docs/framework/windows-workflow-foundation//workflow-tracing.md)   
 [Überwachung mit Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Überwachen von Anwendungen mit AppFabric](http://go.microsoft.com/fwlink/?LinkId=201275)