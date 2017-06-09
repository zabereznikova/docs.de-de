---
title: "Interpretieren von Netzwerkablaufverfolgung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "TraceMode-Attribut"
  - "Hexadezimale Daten, Netzwerkablaufverfolgungsausgabe"
  - "Netzwerkablaufverfolgung, Analysieren"
  - "protocolonly"
  - "Text, Netzwerkablaufverfolgungsausgabe"
  - "includehex"
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Interpretieren von Netzwerkablaufverfolgung
Wenn Netzwerkablaufverfolgung aktiviert ist, können Sie die Ablaufverfolgung verwenden, um Aufrufe aufzuzeichnen, die die Anwendung verschiedenem <xref:System.Net>\-Klassenmember erstellt wird.  Die Ausgabe von diesen Aufrufen kann in den folgenden Beispielen ähnlich.  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 Im vorherigen Beispiel \[588\] ist der aktuelle eindeutige Bezeichner des Threads.  \(4357\) und \(4387\) sind die Timestamps, die die Anzahl von Millisekunden anzugeben, die abgelaufen sind, seit die Anwendung gestartet hat.  Die Daten, die dem Timestamp folgen, zeigen die Anwendung an, die die Methode **Socket.Send** eingibt und beendet.  Das Objekt, das die **Send**\-Methode ausführt, hat 33574638 als eindeutiger Bezeichner.  Die Methodenbeendigungsablaufverfolgung schließt den Rückgabewert \(61 im vorhergehenden Beispiel\).  
  
 Netzwerkablaufverfolgungen können Netzwerkverkehr aufzeichnen, dem von gesendet wird oder durch die Anwendung mithilfe der Protokolle auf Anwendungsebene wie HTTP \(Hypertext Transfer Protocol\) empfangen.  Diese Daten können als Text und hexadezimale Daten optional aufgezeichnet werden.  Hexadezimale Daten verfügbar sind, wenn Sie **includehex** als Wert des **tracemode**\-Attributs angeben.  \(Ausführliche Informationen zu diesem Attribut, finden Sie unter [Gewusst wie: Konfigurieren Sie Netzwerkablaufverfolgung](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).\) Die folgende Beispielsablaufverfolgung wurde mit **includehex** generiert.  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 Hexadezimale Daten auszulassen, geben Sie **protocolonly** als Wert für das **tracemode**\-Attribut an.  Im folgenden Beispiel wird die Ablaufverfolgung an, wenn **protocolonly** angegeben wird.  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## Siehe auch  
 [Aktivieren der Netzwerkablaufverfolgung](../../../docs/framework/network-programming/enabling-network-tracing.md)   
 [Gewusst wie: Konfigurieren Sie Netzwerkablaufverfolgung](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)   
 [Netzwerkablaufverfolgung in .NET Framework](../../../docs/framework/network-programming/network-tracing.md)