---
title: 'Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung'
ms.date: 03/30/2017
helpviewer_keywords:
- formatting [.NET Framework], network tracing
- network tracing, configuring
- level attribute
- app.config files, network tracing
- configuration files [.NET Framework], network tracing
- protocol-level trace output
- application configuration files, network tracing
- sockets, trace output
ms.assetid: 5ef9fe4b-8d3d-490e-9259-1d014b2181af
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 77eb199e5e8bbfb0874f8189a8daa2904b31d48e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-configure-network-tracing"></a>Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung
Die Anwendungs- oder Computerkonfigurationsdatei enthält die Einstellungen, die das Format und die Inhalte von Netzwerkablaufverfolgungen bestimmen. Bevor Sie diese Verfahren ausführen, stellen Sie sicher, dass die Ablaufverfolgung aktiviert ist. Weitere Informationen zur Aktivierung der Netzwerkablaufverfolgung finden Sie unter [Enabling Network Tracing (Aktivieren der Netzwerkablaufverfolgung)](../../../docs/framework/network-programming/enabling-network-tracing.md).  
  
 Die Computerkonfigurationsdatei "machine.config" ist im Ordner "%Windir%\Microsoft.NET\Framework" in dem Verzeichnis gespeichert, in dem Windows installiert wurde. Es gibt für jede Version von .NET Framework, die auf dem Computer installiert ist, eine eigene machine.config-Datei in den Unterordnern von %Windir%\Microsoft.NET\Framework (z.B. C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config oder C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config).  
  
 Diese Einstellungen können auch in der Konfigurationsdatei für die Anwendung vorgenommen werden. Die Anwendungskonfigurationsdatei hat Vorrang vor der Computerkonfigurationsdatei.  
  
### <a name="to-configure-network-tracing"></a>So konfigurieren Sie die Netzwerkablaufverfolgung  
  
-   Fügen Sie der jeweiligen Konfigurationsdatei die folgenden Zeilen hinzu. Die Werte und Optionen für diese Einstellungen sind in den folgenden Tabellen beschrieben.  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <source name="System.Net" tracemode="includehex" maxdatasize="1024">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Cache">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Http">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.Sockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
          <source name="System.Net.WebSockets">  
            <listeners>  
              <add name="System.Net"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="System.Net" value="Verbose"/>  
          <add name="System.Net.Cache" value="Verbose"/>  
          <add name="System.Net.Http" value="Verbose"/>  
          <add name="System.Net.Sockets" value="Verbose"/>  
          <add name="System.Net.WebSockets" value="Verbose"/>  
        </switches>  
        <sharedListeners>  
          <add name="System.Net"  
            type="System.Diagnostics.TextWriterTraceListener"  
            initializeData="network.log"  
          />  
        </sharedListeners>  
        <trace autoflush="true"/>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
 Wenn Sie einen Namen im `<switches>`-Block hinzufügen, enthält die Ausgabe der Ablaufverfolgung Informationen von einigen zu diesem Namen gehörenden Methoden. Die Ausgabe wird in der folgenden Tabelle beschrieben.  
  
|name|Ausgabe von|  
|----------|-----------------|  
|`System.Net.Sockets`|Einige öffentliche Methoden der Klassen <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> und <xref:System.Net.Dns>|  
|`System.Net`|Einige öffentliche Methoden der Klassen <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> sowie SSL-Debuginformationen (Ungültige Zertifikate, fehlende Ausstellerliste und Clientzertifikatsfehler.)|  
|`System.Net.HttpListener`|Einige öffentliche Methoden der Klassen <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> und <xref:System.Net.HttpListenerResponse>.|  
|`System.Net.Cache`|Einige private und interne Methoden in `System.Net.Cache`.|  
|`System.Net.Http`|Einige öffentliche Methoden der Klassen <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> und <xref:System.Net.Http.WebRequestHandler>.|  
|`System.Net.WebSockets.WebSocket`|Einige öffentliche Methoden der Klassen <xref:System.Net.WebSockets.ClientWebSocket> und <xref:System.Net.WebSockets.WebSocket>.|  
  
 Die in der folgenden Tabelle aufgeführten Attribute konfigurieren die Ablaufverfolgungsausgabe.  
  
|Attributname|Attributwert|  
|--------------------|---------------------|  
|`Value`|Erforderliches <xref:System.String>-Attribut. Legt den Ausführlichkeitsgrad der Ausgabe fest. Zulässige Werte sind `Critical`, `Error`, `Verbose`, `Warning` und `Information`.<br /><br /> Dieses Attribut muss für das Element \<add name> des \<switches>-Elements wie im Beispiel festgelegt werden. Eine Ausnahme wird ausgelöst, wenn das Attribut für das \<source>-Element festgelegt wird.|  
|`maxdatasize`|Optionales <xref:System.Int32>-Attribut. Legt die maximale Anzahl von Netzwerkdatenbytes für jede Ablaufverfolgungszeile fest. Der Standardwert ist 1024.<br /><br /> Dieses Attribut muss für das Element \<source> wie im Beispiel festgelegt werden. Eine Ausnahme wird ausgelöst, wenn dieses Attribut für ein Element unter dem \<switches>-Element festgelegt wird.|  
|`Tracemode`|Optionales <xref:System.String>-Attribut. Mit dem Wert `includehex` werden Protokollablaufverfolgungen im Hexadezimalformat und im Textformat angezeigt. Mit dem Wert `protocolonly` wird nur Text angezeigt. Der Standardwert ist `includehex`.<br /><br /> Dieses Attribut muss für das Element \<switches> wie im Beispiel festgelegt werden. Eine Ausnahme wird ausgelöst, wenn dieses Attribut für ein Element unter dem \<source>-Element festgelegt wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Interpretieren von Netzwerkablaufverfolgung](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [Netzwerkablaufverfolgung in .NET Framework](../../../docs/framework/network-programming/network-tracing.md)  
 [Aktivieren der Netzwerkablaufverfolgung](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [Einführung in Instrumentation und Ablaufverfolgung](http://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
