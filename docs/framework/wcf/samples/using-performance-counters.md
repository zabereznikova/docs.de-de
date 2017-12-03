---
title: Verwenden von Leistungsindikatoren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5963a1b2600066020562c1d17b0d2d2eb6eb67c8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="using-performance-counters"></a>Verwenden von Leistungsindikatoren
In diesem Beispiel wird veranschaulicht, wie auf [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Leistungsindikatoren zugegriffen wird und wie benutzerdefinierte Leistungsindikatoren erstellt werden. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel ruft der Client die vier Methoden des `ICalculator`-Diensts auf. Der Client setzt dies fort, bis er vom Benutzer unterbrochen wird. Der Dienst bleibt unverändert.  
  
 Die Leistungsindikatoren sind im Diagnoseabschnitt der Datei "Web.config" für diesen Dienst aktiviert, wie in der folgenden Beispielkonfiguration dargestellt.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 Diese Aufgabe kann auch erfolgen mithilfe der [Dienstkonfigurations-Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Wenn Leistungsindikatoren aktiviert sind, wird die ganze Suite von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Leistungsindikatoren für den Dienst aktiviert. .NET Framework behält Leistungsdaten automatisch auf drei Ebenen bei: `ServiceModelService`, `ServiceModelEndpoint` und `ServiceModelOperation`. Jede dieser Ebenen verfügt über Leistungsindikatoren wie "Calls", "Calls per Second" und "Security Calls Not Authorized".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>So zeigen Sie Leistungsdaten an  
  
1.  Starten Sie das Leistungsmonitor-Tool, indem Sie auf **starten**, **ausführen...** , geben Sie `perfmon` , und klicken Sie auf **"OK".** , oder wählen Sie in der Systemsteuerung **Verwaltung** und doppelklicken Sie auf **Leistung**.  
  
    > [!NOTE]
    >  Sie können erst Indikatoren hinzufügen, wenn der Beispielcode ausgeführt wird.  
  
2.  Entfernen Sie die aufgeführten Leistungsindikatoren, indem Sie sie auswählen und dann die ENTF-TASTE drücken.  
  
3.  Add [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Leistungsindikatoren, indem Sie mit der rechten Maustaste in des Diagrammbereich klicken und auswählen **Leistungsindikatoren hinzufügen**. In der **Leistungsindikatoren hinzufügen** wählen Sie im Dialogfeld **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 oder ServiceModelService 3.0.0.0** in das Leistungsobjekt "" im Dropdown-Liste. Wählen Sie die anzuzeigenden Indikatoren in der Liste aus.  
  
    > [!NOTE]
    >  Es werden keine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Leistungsindikatoren für einen Dienst angezeigt, wenn keine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste auf dem Computer ausgeführt werden.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>So aktivieren Sie Indikatoren mit dem Konfigurations-Editor  
  
1.  Öffnen Sie eine Instanz von SvcConfigEditor.exe.  
  
2.  Klicken Sie auf das Menü Datei auf **öffnen** , und klicken Sie dann auf **Datei "App.config"...** .  
  
3.  Navigieren Sie zum Dienstordner der Beispielanwendung, und öffnen Sie die Datei "Web.config".  
  
4.  Klicken Sie auf **Diagnose** in der Konfigurationsstruktur.  
  
5.  Zum ein-/ausschalten **Leistungsindikator** in der **Diagnose** Fenster werden "All" angezeigt.  
  
6.  Speichern Sie die Konfigurationsdatei, und beenden Sie den Editor.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Siehe auch  
 [Überwachen der AppFabric-Beispiele](http://go.microsoft.com/fwlink/?LinkId=193959)
