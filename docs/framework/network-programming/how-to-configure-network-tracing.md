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
ms.openlocfilehash: 3c9550bf9d3483a8d2961e6137138bfb11f71bca
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45610066"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="4ae3e-102">Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4ae3e-102">How to: Configure Network Tracing</span></span>
<span data-ttu-id="4ae3e-103">Die Anwendungs- oder Computerkonfigurationsdatei enthält die Einstellungen, die das Format und die Inhalte von Netzwerkablaufverfolgungen bestimmen.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="4ae3e-104">Bevor Sie diese Verfahren ausführen, stellen Sie sicher, dass die Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="4ae3e-105">Weitere Informationen zur Aktivierung der Netzwerkablaufverfolgung finden Sie unter [Enabling Network Tracing (Aktivieren der Netzwerkablaufverfolgung)](../../../docs/framework/network-programming/enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="4ae3e-105">For information about enabling tracing, see [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md).</span></span>  
  
 <span data-ttu-id="4ae3e-106">Die Computerkonfigurationsdatei "machine.config" ist im Ordner "%Windir%\Microsoft.NET\Framework" in dem Verzeichnis gespeichert, in dem Windows installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-106">The computer configuration file, machine.config, is stored in the %Windir%\Microsoft.NET\Framework folder in the directory where Windows was installed.</span></span> <span data-ttu-id="4ae3e-107">Es gibt für jede Version von .NET Framework, die auf dem Computer installiert ist, eine eigene machine.config-Datei in den Unterordnern von %Windir%\Microsoft.NET\Framework (z.B. C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config oder C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config).</span><span class="sxs-lookup"><span data-stu-id="4ae3e-107">There is a separate machine.config file in the folders under %Windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer (for example, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config or C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span></span>  
  
 <span data-ttu-id="4ae3e-108">Diese Einstellungen können auch in der Konfigurationsdatei für die Anwendung vorgenommen werden. Die Anwendungskonfigurationsdatei hat Vorrang vor der Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-108">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
### <a name="to-configure-network-tracing"></a><span data-ttu-id="4ae3e-109">So konfigurieren Sie die Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4ae3e-109">To configure network tracing</span></span>  
  
-   <span data-ttu-id="4ae3e-110">Fügen Sie der jeweiligen Konfigurationsdatei die folgenden Zeilen hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-110">Add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="4ae3e-111">Die Werte und Optionen für diese Einstellungen sind in den folgenden Tabellen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-111">The values and options for these settings are described in the tables below.</span></span>  
  
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
  
 <span data-ttu-id="4ae3e-112">Wenn Sie einen Namen im `<switches>`-Block hinzufügen, enthält die Ausgabe der Ablaufverfolgung Informationen von einigen zu diesem Namen gehörenden Methoden.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-112">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="4ae3e-113">Die Ausgabe wird in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-113">The following table describes the output.</span></span>  
  
|<span data-ttu-id="4ae3e-114">name</span><span class="sxs-lookup"><span data-stu-id="4ae3e-114">Name</span></span>|<span data-ttu-id="4ae3e-115">Ausgabe von</span><span class="sxs-lookup"><span data-stu-id="4ae3e-115">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="4ae3e-116">Einige öffentliche Methoden der Klassen <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> und <xref:System.Net.Dns></span><span class="sxs-lookup"><span data-stu-id="4ae3e-116">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes</span></span>|  
|`System.Net`|<span data-ttu-id="4ae3e-117">Einige öffentliche Methoden der Klassen <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> sowie SSL-Debuginformationen (Ungültige Zertifikate, fehlende Ausstellerliste und Clientzertifikatsfehler.)</span><span class="sxs-lookup"><span data-stu-id="4ae3e-117">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors.)</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="4ae3e-118">Einige öffentliche Methoden der Klassen <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> und <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-118">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="4ae3e-119">Einige private und interne Methoden in `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-119">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="4ae3e-120">Einige öffentliche Methoden der Klassen <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> und <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-120">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="4ae3e-121">Einige öffentliche Methoden der Klassen <xref:System.Net.WebSockets.ClientWebSocket> und <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-121">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  
  
 <span data-ttu-id="4ae3e-122">Die in der folgenden Tabelle aufgeführten Attribute konfigurieren die Ablaufverfolgungsausgabe.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-122">The attributes listed in the following table configure trace output.</span></span>  
  
