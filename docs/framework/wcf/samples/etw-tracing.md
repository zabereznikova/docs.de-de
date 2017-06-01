---
title: "ETW-Ablaufverfolgung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
caps.latest.revision: 42
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 42
---
# ETW-Ablaufverfolgung
In diesem Beispiel wird das Implementieren der End\-to\-End \(E2E\)\-Ablaufverfolgung mit Event Tracing for Windows \(ETW\) und dem in diesem Beispiel bereitgestellten `ETWTraceListener` veranschaulicht.Das Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md) und schließt die ETW\-Ablaufverfolgung ein.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird vorausgesetzt, dass Sie mit [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) vertraut sind.  
  
 Alle Ablaufverfolgungsquellen im <xref:System.Diagnostics>\-Ablaufverfolgungsmodell können über mehrere Ablaufverfolgungslistener verfügen, die bestimmen, wann und wie die Daten verfolgt werden.Der Typ des Listeners definiert das Format, in dem Ablaufverfolgungsdaten protokolliert werden.Im folgenden Codebeispiel wird das Hinzufügen eines Listeners zur Konfiguration dargestellt.  
  
```  
  
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
  
 Damit dieser Listener verwendet werden kann, muss eine ETW\-Ablaufverfolgungssitzung gestartet werden.Diese Sitzung kann mithilfe von Logman.exe oder Tracelog.exe gestartet werden.Dieses Beispiel umfasst die Datei "SetupETW.bat", sodass Sie die ETW\-Ablaufverfolgungssitzung einrichten können. Außerdem wird die Datei "CleanupETW.bat" zum Schließen der Sitzung und Abschließen der Protokolldatei bereitgestellt.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.Weitere Informationen zu diesen Tools finden Sie unter [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=56580](http://go.microsoft.com/fwlink/?LinkId=56580) \(möglicherweise in englischer Sprache\).  
  
 Bei der Verwendung von ETWTraceListener werden Ablaufverfolgungen in binären ETL\-Dateien protokolliert.Wenn die ServiceModel\-Ablaufverfolgung aktiviert ist, werden alle generierten Ablaufverfolgungen in der gleichen Datei angezeigt.Verwenden Sie [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) zum Anzeigen von ETL\- und SVCLOG\-Protokolldateien.Der Viewer erstellt eine End\-to\-End\-Ansicht des Systems, mit der eine Nachricht von der Quelle zum Ziel und zur Verwendung verfolgt werden kann.  
  
 Der ETW\-Ablaufverfolgungslistener unterstützt zirkuläre Protokollierung.Klicken Sie zum Aktivieren dieser Funktionen auf **Start**, **Ausführen**, und geben Sie dann `cmd` ein, um eine Befehlskonsole zu starten.Ersetzen Sie im folgenden Befehl den `<logfilename>`\-Parameter durch den Namen der Protokolldatei.  
  
```  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 Der `-f`\-Schalter und der `-max`\-Schalter sind optional.Sie geben das binäre zirkuläre Format bzw. die maximale Protokollgröße von 1000 MB an.Mit dem `-p`\-Schalter wird der Ablaufverfolgungsanbieter angegeben.In diesem Beispiel ist `"{411a0819-c24b-428c-83e2-26b41091702e}"` die GUID für "XML ETW Sample Provider".  
  
 Geben Sie den folgenden Befehl ein, um die Sitzung zu starten.  
  
```  
Logman start Wcf  
  
```  
  
 Nach Abschluss der Protokollierung können Sie die Sitzung mit dem folgenden Befehl beenden.  
  
```  
Logman stop Wcf  
```  
  
 Bei diesem Prozess werden binäre zirkuläre Protokolle generiert, die mit einem beliebigen Tool verarbeitet werden können, beispielsweise [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) oder Tracerpt.  
  
 Im Beispiel [Zirkuläre Ablaufverfolgung](../../../../docs/framework/wcf/samples/circular-tracing.md) finden Sie außerdem weitere Informationen zu einem alternativen Listener zum Ausführen der zirkulären Protokollierung.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Projektmappe zu erstellen.  
  
    > [!NOTE]
    >  Zur Verwendung der Befehle RegisterProvider.bat, SetupETW.bat und CleanupETW.bat muss die Ausführung unter einem lokalen Administratorkonto erfolgen.Wenn Sie mit [!INCLUDE[wv](../../../../includes/wv-md.md)] oder höher arbeiten, müssen Sie auch die Eingabeaufforderung mit erweiterten Berechtigungen ausführen.Klicken Sie hierzu mit der rechten Maustaste auf das Symbol für die Eingabeaufforderung, und klicken Sie dann auf **Als Administrator ausführen**.  
  
3.  Führen Sie vor dem Ausführen des Beispiels RegisterProvider.bat auf dem Client und dem Server aus.Dadurch wird die resultierende Datei ETWTracingSampleLog.etl zum Generieren von Ablaufverfolgungen eingerichtet, die von Service Trace Viewer angezeigt werden können.Diese Datei befindet sich im Ordner C:\\logs.Wenn dieser Ordner nicht vorhanden ist, muss er erstellt werden. Andernfalls werden keine Ablaufverfolgungen generiert.Führen Sie dann SetupETW.bat auf dem Client\- und dem Servercomputer aus, um die ETW\-Ablaufverfolgungssitzung zu starten.Die Datei SetupETW.bat befindet sich unter dem Ordner CS\\Client.  
  
4.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
5.  Führen Sie nach dem Abschließen des Beispiels CleanupETW.bat aus, um das Erstellen der Datei ETWTracingSampleLog.etl abzuschließen.  
  
6.  Öffnen Sie die Datei "ETWTracingSampleLog.etl" in Service Trace Viewer.Sie werden aufgefordert, die binär formatierte Datei als SVCLOG\-Datei zu speichern.  
  
7.  Öffnen Sie die neu erstellte SVCLOG\-Datei im Viewer für Dienstabläufe, um die ETW\- und ServiceModel\-Ablaufverfolgungen anzuzeigen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## Siehe auch  
 [AppFabric\-Überwachungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193959)