---
title: Interpretieren von Netzwerkablaufverfolgung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: deb191f18bda5b00ef4a967f50e8e983289882a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="interpreting-network-tracing"></a><span data-ttu-id="5f4ca-102">Interpretieren von Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="5f4ca-102">Interpreting Network Tracing</span></span>
<span data-ttu-id="5f4ca-103">Wenn die Netzwerkablaufverfolgung aktiviert ist, können Sie die Ablaufverfolgung zum Erfassen von Aufrufen durch Ihre Anwendung an verschiedene <xref:System.Net>-Klassenmember verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-103">When network tracing is enabled, you can use tracing to capture calls your application makes to various <xref:System.Net> class members.</span></span> <span data-ttu-id="5f4ca-104">Die Ausgabe dieser Aufrufe ähnelt möglicherweise den folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-104">The output from these calls may be similar to the following examples.</span></span>  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 <span data-ttu-id="5f4ca-105">Im vorhergehenden Beispiel ist [588] der eindeutige Bezeichner des aktuellen Threads.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-105">In the preceding example, [588] is the current thread's unique identifier.</span></span> <span data-ttu-id="5f4ca-106">(4357) und (4387) sind Zeitstempel, die die Anzahl der Millisekunden seit dem Anwendungsstart angeben.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-106">(4357) and (4387) are timestamps denoting the number of milliseconds that have elapsed since the application started.</span></span> <span data-ttu-id="5f4ca-107">Die Daten nach dem Zeitstempel geben an, dass die Methode **Socket.Send** von der Anwendung betreten und beendet wird.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-107">The data following the timestamp shows the application entering and exiting the method **Socket.Send**.</span></span> <span data-ttu-id="5f4ca-108">Das Objekt, das die Methode **Send** ausführt, besitzt „33574638“ als eindeutigen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-108">The object executing the **Send** method has 33574638 as its unique identifier.</span></span> <span data-ttu-id="5f4ca-109">Die Ablaufverfolgung zum Beenden der Methode enthält den Rückgabewert (im vorherigen Beispiel 61).</span><span class="sxs-lookup"><span data-stu-id="5f4ca-109">The method exit trace includes the return value (61 in the preceding example).</span></span>  
  
 <span data-ttu-id="5f4ca-110">Netzwerkablaufverfolgungen können Netzwerkdatenverkehr erfassen, der mithilfe von Protokollen auf Anwendungsebene, wie z.B. HTTP (Hypertext Transfer Protocol), von der Anwendung gesendet oder empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-110">Network traces can capture network traffic that is sent from or received by your application using application-level protocols such as Hypertext Transfer Protocol (HTTP).</span></span> <span data-ttu-id="5f4ca-111">Diese Daten können als Text und optional als hexadezimale Daten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-111">This data can be captured as text and, optionally, hexadecimal data.</span></span> <span data-ttu-id="5f4ca-112">Hexadezimale Daten sind verfügbar, wenn **includehex** als Wert des Attributs **tracemode** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-112">Hexadecimal data is available when you specify **includehex** as the value of the **tracemode** attribute.</span></span> <span data-ttu-id="5f4ca-113">(Ausführliche Informationen zu diesem Attribut finden Sie unter [How to: Configure Network Tracing (Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung)](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).) Das folgende Beispiel für eine Ablaufverfolgung wurde mit **includehex** generiert.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-113">(For detailed information about this attribute, see [How to: Configure Network Tracing](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).) The following example trace was generated using **includehex**.</span></span>  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 <span data-ttu-id="5f4ca-114">Geben Sie **protocolonly** als Wert des Attributs **tracemode** an, um die hexadezimalen Daten auszulassen.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-114">To omit hexadecimal data, specify **protocolonly** as the value for the **tracemode** attribute.</span></span> <span data-ttu-id="5f4ca-115">Das folgende Beispiel zeigt die Ablaufverfolgung für **protocolonly**.</span><span class="sxs-lookup"><span data-stu-id="5f4ca-115">The following example shows the trace when **protocolonly** is specified.</span></span>  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a><span data-ttu-id="5f4ca-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f4ca-116">See Also</span></span>  
 [<span data-ttu-id="5f4ca-117">Aktivieren der Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="5f4ca-117">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [<span data-ttu-id="5f4ca-118">Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="5f4ca-118">How to: Configure Network Tracing</span></span>](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)  
 [<span data-ttu-id="5f4ca-119">Netzwerkablaufverfolgung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5f4ca-119">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)
