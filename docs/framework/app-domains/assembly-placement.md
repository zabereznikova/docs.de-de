---
title: Assemblypositionierung
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6281a0f68fa0ce81b4763d8d0e8f17b47771d2ff
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053206"
---
# <a name="assembly-placement"></a>Assemblypositionierung
Bei den meisten .NET Framework-Anwendungen werden die Assemblys, aus denen eine Anwendung besteht, im Anwendungsverzeichnis, in einem Unterverzeichnis des Anwendungsverzeichnisses oder im globalen Assemblycache (sofern die Assembly freigegeben ist) gesucht. Sie können den Speicherort überschreiben, in dem die Common Language Runtime nach einer Assembly sucht, indem Sie das [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) in einer Konfigurationsdatei verwenden. Wenn die Assembly keinen starken Namen hat, kann mit dem [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) nur das Anwendungsverzeichnis oder ein Unterverzeichnis als Speicherort angegeben werden. Wenn die Assembly einen starken Namen aufweist, kann mit dem [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) ein beliebiger Speicherort auf dem Computer oder im Netzwerk angegeben werden.  
  
 Ähnliche Regeln gelten für das Suchen von Assemblys, wenn nicht verwalteter Code oder COM-Interop-Anwendungen verwendet werden. Wenn die Assembly für mehrere Anwendungen freigegeben werden soll, muss sie im globalen Assemblycache installiert werden. Assemblys, die mit nicht verwaltetem Code verwendet werden, müssen als Typbibliothek exportiert und registriert werden. Assemblys, die von COM-Interop verwendet werden, müssen im Katalog registriert werden. In einigen Fällen erfolgt diese Registrierung automatisch.  
  
## <a name="see-also"></a>Siehe auch

- [So sucht Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurieren von Apps](../configure-apps/index.md)
- [Interoperabilität mit nicht verwaltetem Code](../interop/index.md)
- [Assemblys in .NET](index.md)
