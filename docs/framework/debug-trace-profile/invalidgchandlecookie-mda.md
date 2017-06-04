---
title: "invalidGCHandleCookie MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid cookies"
  - "cookies, invalid"
  - "managed debugging assistants (MDAs), invalid cookies"
  - "InvalidGCHandleCookie MDA"
  - "invalid cookies"
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# invalidGCHandleCookie MDA
Der `invalidGCHandleCookie`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn versucht wird, ein ungültiges <xref:System.IntPtr>\-Cookie in ein <xref:System.Runtime.InteropServices.GCHandle> umzuwandeln.  
  
## Symptome  
 Undefiniertes Verhalten wie Zugriffsverletzungen und Speicherschäden beim Versuch, ein <xref:System.Runtime.InteropServices.GCHandle> aus einem <xref:System.IntPtr> zu verwenden oder abzurufen.  
  
## Ursache  
 Das Cookie ist wahrscheinlich ungültig, weil es ursprünglich nicht von einem <xref:System.Runtime.InteropServices.GCHandle> erstellt wurde, ein bereits freigegebenes <xref:System.Runtime.InteropServices.GCHandle> darstellt, sich auf ein <xref:System.Runtime.InteropServices.GCHandle> in einer anderen Anwendungsdomäne bezieht oder als <xref:System.Runtime.InteropServices.GCHandle> in systemeigenen Code gemarshallt, jedoch als <xref:System.IntPtr> wieder in die CLR zurückgegeben und dann dort eine Umwandlung versucht wurde.  
  
## Lösung  
 Geben Sie ein gültiges <xref:System.IntPtr>\-Cookie für das <xref:System.Runtime.InteropServices.GCHandle> an.  
  
## Auswirkungen auf die Laufzeit  
 Wenn dieser MDA aktiviert wird, kann der Debugger Wurzeln nicht mehr zu den Objekten zurückverfolgen, da sich die Werte der zurückgegebenen Cookies von denen ohne aktivierten MDA unterscheiden.  
  
## Ausgabe  
 Es wird der Wert des ungültigen <xref:System.IntPtr>\-Cookies gemeldet.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>   
 <xref:System.Runtime.InteropServices.GCHandle>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)