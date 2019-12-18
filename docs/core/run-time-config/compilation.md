---
title: Kompilierungskonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die die Funktionsweise des JIT-Compilers für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998876"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="4d708-103">Laufzeitkonfigurationsoptionen für die Kompilierung</span><span class="sxs-lookup"><span data-stu-id="4d708-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="4d708-104">Mehrstufig Kompilierung</span><span class="sxs-lookup"><span data-stu-id="4d708-104">Tiered compilation</span></span>

- <span data-ttu-id="4d708-105">Konfiguriert, ob der JIT-Compiler [mehrstufige Kompilierung](../whats-new/dotnet-core-3-0.md#tiered-compilation) verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d708-105">Configures whether the JIT compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span>
- <span data-ttu-id="4d708-106">In .NET Core 3.0 und höher ist die mehrstufige Kompilierung standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4d708-106">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="4d708-107">In .NET Core 2.1 und 2.2 ist die mehrstufige Kompilierung standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4d708-107">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>

| | <span data-ttu-id="4d708-108">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="4d708-108">Setting name</span></span> | <span data-ttu-id="4d708-109">Werte</span><span class="sxs-lookup"><span data-stu-id="4d708-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="4d708-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4d708-110">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="4d708-111">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="4d708-111">`true` - enabled</span></span><br/><span data-ttu-id="4d708-112">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="4d708-112">`false` - disabled</span></span> |
| <span data-ttu-id="4d708-113">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="4d708-113">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="4d708-114">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="4d708-114">`1` - enabled</span></span><br/><span data-ttu-id="4d708-115">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="4d708-115">`0` - disabled</span></span> |
