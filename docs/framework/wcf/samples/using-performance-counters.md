---
title: Verwenden von Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 7ffd9f5de5efb4be22968958246839e804daf23d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143576"
---
# <a name="using-performance-counters"></a>Verwenden von Leistungsindikatoren
In diesem Beispiel wird veranschaulicht, wie Sie auf Windows Communication Foundation (WCF)-Leistungsindikatoren zugreifen und wie benutzerdefinierte Leistungsindikatoren erstellt werden. Dieses Beispiel basiert auf den [Ersten Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel ruft der Client die vier Methoden des `ICalculator`-Diensts auf. Der Client setzt dies fort, bis er vom Benutzer unterbrochen wird. Der Dienst bleibt unverändert.  
  
 Die Leistungsindikatoren sind im Diagnoseabschnitt der Datei "Web.config" für diesen Dienst aktiviert, wie in der folgenden Beispielkonfiguration dargestellt.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 Diese Aufgabe kann auch mit dem [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)durchgeführt werden.  
  
 Wenn Leistungsindikatoren aktiviert sind, wird die gesamte Suite von WCF-Leistungsindikatoren für den Dienst aktiviert. .NET Framework behält Leistungsdaten automatisch auf drei Ebenen bei: `ServiceModelService`, `ServiceModelEndpoint` und `ServiceModelOperation`. Jede dieser Ebenen verfügt über Leistungsindikatoren wie "Calls", "Calls per Second" und "Security Calls Not Authorized".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Einzel- oder Computerkonfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>So zeigen Sie Leistungsdaten an  
  
1. Starten Sie das Systemmonitor-Tool, indem `perfmon` Sie auf **Starten**, **Ausführen...** klicken, geben Sie **ok** ein, oder klicken Sie in der Systemsteuerung, wählen Sie **Verwaltungstools aus,** und doppelklicken Sie auf **Leistung**.  
  
    > [!NOTE]
    > Sie können erst Indikatoren hinzufügen, wenn der Beispielcode ausgeführt wird.  
  
2. Entfernen Sie die aufgeführten Leistungsindikatoren, indem Sie sie auswählen und dann die ENTF-TASTE drücken.  
  
3. Fügen Sie WCF-Zähler hinzu, indem Sie mit der rechten Maustaste auf den Diagrammbereich klicken und **Counter hinzufügen**auswählen. Wählen Sie im Dialogfeld **"Zähler hinzufügen"** im Dropdown-Listenfeld **Performance-Objekt3.0.0.0, ServiceModelEndpoint 3.0.0.0 oder ServiceModelService 3.0.0.0** im Dropdown-Listenfeld Performance-Objekt aus. Wählen Sie die anzuzeigenden Indikatoren in der Liste aus.  
  
    > [!NOTE]
    > Es sind keine WCF-Leistungsindikatoren für einen Dienst vorhanden, wenn auf dem Computer keine WCF-Dienste ausgeführt werden.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>So aktivieren Sie Indikatoren mit dem Konfigurations-Editor  
  
1. Öffnen Sie eine Instanz von SvcConfigEditor.exe.  
  
2. Klicken Sie im Menü Datei auf **Öffnen** und dann auf **Config-Datei...**.  
  
3. Navigieren Sie zum Dienstordner der Beispielanwendung, und öffnen Sie die Datei "Web.config".  
  
4. Klicken Sie in der Konfigurationsstruktur auf **Diagnose.**  
  
5. Schalten Sie den **Leistungsindikator** im **Diagnosefenster** um, um "Alle" anzuzeigen.  
  
6. Speichern Sie die Konfigurationsdatei, und beenden Sie den Editor.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
