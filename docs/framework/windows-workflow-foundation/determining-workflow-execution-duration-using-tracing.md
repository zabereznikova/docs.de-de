---
title: Bestimmen der Workflowausführungsdauer mithilfe der Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
ms.openlocfilehash: 9f9c65f2c873d54da443db14e7f5797ef1e14174
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="determining-workflow-execution-duration-using-tracing"></a>Bestimmen der Workflowausführungsdauer mithilfe der Ablaufverfolgung
In diesem Thema wird veranschaulicht, wie mit der Workflowüberwachung der Zeitraum bestimmt werden kann, den ein erfolgreich abgeschlossener und selbst gehosteter Workflow zur Ausführung benötigt.  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a>So bestimmen Sie die Ausführungsdauer der Workflowanwendung mit der Workflowüberwachung  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  Wählen Sie **Datei**, **neue**, **Projekt**.  Klicken Sie unter **c#**, wählen die **Workflow** Knoten.  Wählen Sie **Workflowkonsolenanwendung** aus der Liste der Vorlagen.  Nennen Sie das neue Projekt `WorkflowDurationTracing` , und klicken Sie auf **OK**.  
  
2.  Öffnen Sie Workflow1.xaml.  Ziehen Sie eine <xref:System.Activities.Statements.Delay>-Aktivität auf die Designeroberfläche. Weisen Sie der Duration-Eigenschaft der Aktivität den Wert 00:00:10 (zehn Sekunden) zu.  
  
3.  Ereignisanzeige öffnen, indem Sie auf **starten**, **ausführen**, und geben Sie `eventvwr.exe`.  
  
4.  Wenn Sie workflowüberwachung nicht aktiviert haben, erweitern Sie **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver-Anwendungen** . Wählen Sie **Ansicht**, **analytische und Debugprotokolle einblenden**. Mit der rechten Maustaste **Debuggen** , und wählen Sie **Protokoll aktivieren**. Lassen Sie die Ereignisanzeige geöffnet, damit Ablaufverfolgungen angezeigt werden können, nachdem der Workflow ausgeführt wurde.  
  
5.  Führen Sie die Workflowanwendung aus, indem Sie STRG+UMSCHALT+B drücken.  
  
6.  Suchen Sie in der Ereignisanzeige ein aktuelles Ereignis mit der ID 1009 und einer Meldung ähnlich der folgenden. Notieren Sie sich den Zeitpunkt der Protokollierung der Meldung.  
  
 **Übergeordnete Aktivität '', DisplayName: '', InstanceId: '' geplante untergeordnete Aktivität 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**  
  
7.  Suchen Sie ein anderes aktuelles Ereignis mit der ID 1001 und einer Meldung ähnlich der folgenden.  Subtrahieren Sie den Zeitpunkt der vorherigen Nachricht vom protokollierten Wert für diese Nachricht, um die Ausführungsdauer des Workflows zu bestimmen. Diese sollte sich im Bereich von 10 Sekunden bewegen.  
  
 **WorkflowInstance-Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' wurde in den geschlossenen Zustand übergeht.**  
  
## <a name="see-also"></a>Siehe auch  
 [Workflowüberwachung](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [Windows Server App Fabric-Überwachung](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Überwachen von Anwendungen mit AppFabric](http://go.microsoft.com/fwlink/?LinkId=201275)
