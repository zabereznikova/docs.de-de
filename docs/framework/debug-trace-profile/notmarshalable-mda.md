---
title: "notMarshalable MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), interface pointer not marshalable"
  - "interface pointer not marshalable MDA"
  - "MDAs (managed debugging assistants), interface pointer not marshalable"
  - "marshaling, run-time errors"
  - "managed debugging assistants (MDAs), marshaling"
  - "marshalable interface pointers"
  - "MDAs (managed debugging assistants), marshaling"
  - "notMarshalable MDA"
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# notMarshalable MDA
Der `notMarshalable`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn die Common Language Runtime \(CLR\) beim Versuch, eine Schnittstelle über Kontexte hinweg zu marshallen, einen COM\-Schnittstellenzeiger ohne gültigen registrierten Proxy\/Stub oder eine nicht ordnungsgemäß implementierte `IMarshal`\-Schnittstelle erkennt.  
  
## Symptome  
 Aufrufe werden nicht abgewickelt, oder Aufrufe treten im falschen Kontext für COM\-Schnittstellenzeiger auf.  
  
## Ursache  
 Beim Versuch, die Schnittstelle über Kontexte hinweg zu marshallen, wurde kein gültiger registrierter Proxy\/Stub oder eine fehlerhafte `IMarshal`\-Schnittstelle erkannt.  
  
## Lösung  
 Stellen Sie sicher, dass ein Proxy\/Stub registriert ist und die `IMarshal`\-Implementierung gültig ist.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die Laufzeit.  
  
## Ausgabe  
 Eine Meldung mit einer Beschreibung des Problems.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)