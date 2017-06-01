---
title: "reportAvOnComRelease MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), reference counting errors"
  - "exceptions, reference counting errors"
  - "ReportAvOnComRelease MDA"
  - "COM release access violations"
  - "user reference counting errors"
  - "managed debugging assistants (MDAs), reference counting errors"
  - "report access violation on Com release"
  - "reference counting errors"
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# reportAvOnComRelease MDA
Der `reportAvOnComRelease`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn aufgrund von Fehlern bei der Benutzerverweiszählung Ausnahmen ausgelöst werden, während COM\-Interop durchgeführt und die <xref:System.Runtime.InteropServices.Marshal.Release%2A>\- oder die <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A>\-Methode in Kombination mit Rohdaten\-COM\-Aufrufen verwendet wird.  
  
## Symptome  
 Zugriffsverletzungen und Speicherschäden.  
  
## Ursache  
 Es kann vorkommen, dass durch Fehler bei der Benutzerverweiszählung eine Ausnahme ausgelöst wird, während COM\-Interop durchgeführt und die <xref:System.Runtime.InteropServices.Marshal.Release%2A>\- oder die <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A>\-Methode in Kombination mit Rohdaten\-COM\-Aufrufen verwendet wird.  Normalerweise wird diese Ausnahme verworfen, da es andernfalls zu einer Zugriffsverletzung in der CLR kommen kann, wodurch diese beendet wird.  Ist dieser Assistent aktiviert, können solche Ausnahmen festgestellt und gemeldet werden, anstatt sie einfach zu verwerfen.  
  
## Lösung  
 Überprüfen Sie den Verweiszählungscode und prüfen Sie auch die systemeigenen Clients Ihres Objekts auf Fehler bei der Verweiszählung.  
  
## Auswirkungen auf die Laufzeit  
 Es sind zwei Modi verfügbar.  Ist das `allowAv`\-Attribut `true`, verhindert der Assistent, dass die Laufzeit die Zugriffsverletzung verwirft.  Hat `allowAv` den Standardwert `false`, verwirft die Laufzeit die Zugriffsverletzung und der Benutzer erhält die Warnmeldung, dass eine Ausnahme ausgelöst und verworfen wurde.  
  
## Ausgabe  
 Wenn möglich, enthält die Ausgabe den ursprünglichen vtable des COM\-Schnittstellenzeigers.  Andernfalls wird eine Informationsmeldung angezeigt.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)