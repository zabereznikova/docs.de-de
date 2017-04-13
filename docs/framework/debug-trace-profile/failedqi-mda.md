---
title: "failedQI MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "failed QueryInterface"
  - "FailedQI MDA"
  - "QueryInterface call failures"
  - "MDAs (managed debugging assistants), failed QueryInterface"
  - "managed debugging assistants (MDAs), failed QueryInterface"
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# failedQI MDA
Der `failedQI`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn die CLR stellvertretend für einen RCW \(Runtime Callable Wrapper\) `QueryInterface` für einen COM\-Schnittstellenzeiger aufruft und der Aufruf von `QueryInterface` fehlschlägt.  
  
## Symptome  
 Eine Umwandlung für einen RCW schlägt fehl, oder ein Aufruf von COM von einem RCW aus schlägt unerwartet fehl.  
  
## Ursache  
  
-   Der Aufruf erfolgt im falschen Kontext.  
  
-   Der registrierte Proxy kann den Aufruf von `QueryInterface` nicht ausführen, weil der Aufruf im falschen Kontext erfolgte.  
  
-   Ein OLE zugehöriger Proxy hat einen falschen Wert für HRESULT zurückgegeben.  
  
## Auflösung  
 Informationen hierzu finden Sie in der MSDN\-Dokumentation zu COM\-Regeln.  
  
## Auswirkungen auf die Laufzeit  
 Wenn ein Aufruf von `QueryInterface` fehlschlägt, erfolgt ein Kontextwechsel, und der Aufruf von `QueryInterface` wird erneut ausgeführt, um zu ermitteln, ob ein falscher Kontext für das Fehlschlagen verantwortlich war.  
  
## Ausgabe  
 Der verwaltete Name der Schnittstelle, die GUID der Schnittstelle und das HRESULT des Fehlers.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)