---
title: Ladealgorithmus für nicht verwaltete Bibliotheken – .NET Core
description: Beschreibung von Details des Ladealgorithmus für nicht verwaltete Assemblys in .NET Core
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72303695"
---
# <a name="unmanaged-native-library-loading-algorithm"></a><span data-ttu-id="1c226-103">Ladealgorithmus für nicht verwaltete (native) Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="1c226-103">Unmanaged (native) library loading algorithm</span></span>

<span data-ttu-id="1c226-104">Nicht verwaltete Bibliotheken werden in mehreren Schritten über einen Algorithmus gesucht und geladen.</span><span class="sxs-lookup"><span data-stu-id="1c226-104">Unmanaged libraries are located and loaded with an algorithm involving various stages.</span></span>

<span data-ttu-id="1c226-105">Der folgende Algorithmus beschreibt, wie native Bibliotheken über `PInvoke` geladen werden.</span><span class="sxs-lookup"><span data-stu-id="1c226-105">The following algorithm describes how native libraries are loaded through `PInvoke`.</span></span>

## <a name="pinvoke-load-library-algorithm"></a><span data-ttu-id="1c226-106">Der Algorithmus `PInvoke` für das Laden von Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="1c226-106">`PInvoke` load library algorithm</span></span>

<span data-ttu-id="1c226-107">`PInvoke` verwendet beim Versuch, eine nicht verwaltete Assembly zu laden, den folgenden Algorithmus:</span><span class="sxs-lookup"><span data-stu-id="1c226-107">`PInvoke` uses the following algorithm when attempting to load an unmanaged assembly:</span></span>

1. <span data-ttu-id="1c226-108">Ermitteln Sie den `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="1c226-108">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="1c226-109">Beim Laden einer nicht verwalteten Bibliothek ist der `active` AssemblyLoadContext der mit der Assembly, die `PInvoke` definiert.</span><span class="sxs-lookup"><span data-stu-id="1c226-109">For an unmanaged load library, the `active` AssemblyLoadContext is the one with the assembly that defines the `PInvoke`.</span></span>

2. <span data-ttu-id="1c226-110">Versuchen Sie, die Assembly für den `active` <xref:System.Runtime.Loader.AssemblyLoadContext> in der Reihenfolge nach Priorität zu suchen:</span><span class="sxs-lookup"><span data-stu-id="1c226-110">For the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, try to find the assembly in priority order by:</span></span>
    * <span data-ttu-id="1c226-111">Überprüfen des Caches</span><span class="sxs-lookup"><span data-stu-id="1c226-111">Checking its cache.</span></span>

    * <span data-ttu-id="1c226-112">Aufrufen des aktuellen <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType>-Delegaten, der von der <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType>-Funktion festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="1c226-112">Calling the current <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegate set by the <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> function.</span></span>

    * <span data-ttu-id="1c226-113">Aufrufen der <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType>-Funktion für den `active` AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="1c226-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> function on the `active` AssemblyLoadContext.</span></span>

    * <span data-ttu-id="1c226-114">Überprüfen des Caches der <xref:System.AppDomain>-Instanz und Ausführen der Logik für die [Überprüfung nicht verwalteter (nativer) Bibliotheken](default-probing.md#unmanaged-native-library-probing)</span><span class="sxs-lookup"><span data-stu-id="1c226-114">Checking the <xref:System.AppDomain> instance's cache and running the [Unmanaged (native) library probing](default-probing.md#unmanaged-native-library-probing) logic.</span></span>

    * <span data-ttu-id="1c226-115">Auslösen des <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType>-Ereignisses für den `active` AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="1c226-115">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> event for the `active` AssemblyLoadContext.</span></span>
