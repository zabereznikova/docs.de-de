---
title: reportAvOnComRelease-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
caps.latest.revision: 15
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d60b63977e8e05cfdb1103a2571ba8d986b98fbf
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="reportavoncomrelease-mda"></a>reportAvOnComRelease-MDA
Der `reportAvOnComRelease`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn aufgrund von Fehlern bei der Benutzerverweiszählung Ausnahmen ausgelöst werden, während COM-Interop durchgeführt und die <xref:System.Runtime.InteropServices.Marshal.Release%2A>- oder die <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A>-Methode in Kombination mit Rohdaten-COM-Aufrufen verwendet wird.  
  
## <a name="symptoms"></a>Symptome  
 Zugriffsverletzungen und Speicherschäden.  
  
## <a name="cause"></a>Ursache  
 Es kann vorkommen, dass durch Fehler bei der Benutzerverweiszählung eine Ausnahme ausgelöst wird, während COM-Interop durchgeführt und die <xref:System.Runtime.InteropServices.Marshal.Release%2A>- oder die <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A>-Methode in Kombination mit Rohdaten-COM-Aufrufen verwendet wird. Normalerweise wird diese Ausnahme verworfen, da es andernfalls zu einer Zugriffsverletzung in der CLR kommen kann, wodurch diese beendet wird. Ist dieser Assistent aktiviert, können solche Ausnahmen festgestellt und gemeldet werden, anstatt sie einfach zu verwerfen.  
  
## <a name="resolution"></a>Lösung  
 Überprüfen Sie den Verweiszählungscode und prüfen Sie auch die systemeigenen Clients Ihres Objekts auf Fehler bei der Verweiszählung.  
  
## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit  
 Es sind zwei Modi verfügbar. Ist das `allowAv`-Attribut `true`, verhindert der Assistent, dass die Laufzeit die Zugriffsverletzung verwirft. Hat `allowAv` den Standardwert `false`, verwirft die Laufzeit die Zugriffsverletzung und der Benutzer erhält die Warnmeldung, dass eine Ausnahme ausgelöst und verworfen wurde.  
  
## <a name="output"></a>Ausgabe  
 Wenn möglich, enthält die Ausgabe den ursprünglichen vtable des COM-Schnittstellenzeigers. Andernfalls wird eine Informationsmeldung angezeigt.  
  
## <a name="configuration"></a>Konfiguration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop-Marshalling](../../../docs/framework/interop/interop-marshaling.md)

