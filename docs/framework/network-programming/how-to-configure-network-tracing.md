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
ms.openlocfilehash: 06132509860b16d1e22cfdf7e3226c968d16b7cf
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040644"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="63815-102">Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="63815-102">How to: Configure network tracing</span></span>

<span data-ttu-id="63815-103">Die Anwendungs- oder Computerkonfigurationsdatei enthält die Einstellungen, die das Format und die Inhalte von Netzwerkablaufverfolgungen bestimmen.</span><span class="sxs-lookup"><span data-stu-id="63815-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="63815-104">Bevor Sie diese Verfahren ausführen, stellen Sie sicher, dass die Ablaufverfolgung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="63815-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="63815-105">Weitere Informationen finden Sie unter [Aktivieren der Netzwerkablaufverfolgung](enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="63815-105">For more information, see [Enable network tracing](enabling-network-tracing.md).</span></span>

<span data-ttu-id="63815-106">Die Computerkonfigurationsdatei *machine.config* wird im Ordner *%windir%\Microsoft.NET\Framework* gespeichert.</span><span class="sxs-lookup"><span data-stu-id="63815-106">The computer configuration file, *machine.config*, is stored in the *%windir%\Microsoft.NET\Framework* folder.</span></span> <span data-ttu-id="63815-107">Es gibt für jede Version von .NET Framework, die auf dem Computer installiert ist, eine eigene *machine.config*-Datei in den Unterordnern von *%windir%\Microsoft.NET\Framework*, z. B.:</span><span class="sxs-lookup"><span data-stu-id="63815-107">There is a separate *machine.config* file in the folders under *%windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer, for example:</span></span>

- <span data-ttu-id="63815-108">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="63815-108">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span></span>
- <span data-ttu-id="63815-109">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="63815-109">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span></span>

<span data-ttu-id="63815-110">Diese Einstellungen können auch in der Konfigurationsdatei für die Anwendung vorgenommen werden. Die Anwendungskonfigurationsdatei hat Vorrang vor der Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="63815-110">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>

## <a name="configure-network-tracing"></a><span data-ttu-id="63815-111">Konfigurieren der Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="63815-111">Configure network tracing</span></span>

<span data-ttu-id="63815-112">Fügen Sie der jeweiligen Konfigurationsdatei die folgenden Zeilen hinzu, um die Netzwerkablaufverfolgung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="63815-112">To configure network tracing, add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="63815-113">Die Werte und Optionen für diese Einstellungen sind in den folgenden Tabellen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="63815-113">The values and options for these settings are described in the tables below.</span></span>

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
        traceOutputOptions="ProcessId, DateTime"
      />
    </sharedListeners>
    <trace autoflush="true"/>
  </system.diagnostics>
</configuration>
```

### <a name="trace-output-from-methods"></a><span data-ttu-id="63815-114">Ablaufverfolgungsausgabe von Methoden</span><span class="sxs-lookup"><span data-stu-id="63815-114">Trace output from methods</span></span>

<span data-ttu-id="63815-115">Wenn Sie einen Namen im `<switches>`-Block hinzufügen, enthält die Ausgabe der Ablaufverfolgung Informationen von einigen zu diesem Namen gehörenden Methoden.</span><span class="sxs-lookup"><span data-stu-id="63815-115">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="63815-116">Die Ausgabe wird in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="63815-116">The following table describes the output:</span></span>

|<span data-ttu-id="63815-117">name</span><span class="sxs-lookup"><span data-stu-id="63815-117">Name</span></span>|<span data-ttu-id="63815-118">Ausgabe von</span><span class="sxs-lookup"><span data-stu-id="63815-118">Output from</span></span>|
|----------|-----------------|
|`System.Net.Sockets`|<span data-ttu-id="63815-119">Einige öffentliche Methoden der Klassen <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> und <xref:System.Net.Dns>.</span><span class="sxs-lookup"><span data-stu-id="63815-119">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes.</span></span>|
|`System.Net`|<span data-ttu-id="63815-120">Einige öffentliche Methoden der Klassen <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> sowie SSL-Debuginformationen (ungültige Zertifikate, fehlende Ausstellerliste und Clientzertifikatsfehler).</span><span class="sxs-lookup"><span data-stu-id="63815-120">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors).</span></span>|
|`System.Net.HttpListener`|<span data-ttu-id="63815-121">Einige öffentliche Methoden der Klassen <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> und <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="63815-121">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|
|`System.Net.Cache`|<span data-ttu-id="63815-122">Einige private und interne Methoden in `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="63815-122">Some private and internal methods in `System.Net.Cache`.</span></span>|
|`System.Net.Http`|<span data-ttu-id="63815-123">Einige öffentliche Methoden der Klassen <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>, <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> und <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="63815-123">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="63815-124">Einige öffentliche Methoden der Klassen <xref:System.Net.WebSockets.ClientWebSocket> und <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="63815-124">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|

### <a name="trace-output-attributes"></a><span data-ttu-id="63815-125">Attribute der Ablaufverfolgungsausgabe</span><span class="sxs-lookup"><span data-stu-id="63815-125">Trace output attributes</span></span>

<span data-ttu-id="63815-126">Die in der folgenden Tabelle aufgeführten Attribute konfigurieren die Ablaufverfolgungsausgabe:</span><span class="sxs-lookup"><span data-stu-id="63815-126">The attributes listed in the following table configure trace output:</span></span>

|<span data-ttu-id="63815-127">Attributname</span><span class="sxs-lookup"><span data-stu-id="63815-127">Attribute name</span></span>|<span data-ttu-id="63815-128">Attributwert</span><span class="sxs-lookup"><span data-stu-id="63815-128">Attribute value</span></span>|
|--------------------|---------------------|
|`value`|<span data-ttu-id="63815-129">Erforderliches <xref:System.String>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="63815-129">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="63815-130">Legt den Ausführlichkeitsgrad der Ausgabe fest.</span><span class="sxs-lookup"><span data-stu-id="63815-130">Sets the verbosity of the output.</span></span> <span data-ttu-id="63815-131">Zulässige Werte sind `Critical`, `Error`, `Verbose`, `Warning` und `Information`.</span><span class="sxs-lookup"><span data-stu-id="63815-131">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /><span data-ttu-id="63815-132">Dieses Attribut muss für das Element **Hinzufügen** des Elements **switches** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="63815-132">This attribute must be set on the **add** element of the **switches** element.</span></span> <span data-ttu-id="63815-133">Eine Ausnahme wird ausgelöst, wenn das Attribut für das Element **source** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="63815-133">An exception is thrown if this attribute is set on the **source** element.</span></span><br/><br/><span data-ttu-id="63815-134">Ein Beispiel: `<add name="System.Net" value="Verbose"/>`</span><span class="sxs-lookup"><span data-stu-id="63815-134">Example: `<add name="System.Net" value="Verbose"/>`</span></span>|
|`maxdatasize`|<span data-ttu-id="63815-135">Optionales <xref:System.Int32>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="63815-135">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="63815-136">Legt die maximale Anzahl von Netzwerkdatenbytes für jede Ablaufverfolgungszeile fest.</span><span class="sxs-lookup"><span data-stu-id="63815-136">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="63815-137">Der Standardwert ist 1024.</span><span class="sxs-lookup"><span data-stu-id="63815-137">The default value is 1024.</span></span><br /><br /><span data-ttu-id="63815-138">Dieses Attribut muss für das Element **Quelle** wie im Beispiel festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="63815-138">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="63815-139">Eine Ausnahme wird ausgelöst, wenn dieses Attribut für ein Element unter dem Element **switches** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="63815-139">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="63815-140">Ein Beispiel: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="63815-140">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|
|`tracemode`|<span data-ttu-id="63815-141">Optionales <xref:System.String>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="63815-141">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="63815-142">Mit dem Wert `includehex` werden Protokollablaufverfolgungen im Hexadezimalformat und im Textformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63815-142">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="63815-143">Mit dem Wert `protocolonly` wird nur Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63815-143">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="63815-144">Der Standardwert ist `includehex`sein.</span><span class="sxs-lookup"><span data-stu-id="63815-144">The default value is `includehex`.</span></span><br /><br /><span data-ttu-id="63815-145">Dieses Attribut muss für das Element **Quelle** wie im Beispiel festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="63815-145">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="63815-146">Eine Ausnahme wird ausgelöst, wenn dieses Attribut für ein Element unter dem Element **switches** festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="63815-146">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="63815-147">Ein Beispiel: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="63815-147">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|

## <a name="see-also"></a><span data-ttu-id="63815-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63815-148">See also</span></span>

- [<span data-ttu-id="63815-149">Interpretieren von Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="63815-149">Interpreting Network Tracing</span></span>](interpreting-network-tracing.md)
- [<span data-ttu-id="63815-150">Netzwerkablaufverfolgung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="63815-150">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
- [<span data-ttu-id="63815-151">Aktivieren der Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="63815-151">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="63815-152">Ablaufverfolgung und Instrumentieren von Anwendungen</span><span class="sxs-lookup"><span data-stu-id="63815-152">Tracing and Instrumenting Applications</span></span>](../debug-trace-profile/tracing-and-instrumenting-applications.md)
