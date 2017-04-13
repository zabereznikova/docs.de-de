---
title: "invalidVariant MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid variant"
  - "VARIANT type errors"
  - "InvalidVariant MDA"
  - "invalid VARIANT types"
  - "managed debugging assistants (MDAs), invalid variant"
ms.assetid: d273e070-d1b1-4a53-a9c7-7af837b04a3d
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# invalidVariant MDA
Der Assistent für verwaltetes Debugging \(MDA\) `invalidVariant` wird aktiviert, wenn während eines Aufrufs aus systemeigenem oder unverwaltetem Code an verwalteten Code eine ungültige `VARIANT`\-Struktur erkannt wird.  
  
## Symptome  
 Unerwartetes Verhalten während eines Übergangs zwischen systemeigenem und verwaltetem Code, das das Marshalling eines `VARIANT` an ein Objekt einbezieht.  
  
## Ursache  
 Systemeigener Code übergibt eine fehlerhafte `VARIANT`\-Struktur an verwalteten Code.  Zur Laufzeit wird versucht, diesen `VARIANT` an ein Objekt zu marshallen, und der MDA wird aktiviert, wenn der `VARIANT` ungültig ist.  Beispiele für ungültige `VARIANT`S sind unter anderem ein `VARIANT` mit dem `VARTYPE` VT\_EMPTY &#124; VT\_BYREF oder ein `VARIANT` mit dem `VARTYPE` VT\_VARIANT.  
  
## Lösung  
 Der systemeigene oder unverwaltete Code, der den `VARIANT` übergibt, muss sicherstellen, dass der `VARIANT` korrekt geformt und initialisiert ist.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die Laufzeit.  
  
## Ausgabe  
 Eine MDA\-Meldung, die angibt, dass zur Laufzeit ein ungültiger `VARIANT` erkannt wurde, der von einem unverwalteten Modul an verwalteten Code übergeben wurde.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidVariant />  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)