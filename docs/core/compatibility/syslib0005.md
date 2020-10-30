---
title: Warnung „SYSLIB0005“
description: In diesem Artikel erfahren Sie mehr über das veraltete Element, das zur Kompilierzeit den Fehler „SYSLIB0005“ generiert.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 8a9893d81c781335014c8b970c460b5a4241ed18
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333089"
---
# <a name="syslib0005-the-global-assembly-cache-gac-is-not-supported"></a><span data-ttu-id="4417e-103">SYSLIB0005: Der globale Assemblycache (GAC) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4417e-103">SYSLIB0005: The global assembly cache (GAC) is not supported</span></span>

<span data-ttu-id="4417e-104">.NET Core und .NET 5.0 sowie höhere Versionen verzichten auf das Konzept des globalen Assemblycaches (GAC), das in .NET Framework vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="4417e-104">.NET Core and .NET 5.0 and later versions eliminate the concept of the global assembly cache (GAC) that was present in .NET Framework.</span></span> <span data-ttu-id="4417e-105">Einige GAC-bezogene APIs werden ab .NET 5.0 als veraltet markiert, damit Entwickler zunehmend andere APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="4417e-105">To help steer developers away from these APIs, some GAC-related APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="4417e-106">Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0005` hervor.</span><span class="sxs-lookup"><span data-stu-id="4417e-106">Using these APIs generates warning `SYSLIB0005` at compile time.</span></span>

<span data-ttu-id="4417e-107">Die folgenden GAC-bezogenen APIs sind als veraltet markiert:</span><span class="sxs-lookup"><span data-stu-id="4417e-107">The following GAC-related APIs are marked obsolete:</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType>

  <span data-ttu-id="4417e-108">Bibliotheken und Apps sollten die <xref:System.Reflection.Assembly.GlobalAssemblyCache>-API nicht beim Festlegen des Laufzeitverhaltens verwenden, da diese in .NET Core und .NET 5 (oder höher) immer `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4417e-108">Libraries and apps should not use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> API to make determinations about run-time behavior, as it always returns `false` in .NET Core and .NET 5+.</span></span>

## <a name="workaround"></a><span data-ttu-id="4417e-109">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="4417e-109">Workaround</span></span>

<span data-ttu-id="4417e-110">Wenn die Anwendung die <xref:System.Reflection.Assembly.GlobalAssemblyCache>-Eigenschaft abfragt, sollten Sie den Aufruf entfernen.</span><span class="sxs-lookup"><span data-stu-id="4417e-110">If your application queries the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property, consider removing the call.</span></span> <span data-ttu-id="4417e-111">Wenn Sie den Wert <xref:System.Reflection.Assembly.GlobalAssemblyCache> verwenden, um zur Laufzeit zwischen Flows zu wählen, bei denen sich die Assembly entweder im GAC oder nicht im GAC befindet, sollten Sie sich überlegen, ob der Flow auch für eine .NET 5-Anwendung (oder höher) geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="4417e-111">If you use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> value to choose between an "assembly in the GAC"-flow vs. an "assembly not in the GAC"-flow at run time, reconsider whether the flow still makes sense for a .NET 5+ application.</span></span>

## <a name="see-also"></a><span data-ttu-id="4417e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4417e-112">See also</span></span>

- [<span data-ttu-id="4417e-113">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="4417e-113">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