|<span data-ttu-id="4ae3e-123">Attributname</span><span class="sxs-lookup"><span data-stu-id="4ae3e-123">Attribute name</span></span>|<span data-ttu-id="4ae3e-124">Attributwert</span><span class="sxs-lookup"><span data-stu-id="4ae3e-124">Attribute value</span></span>|  
|--------------------|---------------------|  
|`Value`|<span data-ttu-id="4ae3e-125">Erforderliches <xref:System.String>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-125">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="4ae3e-126">Legt den Ausführlichkeitsgrad der Ausgabe fest.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-126">Sets the verbosity of the output.</span></span> <span data-ttu-id="4ae3e-127">Zulässige Werte sind `Critical`, `Error`, `Verbose`, `Warning` und `Information`.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-127">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /> <span data-ttu-id="4ae3e-128">Dieses Attribut muss für das Element \<add name> des \<switches>-Elements wie im Beispiel festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-128">This attribute must be set on the \<add name> element of the \<switches> element as shown in the example.</span></span> <span data-ttu-id="4ae3e-129">Eine Ausnahme wird ausgelöst, wenn das Attribut für das \<source>-Element festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-129">An exception is thrown if this attribute is set on the \<source> element.</span></span>|  
|`maxdatasize`|<span data-ttu-id="4ae3e-130">Optionales <xref:System.Int32>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-130">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="4ae3e-131">Legt die maximale Anzahl von Netzwerkdatenbytes für jede Ablaufverfolgungszeile fest.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-131">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="4ae3e-132">Der Standardwert ist 1024.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-132">The default value is 1024.</span></span><br /><br /> <span data-ttu-id="4ae3e-133">Dieses Attribut muss für das Element \<source> wie im Beispiel festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-133">This attribute must be set on the \<source> element as shown in the example.</span></span> <span data-ttu-id="4ae3e-134">Eine Ausnahme wird ausgelöst, wenn dieses Attribut für ein Element unter dem \<switches>-Element festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-134">An exception is thrown if this attribute is set on an element under the \<switches> element.</span></span>|  
|`Tracemode`|<span data-ttu-id="4ae3e-135">Optionales <xref:System.String>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-135">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="4ae3e-136">Mit dem Wert `includehex` werden Protokollablaufverfolgungen im Hexadezimalformat und im Textformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-136">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="4ae3e-137">Mit dem Wert `protocolonly` wird nur Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-137">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="4ae3e-138">Der Standardwert ist `includehex`.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-138">The default value is `includehex`.</span></span><br /><br /> <span data-ttu-id="4ae3e-139">Dieses Attribut muss für das Element \<switches> wie im Beispiel festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-139">This attribute must be set on the \<switches> element as shown in the example.</span></span> <span data-ttu-id="4ae3e-140">Eine Ausnahme wird ausgelöst, wenn dieses Attribut für ein Element unter dem \<source>-Element festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4ae3e-140">An exception is thrown if this attribute is set on an element under the \<source> element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4ae3e-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ae3e-141">See Also</span></span>  
 [<span data-ttu-id="4ae3e-142">Interpretieren von Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4ae3e-142">Interpreting Network Tracing</span></span>](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [<span data-ttu-id="4ae3e-143">Netzwerkablaufverfolgung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4ae3e-143">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)  
 [<span data-ttu-id="4ae3e-144">Aktivieren der Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4ae3e-144">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [<span data-ttu-id="4ae3e-145">Einführung in Instrumentation und Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4ae3e-145">Introduction to Instrumentation and Tracing</span></span>](https://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
