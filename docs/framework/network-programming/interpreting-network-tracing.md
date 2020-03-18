---
title: Interpretieren von Netzwerkablaufverfolgung
ms.date: 03/30/2017
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
ms.openlocfilehash: fd617e152b1e86cc71dd8e3cc8a01f1d2f52c30a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047901"
---
# <a name="interpreting-network-tracing"></a>Interpretieren von Netzwerkablaufverfolgung
Wenn die Netzwerkablaufverfolgung aktiviert ist, können Sie die Ablaufverfolgung zum Erfassen von Aufrufen durch Ihre Anwendung an verschiedene <xref:System.Net>-Klassenmember verwenden. Die Ausgabe dieser Aufrufe ähnelt möglicherweise den folgenden Beispielen.  
  
```output
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61
```  
  
 Im vorhergehenden Beispiel ist [588] der eindeutige Bezeichner des aktuellen Threads. (4357) und (4387) sind Zeitstempel, die die Anzahl der Millisekunden seit dem Anwendungsstart angeben. Die Daten nach dem Zeitstempel geben an, dass die Methode **Socket.Send** von der Anwendung betreten und beendet wird. Das Objekt, das die Methode **Send** ausführt, besitzt „33574638“ als eindeutigen Bezeichner. Die Ablaufverfolgung zum Beenden der Methode enthält den Rückgabewert (im vorherigen Beispiel 61).  
  
 Netzwerkablaufverfolgungen können Netzwerkdatenverkehr erfassen, der mithilfe von Protokollen auf Anwendungsebene, wie z.B. HTTP (Hypertext Transfer Protocol), von der Anwendung gesendet oder empfangen wird. Diese Daten können als Text und optional als hexadezimale Daten erfasst werden. Hexadezimale Daten sind verfügbar, wenn **includehex** als Wert des Attributs **tracemode** angegeben wird. (Ausführliche Informationen zu diesem Attribut finden Sie unter [Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung](how-to-configure-network-tracing.md).) Das folgende Beispiel für eine Ablaufverfolgung wurde mit **includehex** generiert.  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 Geben Sie **protocolonly** als Wert des Attributs **tracemode** an, um die hexadezimalen Daten auszulassen. Das folgende Beispiel zeigt die Ablaufverfolgung für **protocolonly**.  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a>Siehe auch

- [Aktivieren der Netzwerkablaufverfolgung](enabling-network-tracing.md)
- [How to: Konfigurieren der Netzwerkablaufverfolgung](how-to-configure-network-tracing.md)
- [Netzwerkablaufverfolgung in .NET Framework](network-tracing.md)
