---
title: Assemblypositionierung
description: Lesen Sie sich den Leitfaden zur .NET-Assemblypositionierung innerhalb von Verzeichnissen durch (z. B. im globalen Assemblycache oder im Verzeichnis oder Unterverzeichnis der Anwendung).
ms.date: 03/30/2017
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
ms.openlocfilehash: 15ff6edf5887062b0cce918b39beef6c9b618ca2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271551"
---
# <a name="assembly-placement"></a>Assemblypositionierung

Bei den meisten .NET Framework-Anwendungen werden die Assemblys, aus denen eine Anwendung besteht, im Anwendungsverzeichnis, in einem Unterverzeichnis des Anwendungsverzeichnisses oder im globalen Assemblycache (sofern die Assembly freigegeben ist) gesucht. Sie können den Speicherort überschreiben, in dem die Common Language Runtime nach einer Assembly sucht, indem Sie das [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) in einer Konfigurationsdatei verwenden. Wenn die Assembly keinen starken Namen aufweist, kann mit dem [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) nur das Anwendungsverzeichnis oder ein Unterverzeichnis als Speicherort angegeben werden. Wenn die Assembly einen starken Namen aufweist, kann mit dem [\<codeBase>-Element](../configure-apps/file-schema/runtime/codebase-element.md) ein beliebiger Speicherort auf dem Computer oder in einem Netzwerk angegeben werden.  
  
 Ähnliche Regeln gelten für das Suchen von Assemblys, wenn nicht verwalteter Code oder COM-Interop-Anwendungen verwendet werden. Wenn die Assembly für mehrere Anwendungen freigegeben werden soll, muss sie im globalen Assemblycache installiert werden. Assemblys, die mit nicht verwaltetem Code verwendet werden, müssen als Typbibliothek exportiert und registriert werden. Assemblys, die von COM-Interop verwendet werden, müssen im Katalog registriert werden. In einigen Fällen erfolgt diese Registrierung automatisch.  
  
## <a name="see-also"></a>Siehe auch

- [So sucht Common Language Runtime nach Assemblys](../deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurieren von Apps](../configure-apps/index.md)
- [Interoperabilität mit nicht verwaltetem Code](../interop/index.md)
- [Assemblys in .NET](index.md)
