---
title: "dllMainReturnsFalse MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), DllMain returns false"
  - "DllMainReturnsFalse MDA"
  - "DllMain function"
  - "MDAs (managed debugging assistants), DllMain returns false"
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# dllMainReturnsFalse MDA
Der `dllMainReturnsFalse`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn die mit Grund DLL\_PROCESS\_ATTACH aufgerufene verwaltete `DllMain`\-Funktion einer Benutzerassembly den Wert FALSE zurückgibt.  
  
## Symptome  
 Die `DllMain`\-Funktion gibt FALSE zurück und zeigt damit an, dass die Ausführung nicht ordnungsgemäß abgeschlossen wurde.  Dies kann nicht vorhersagbare Probleme verursachen, da `DllMain`\-Funktionen i. d. R. wichtigen Initialisierungscode enthalten.  
  
## Ursache  
 Die `DllMain`\-Funktion wird mit Grund DLL\_PROCESS\_ATTACH für die DLL\-Initialisierung nach dem Laden aufgerufen.  Wenn FALSE zurückgegeben wird, bedeutet dies, dass die DLL\-Initialisierung fehlgeschlagen ist.  
  
## Lösung  
 Analysieren Sie den Programmcode der `DllMain`\-Funktion dieser DLL, und ermitteln Sie die Ursache der fehlgeschlagenen Initialisierung.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  Es werden nur Angaben über den Rückgabewert von `DllMain` gemeldet.  
  
## Ausgabe  
 Eine Meldung mit dem Hinweis, dass eine mit dem Grund DLL\_PROCESS\_ATTACH aufgerufene `DllMain`\-Funktion den Wert FALSE zurückgegeben hat.  Beachten Sie, dass dieser MDA nur aktiviert wird, wenn `DllMain` in verwaltetem Code implementiert ist.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)