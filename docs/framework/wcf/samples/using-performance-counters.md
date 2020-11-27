---
title: Verwenden von Leistungsindikatoren
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: d3e6b9805bd0b9c5eea991fce4dde2035f8f5c1b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294910"
---
# <a name="using-performance-counters"></a>Verwenden von Leistungsindikatoren

In diesem Beispiel wird veranschaulicht, wie auf Windows Communication Foundation (WCF)-Leistungsindikatoren zugegriffen wird und wie benutzerdefinierte Leistungsindikatoren erstellt werden. Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten.  
  
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
  
 Diese Aufgabe kann auch mithilfe des- [Konfigurations-Editor-Tools (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)ausgeführt werden.  
  
 Wenn Leistungsindikatoren aktiviert sind, wird die gesamte Sammlung von WCF-Leistungsindikatoren für den Dienst aktiviert. .NET Framework behält Leistungsdaten automatisch auf drei Ebenen bei: `ServiceModelService`, `ServiceModelEndpoint` und `ServiceModelOperation`. Jede dieser Ebenen verfügt über Leistungsindikatoren wie "Calls", "Calls per Second" und "Security Calls Not Authorized".  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
### <a name="to-view-performance-data"></a>So zeigen Sie Leistungsdaten an  
  
1. Starten Sie das System Monitor Tool, indem Sie auf **Start**, **ausführen...**, eingeben `perfmon` und auf **OK klicken,** oder wählen Sie in der Systemsteuerung die Option **Verwaltung** aus, und doppelklicken Sie auf **Leistung**.  
  
    > [!NOTE]
    > Sie können erst Indikatoren hinzufügen, wenn der Beispielcode ausgeführt wird.  
  
2. Entfernen Sie die aufgeführten Leistungsindikatoren, indem Sie sie auswählen und dann die ENTF-TASTE drücken.  
  
3. Fügen Sie WCF-Indikatoren hinzu, indem Sie mit der rechten Maustaste auf den Diagrammbereich klicken und **Zähler hinzufügen** Wählen Sie im Dialogfeld Leistungsindikatoren **Hinzufügen** im Dropdown-Listenfeld Leistungs Objekt die Option **Service Model Operation 3.0.0.0, Service Model Endpoint 3.0.0.0 oder Service Model Service 3.0.0.0** aus. Wählen Sie die anzuzeigenden Indikatoren in der Liste aus.  
  
    > [!NOTE]
    > Es sind keine WCF-Leistungsindikatoren für einen Dienst vorhanden, wenn auf dem Computer keine WCF-Dienste ausgeführt werden.  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a>So aktivieren Sie Indikatoren mit dem Konfigurations-Editor  
  
1. Öffnen Sie eine Instanz von SvcConfigEditor.exe.  
  
2. Klicken Sie im Menü Datei auf **Öffnen** , und klicken Sie dann auf **Konfigurationsdatei...**.  
  
3. Navigieren Sie zum Dienstordner der Beispielanwendung, und öffnen Sie die Datei "Web.config".  
  
4. Klicken Sie in der Konfigurations Struktur auf **Diagnose** .  
  
5. **Wechseln Sie im** **Diagnose** Fenster zum Anzeigen von "alle".  
  
6. Speichern Sie die Konfigurationsdatei, und beenden Sie den Editor.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungsbeispiele](/previous-versions/appfabric/ff383407(v=azure.10))
