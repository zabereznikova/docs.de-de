---
title: Verwenden von Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 755d93e8165b9747f799571836d6b54e54a5fc45
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623156"
---
# <a name="using-performance-counters"></a>Verwenden von Leistungsindikatoren
In diesem Beispiel wird veranschaulicht, wie Zugriff auf Windows Communication Foundation (WCF)-Leistungsindikatoren und benutzerdefinierte Leistungsindikatoren erstellen. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
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
  
 Diese Aufgabe kann auch erfolgen mithilfe der [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Wenn Leistungsindikatoren aktiviert sind, wird die gesamte Suite von WCF-Leistungsindikatoren für den Dienst aktiviert. .NET Framework behält Leistungsdaten automatisch auf drei Ebenen bei: `ServiceModelService`, `ServiceModelEndpoint` und `ServiceModelOperation`. Jede dieser Ebenen verfügt über Leistungsindikatoren wie "Calls", "Calls per Second" und "Security Calls Not Authorized".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>So zeigen Sie Leistungsdaten an  
  
1.  Starten Sie das Leistungsmonitor-Tool, indem Sie auf **starten**, **ausführen...** , geben Sie `perfmon` , und klicken Sie auf **"OK".** , oder wählen Sie in der Systemsteuerung, **Verwaltung** und doppelklicken Sie auf **Leistung**.  
  
    > [!NOTE]
    >  Sie können erst Indikatoren hinzufügen, wenn der Beispielcode ausgeführt wird.  
  
2.  Entfernen Sie die aufgeführten Leistungsindikatoren, indem Sie sie auswählen und dann die ENTF-TASTE drücken.  
  
3.  Fügen Sie WCF-Leistungsindikatoren hinzu, indem Sie mit der rechten Maustaste in des Diagrammbereich klicken und auswählen **Leistungsindikatoren hinzufügen**. In der **Leistungsindikatoren hinzufügen** wählen Sie im Dialogfeld **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 oder ServiceModelService 3.0.0.0** im Leistungsobjekt im Dropdown-Liste. Wählen Sie die anzuzeigenden Indikatoren in der Liste aus.  
  
    > [!NOTE]
    >  Es sind keine WCF-Leistungsindikatoren für einen Dienst auf, wenn keine WCF-Dienste, die auf dem Computer vorhanden sind.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>So aktivieren Sie Indikatoren mit dem Konfigurations-Editor  
  
1.  Öffnen Sie eine Instanz von SvcConfigEditor.exe.  
  
2.  Klicken Sie auf im Menü Datei auf **öffnen** , und klicken Sie dann auf **Config-Datei...** .  
  
3.  Navigieren Sie zum Dienstordner der Beispielanwendung, und öffnen Sie die Datei "Web.config".  
  
4.  Klicken Sie auf **Diagnose** in der Konfigurationsstruktur.  
  
5.  Umschalten **Leistungsindikator** in die **Diagnose** Fenster 'All' angezeigt wird.  
  
6.  Speichern Sie die Konfigurationsdatei, und beenden Sie den Editor.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Siehe auch
- [AppFabric-Überwachungsbeispiele](https://go.microsoft.com/fwlink/?LinkId=193959)
