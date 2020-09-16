---
title: Workflowüberwachung
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: fc27be295cbf0a83b65ff03e36f2aeffeda12db9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557501"
---
# <a name="workflow-tracing"></a>Workflowüberwachung
Die Workflowüberwachung bietet eine Möglichkeit, Diagnoseinformationen mit .NET Framework-Ablaufverfolgungslistenern zu erfassen. Die Ablaufverfolgung kann aktiviert werden, wenn ein Problem mit der Anwendung erkannt wird, und dann wieder deaktiviert werden, sobald das Problem behoben ist. Es gibt zwei Methoden zur Aktivierung der Debugablaufverfolgung für Workflows. Sie können sie mit der Ereignisablaufverfolgung (ETW) konfigurieren, oder Sie können Ablaufverfolgungsereignisse mit <xref:System.Diagnostics> an eine Datei senden.  
  
## <a name="enabling-debug-tracing-in-etw"></a>Aktivieren der Debugablaufverfolgung in ETW  
 Zum Aktivieren der Ablaufverfolgung in ETW aktivieren Sie den Debugkanal in der Ereignisanzeige:  
  
1. Navigieren Sie in der Ereignisanzeige zum Knoten für analytische und Debugprotokolle.  
  
2. Navigieren Sie in der Strukturansicht in Ereignisanzeige zu **Ereignisanzeige >Anwendungs-und Dienst Protokolle->Microsoft->Windows->Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Anwendungs Server-Anwendungen** , und wählen Sie **Ansicht->analytische und Debugprotokolle anzeigen**. Klicken Sie mit der rechten Maustaste auf **Debug** , und wählen Sie **Protokoll aktivieren**  
  
3. Wenn ein Workflow den Debugmodus ausführt und die Ablaufverfolgungen an den Debugkanal in ETW ausgegeben werden, können Sie diese in der Ereignisanzeige anzeigen. Navigieren Sie zu **Ereignisanzeige->Anwendungs-und Dienst Protokolle->Microsoft->Windows->Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Debug** , **und wählen Sie**  
  
4. Die Standardpuffergröße für die analytische Ablaufverfolgung beträgt nur 4 Kilobytes (KB). Es wird empfohlen, die Größe auf 32 KB zu erweitern. Führen Sie dazu die folgenden Schritte aus.  
  
    1. Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus: `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2. Ändern \<bufferSize> Sie den Wert in der Datei "Windows. ApplicationServer. Applications. man" in "32".  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3. Führen Sie den folgenden Befehl im aktuellen Frameworkverzeichnis (z. B. C:\Windows\Microsoft.NET\Framework\v4.0.21203) aus: `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
> Wenn Sie das .NET Framework 4-Client Profil verwenden, müssen Sie zuerst das ETW-Manifest registrieren, indem Sie den folgenden Befehl im Verzeichnis ".NET Framework 4" ausführen: `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a>Aktivieren der Debugablaufverfolgung mit System.Diagnostics  
 Diese Listener können in der Datei App.config der Workflowanwendung konfiguriert werden bzw. in der Datei Web.config, wenn es sich um einen Workflowdienst handelt. In diesem Beispiel ist ein <xref:System.Diagnostics.TextWriterTraceListener> so konfiguriert, dass Ablauf Verfolgungs Informationen in der MyTraceLog.txt-Datei im aktuellen Verzeichnis gespeichert werden.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Windows Server-App-Fabric-Überwachung](/previous-versions/appfabric/ee677251(v=azure.10))
- [Überwachen von Anwendungen mit App-Fabric](/previous-versions/appfabric/ee677276(v=azure.10))
