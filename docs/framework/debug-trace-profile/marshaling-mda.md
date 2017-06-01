---
title: "marshaling MDA | Microsoft Docs"
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
  - "marshaling, run-time errors"
  - "marshaling MDA"
  - "managed debugging assistants (MDAs), marshaling"
  - "MDAs (managed debugging assistants), marshaling"
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# marshaling MDA
Der `marshaling`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn die CLR Marshallinginformationen für einen Methodenparameter oder das Feld einer Struktur einrichtet.  Dieser MDA funktioniert nicht mit JIT\-kompilierten Assemblys.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## Ausgabe  
 Der MDA zeigt den Typ des Parameters bzw. Felds in den verwalteten und nicht verwalteten Kontexten sowie die Struktur bzw. Methode an, die diesen Typ enthält.  Das Folgende ist ein Beispiel für die Ausgabe für ein Feld:  
  
```  
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## Konfiguration  
 Durch Konfigurieren des MDA können Sie die gemeldeten Marshallinginformationen anhand der betroffenen Feld\- oder Methodennamen filtern.  Im folgenden Beispiel wird gezeigt, wie die Elemente `methodFilter`, `fieldFilter` und `match` verwendet werden, um Filter anzugeben.  Wird das `name`\-Attribut auf ein Sternchen \(\*\) festgelegt, werden alle Namen erfasst.  
  
```  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)