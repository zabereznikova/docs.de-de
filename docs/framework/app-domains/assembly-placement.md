---
title: "Assemblypositionierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<codeBase>-Element"
  - "Assemblys [.NET Framework], Speicherort"
  - "Assemblys [.NET Framework], Positionierung"
  - "Suchen von Assemblys"
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Assemblypositionierung
Bei den meisten .NET Framework\-Anwendungen werden die Assemblys, aus denen eine Anwendung besteht, im Anwendungsverzeichnis, in einem Unterverzeichnis des Anwendungsverzeichnisses oder im globalen Assemblycache \(sofern die Assembly freigegeben ist\) gesucht.  Sie können den Speicherort überschreiben, in dem die Common Language Runtime nach einer Assembly sucht, indem Sie in einer Konfigurationsdatei [\<codeBase\>\-Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) verwenden.  Wenn die Assembly keinen starken Namen hat, kann mit [\<codeBase\>\-Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) nur das Anwendungsverzeichnis oder ein Unterverzeichnis als Speicherort angegeben werden.  Wenn die Assembly einen starken Namen aufweist, kann mit [\<codeBase\>\-Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) ein beliebiger Speicherort auf dem Computer oder im Netzwerk angegeben werden.  
  
 Ähnliche Regeln gelten für das Suchen von Assemblys, wenn nicht verwalteter Code oder COM\-Interop\-Anwendungen verwendet werden. Wenn die Assembly für mehrere Anwendungen freigegeben werden soll, muss sie im globalen Assemblycache installiert werden.  Assemblys, die mit nicht verwaltetem Code verwendet werden, müssen als Typbibliothek exportiert und registriert werden.  Assemblys, die von COM\-Interop verwendet werden, müssen im Katalog registriert werden. In einigen Fällen erfolgt diese Registrierung automatisch.  
  
## Siehe auch  
 [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Konfigurieren von Apps](../../../docs/framework/configure-apps/index.md)   
 [Advanced COM Interoperability](http://msdn.microsoft.com/de-de/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Assemblys in der Common Language Runtime \(CLR\)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)