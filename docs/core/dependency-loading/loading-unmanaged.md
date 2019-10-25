---
title: Ladealgorithmus für nicht verwaltete Bibliotheken – .NET Core
description: Beschreibung von Details des Ladealgorithmus für nicht verwaltete Assemblys in .NET Core
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72303695"
---
# <a name="unmanaged-native-library-loading-algorithm"></a>Ladealgorithmus für nicht verwaltete (native) Bibliotheken

Nicht verwaltete Bibliotheken werden in mehreren Schritten über einen Algorithmus gesucht und geladen.

Der folgende Algorithmus beschreibt, wie native Bibliotheken über `PInvoke` geladen werden.

## <a name="pinvoke-load-library-algorithm"></a>Der Algorithmus `PInvoke` für das Laden von Bibliotheken

`PInvoke` verwendet beim Versuch, eine nicht verwaltete Assembly zu laden, den folgenden Algorithmus:

1. Ermitteln Sie den `active` <xref:System.Runtime.Loader.AssemblyLoadContext>. Beim Laden einer nicht verwalteten Bibliothek ist der `active` AssemblyLoadContext der mit der Assembly, die `PInvoke` definiert.

2. Versuchen Sie, die Assembly für den `active` <xref:System.Runtime.Loader.AssemblyLoadContext> in der Reihenfolge nach Priorität zu suchen:
    * Überprüfen des Caches

    * Aufrufen des aktuellen <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType>-Delegaten, der von der <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType>-Funktion festgelegt wird

    * Aufrufen der <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType>-Funktion für den `active` AssemblyLoadContext

    * Überprüfen des Caches der <xref:System.AppDomain>-Instanz und Ausführen der Logik für die [Überprüfung nicht verwalteter (nativer) Bibliotheken](default-probing.md#unmanaged-native-library-probing)

    * Auslösen des <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType>-Ereignisses für den `active` AssemblyLoadContext
