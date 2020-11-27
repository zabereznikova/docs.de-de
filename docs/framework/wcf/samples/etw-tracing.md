---
title: ETW-Ablaufverfolgung
description: In diesem Beispiel wird veranschaulicht, wie End-to-End (E2E)-Ablauf Verfolgung mithilfe der Ereignis Ablauf Verfolgung für Windows (ETW) und ETWTraceListener implementiert wird.
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: 6777b2d14786f7a79b3605bec93b4da62ff24616
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258477"
---
# <a name="etw-tracing"></a>ETW-Ablaufverfolgung

In diesem Beispiel wird das Implementieren der End-to-End (E2E)-Ablaufverfolgung mit Event Tracing for Windows (ETW) und dem in diesem Beispiel bereitgestellten `ETWTraceListener` veranschaulicht. Das Beispiel basiert auf den ersten [Schritten und umfasst](getting-started-sample.md) die ETW-Ablauf Verfolgung.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird davon ausgegangen, dass Sie mit Ablauf [Verfolgung und Nachrichten Protokollierung](tracing-and-message-logging.md)vertraut sind.  
  
 Alle Ablaufverfolgungsquellen im <xref:System.Diagnostics>-Ablaufverfolgungsmodell können über mehrere Ablaufverfolgungslistener verfügen, die bestimmen, wann und wie die Daten verfolgt werden. Der Typ des Listeners definiert das Format, in dem Ablaufverfolgungsdaten protokolliert werden. Im folgenden Codebeispiel wird das Hinzufügen eines Listeners zur Konfiguration dargestellt.  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 Damit dieser Listener verwendet werden kann, muss eine ETW-Ablaufverfolgungssitzung gestartet werden. Diese Sitzung kann mithilfe von Logman.exe oder Tracelog.exe gestartet werden. Dieses Beispiel umfasst die Datei "SetupETW.bat", sodass Sie die ETW-Ablaufverfolgungssitzung einrichten können. Außerdem wird die Datei "CleanupETW.bat" zum Schließen der Sitzung und Abschließen der Protokolldatei bereitgestellt.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas. Weitere Informationen zu diesen Tools finden Sie unter. <https://go.microsoft.com/fwlink/?LinkId=56580>  
  
 Bei der Verwendung von ETWTraceListener werden Ablaufverfolgungen in binären ETL-Dateien protokolliert. Wenn die ServiceModel-Ablaufverfolgung aktiviert ist, werden alle generierten Ablaufverfolgungen in der gleichen Datei angezeigt. Verwenden Sie das [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) zum Anzeigen von ETL-und SVCLOG-Protokolldateien. Der Viewer erstellt eine End-to-End-Ansicht des Systems, mit der eine Nachricht von der Quelle zum Ziel und zur Verwendung verfolgt werden kann.  
  
 Der ETW-Ablaufverfolgungslistener unterstützt zirkuläre Protokollierung. Um dieses Feature zu aktivieren, wechseln Sie zu **Start**, **Ausführen** , und geben `cmd` Sie ein, um eine Befehlskonsole zu starten. Ersetzen Sie im folgenden Befehl den `<logfilename>`-Parameter durch den Namen der Protokolldatei.  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 Der `-f`-Schalter und der `-max`-Schalter sind optional. Sie geben das binäre zirkuläre Format bzw. die maximale Protokollgröße von 1000 MB an. Mit dem `-p`-Schalter wird der Ablaufverfolgungsanbieter angegeben. In diesem Beispiel ist `"{411a0819-c24b-428c-83e2-26b41091702e}"` die GUID für "XML ETW Sample Provider".  
  
 Geben Sie den folgenden Befehl ein, um die Sitzung zu starten.  
  
```console  
logman start Wcf  
```  
  
 Nach Abschluss der Protokollierung können Sie die Sitzung mit dem folgenden Befehl beenden.  
  
```console  
logman stop Wcf  
```  
  
 Bei diesem Prozess werden binäre zirkuläre Protokolle generiert, die Sie mit dem Tool Ihrer Wahl verarbeiten können, einschließlich des [Service Trace Viewer-Tools (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) oder der tracerpt.  
  
 Weitere Informationen zu einem alternativen Listener zum Durchführen der zirkulären Protokollierung finden Sie auch im Beispiel für eine [zirkuläre Ablauf Verfolgung](circular-tracing.md) .  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.  
  
    > [!NOTE]
    > Zur Verwendung der Befehle RegisterProvider.bat, SetupETW.bat und CleanupETW.bat muss die Ausführung unter einem lokalen Administratorkonto erfolgen. Wenn Sie Windows Vista oder höher verwenden, müssen Sie auch die Eingabeaufforderung mit erhöhten Rechten ausführen. Klicken Sie hierzu mit der rechten Maustaste auf das Symbol für die Eingabeaufforderung, und klicken Sie dann auf **als Administrator ausführen**.  
  
3. Führen Sie vor dem Ausführen des Beispiels RegisterProvider.bat auf dem Client und dem Server aus. Dadurch wird die resultierende Datei ETWTracingSampleLog.etl zum Generieren von Ablaufverfolgungen eingerichtet, die von Service Trace Viewer angezeigt werden können. Diese Datei befindet sich im Ordner C:\logs. Wenn dieser Ordner nicht vorhanden ist, muss er erstellt werden. Andernfalls werden keine Ablaufverfolgungen generiert. Führen Sie dann SetupETW.bat auf dem Client- und dem Servercomputer aus, um die ETW-Ablaufverfolgungssitzung zu starten. Die Datei SetupETW.bat befindet sich unter dem Ordner CS\Client.  
  
4. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
5. Führen Sie nach dem Abschließen des Beispiels CleanupETW.bat aus, um das Erstellen der Datei ETWTracingSampleLog.etl abzuschließen.  
  
6. Öffnen Sie die Datei "ETWTracingSampleLog.etl" in Service Trace Viewer. Sie werden aufgefordert, die binär formatierte Datei als SVCLOG-Datei zu speichern.  
  
7. Öffnen Sie die neu erstellte SVCLOG-Datei im Viewer für Dienstabläufe, um die ETW- und ServiceModel-Ablaufverfolgungen anzuzeigen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungsbeispiele](/previous-versions/appfabric/ff383407(v=azure.10))
