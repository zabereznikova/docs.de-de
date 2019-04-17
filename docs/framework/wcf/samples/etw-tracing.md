---
title: ETW-Ablaufverfolgung
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: a5c2f173978f514aa4627caa476a595d8d45d4f9
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613745"
---
# <a name="etw-tracing"></a>ETW-Ablaufverfolgung
In diesem Beispiel wird das Implementieren der End-to-End (E2E)-Ablaufverfolgung mit Event Tracing for Windows (ETW) und dem in diesem Beispiel bereitgestellten `ETWTraceListener` veranschaulicht. Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) und ETW-Ablaufverfolgung enthält.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird davon ausgegangen, dass Sie kennen [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
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
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas. Weitere Informationen zu diesen Tools finden Sie unter <https://go.microsoft.com/fwlink/?LinkId=56580>  
  
 Bei der Verwendung von ETWTraceListener werden Ablaufverfolgungen in binären ETL-Dateien protokolliert. Wenn die ServiceModel-Ablaufverfolgung aktiviert ist, werden alle generierten Ablaufverfolgungen in der gleichen Datei angezeigt. Verwendung [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zum Anzeigen von ETL- und svclog-Protokolldateien. Der Viewer erstellt eine End-to-End-Ansicht des Systems, mit der eine Nachricht von der Quelle zum Ziel und zur Verwendung verfolgt werden kann.  
  
 Der ETW-Ablaufverfolgungslistener unterstützt zirkuläre Protokollierung. Um dieses Feature zu aktivieren, wechseln Sie zu **starten**, **ausführen** und `cmd` um eine Befehlskonsole zu starten. Ersetzen Sie im folgenden Befehl den `<logfilename>`-Parameter durch den Namen der Protokolldatei.  
  
```  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 Der `-f`-Schalter und der `-max`-Schalter sind optional. Sie geben das binäre zirkuläre Format bzw. die maximale Protokollgröße von 1000 MB an. Mit dem `-p`-Schalter wird der Ablaufverfolgungsanbieter angegeben. In diesem Beispiel ist `"{411a0819-c24b-428c-83e2-26b41091702e}"` die GUID für "XML ETW Sample Provider".  
  
 Geben Sie den folgenden Befehl ein, um die Sitzung zu starten.  
  
```  
Logman start Wcf  
```  
  
 Nach Abschluss der Protokollierung können Sie die Sitzung mit dem folgenden Befehl beenden.  
  
```  
Logman stop Wcf  
```  
  
 Dieser Prozess wird generiert, binäre zirkuläre Protokolle, die Sie mit dem Tool Ihrer Wahl verarbeiten können einschließlich [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) oder Tracerpt.  
  
 Sie können auch überprüfen, die [zirkuläre Ablaufverfolgung](../../../../docs/framework/wcf/samples/circular-tracing.md) Beispiel für Weitere Informationen zu einem alternativen Listener zum Ausführen der zirkulären Protokollierung.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Achten Sie darauf durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Um die Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
    > [!NOTE]
    >  Zur Verwendung der Befehle RegisterProvider.bat, SetupETW.bat und CleanupETW.bat muss die Ausführung unter einem lokalen Administratorkonto erfolgen. Wenn Sie mit [!INCLUDE[wv](../../../../includes/wv-md.md)] oder höher arbeiten, müssen Sie auch die Eingabeaufforderung mit erweiterten Berechtigungen ausführen. Zu diesem Zweck mit der rechten Maustaste in des Symbol "Eingabeaufforderung", und klicken Sie dann **als Administrator ausführen**.  
  
3. Führen Sie vor dem Ausführen des Beispiels RegisterProvider.bat auf dem Client und dem Server aus. Dadurch wird die resultierende Datei ETWTracingSampleLog.etl zum Generieren von Ablaufverfolgungen eingerichtet, die von Service Trace Viewer angezeigt werden können. Diese Datei befindet sich im Ordner C:\logs. Wenn dieser Ordner nicht vorhanden ist, muss er erstellt werden. Andernfalls werden keine Ablaufverfolgungen generiert. Führen Sie dann SetupETW.bat auf dem Client- und dem Servercomputer aus, um die ETW-Ablaufverfolgungssitzung zu starten. Die Datei SetupETW.bat befindet sich unter dem Ordner CS\Client.  
  
4. Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
5. Führen Sie nach dem Abschließen des Beispiels CleanupETW.bat aus, um das Erstellen der Datei ETWTracingSampleLog.etl abzuschließen.  
  
6. Öffnen Sie die Datei "ETWTracingSampleLog.etl" in Service Trace Viewer. Sie werden aufgefordert, die binär formatierte Datei als SVCLOG-Datei zu speichern.  
  
7. Öffnen Sie die neu erstellte SVCLOG-Datei im Viewer für Dienstabläufe, um die ETW- und ServiceModel-Ablaufverfolgungen anzuzeigen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a>Siehe auch

- [AppFabric-Überwachungsbeispiele](https://go.microsoft.com/fwlink/?LinkId=193959)
