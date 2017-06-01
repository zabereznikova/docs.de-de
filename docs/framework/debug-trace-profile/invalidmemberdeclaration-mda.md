---
title: "invalidMemberDeclaration MDA | Microsoft Docs"
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
  - "invalid member declaration"
  - "InvalidMemberDeclaration MDA"
  - "marshaling, run-time errors"
  - "managed debugging assistants (MDAs), marshaling"
  - "MDAs (managed debugging assistants), marshaling"
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# invalidMemberDeclaration MDA
Der `invalidMemberDeclaration`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, um einen Fehler zu melden, der aufgetreten ist, als ermittelt werden sollte, wie das Marshalling für die Parameter eines Members zu erfolgen hat, das aus COM aufgerufen werden soll.  
  
## Symptome  
 Es wird ein Fehler\-HRESULT an COM zurückgegeben, ohne dass die verwaltete Methode aufgerufen wurde.  
  
## Ursache  
 Dies wird höchstwahrscheinlich durch ein inkompatibles <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut für einen der Parameter verursacht.  
  
## Auflösung  
 Geben Sie gültige <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribute für die Parameter an.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## Ausgabe  
 Eine Informationsmeldung, die den Membernamen, den Typnamen und die Fehlermeldung enthält.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)