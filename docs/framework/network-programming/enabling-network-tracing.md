---
title: "Aktivieren der Netzwerkablaufverfolgung | Microsoft Docs"
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
  - "Ablaufverfolgungsziele"
  - "Senden von Ablaufverfolgungen an eine Protokolldatei"
  - "Ablaufverfolgungslistener, Netzwerkablaufverfolgung"
  - "Netzwerkablaufverfolgung, aktivieren"
  - "CLR Debugger"
  - "Standardlistener"
  - "Protokolle, Ablaufverfolgung"
  - "Ziel für Ablaufverfolgungsausgabe"
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Aktivieren der Netzwerkablaufverfolgung
Netzwerkablaufverfolgung bietet Zugriff auf Informationen über Methodenaufrufe und den Netzwerkverkehr, der von einer Anwendung generiert wird.  Sie müssen die folgenden Aufgaben ausführen, können in der Anwendung zu aktivieren:  
  
-   Kompilieren Sie den Code mit aktivierter Ablaufverfolgung.  Siehe [How to: Compile Conditionally with Trace and Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) weitere Informationen über die Compilerschalter, die erforderlich sind, um die Ablaufverfolgung zu aktivieren.  
  
-   Geben Sie ein Ziel für Ablaufverfolgungsausgabe an.  
  
-   Konfigurieren Sie das Verhalten der Netzwerkablaufverfolgung.  Siehe [Gewusst wie: Konfigurieren Sie Netzwerkablaufverfolgung](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) detaillierte Informationen.  
  
 Die meisten allgemeinen Ablaufverfolgungsziele, auch bezeichnet als Ablaufverfolgungslistener, werden standardmäßig Listener und die Protokolldatei.  
  
 Die Ablaufverfolgung mithilfe der standardmäßigen Listener, wenn Sie keinen Ablaufverfolgungslistener angeben.  Sie können die Meldungen, die auf dem Listener, gesendet werden, indem Sie den Code in einem verwalteten Code\-aktivierten Debugger wie dem CLR\-Debugger ausführen, der mit dem .NET Framework SDK ausgeliefert wird, oder DBwin32.exe anzeigen, das mit dem Windows SDK enthalten.  Verwenden des CLR\-Debuggers werden die Ablaufverfolgungsmeldungen **Ausgabe** im Fenster.  
  
 Wenn Sie es vorziehen, eine Datei zu verwenden, um Ablaufverfolgungen zu erhalten, können Sie eine Protokolldatei angeben, indem Sie Konfigurationseinstellungen, wie im folgenden Beispiel dargestellt.  \(Eine allgemeine Erläuterung Konfigurationsdateien, finden Sie unter [Konfigurationsdateien](../../../docs/framework/configure-apps/index.md).\)  
  
 Um Ablaufverfolgungen in eine Protokolldatei zu senden, fügen Sie den folgenden Knoten dem `<system.diagnostics>` Knoten der entsprechenden Konfigurationsdatei hinzu \(Anwendung oder Computer\).  Sie können den Namen der Datei \(trace.log\) ändern die jeweiligen Anforderungen anzupassen.  
  
```  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## Siehe auch  
 [Interpretieren von Netzwerkablaufverfolgung](../../../docs/framework/network-programming/interpreting-network-tracing.md)   
 [Netzwerkablaufverfolgung in .NET Framework](../../../docs/framework/network-programming/network-tracing.md)   
 [Introduction to Instrumentation and Tracing](http://msdn.microsoft.com/de-de/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)