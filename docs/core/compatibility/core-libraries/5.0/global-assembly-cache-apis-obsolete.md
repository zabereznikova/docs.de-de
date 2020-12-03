---
title: 'Breaking Change: APIs für den globalen Assemblycache sind veraltet'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, der sich auf GAC-APIs bezieht, die früher entweder fehlschlugen oder keinen Vorgang ausführten.
ms.date: 11/01/2020
ms.openlocfilehash: 2f74fccc68b7a925d909938d77578df8ebe8d60d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759484"
---
# <a name="global-assembly-cache-apis-are-obsolete"></a><span data-ttu-id="34a66-103">APIs für den globalen Assemblycache sind veraltet</span><span class="sxs-lookup"><span data-stu-id="34a66-103">Global assembly cache APIs are obsolete</span></span>

<span data-ttu-id="34a66-104">.NET Core und .NET 5.0 sowie höhere Versionen verzichten auf das Konzept des globalen Assemblycaches (GAC), das in .NET Framework vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="34a66-104">.NET Core and .NET 5.0 and later versions eliminate the concept of the global assembly cache (GAC) that was present in .NET Framework.</span></span> <span data-ttu-id="34a66-105">Daher treten bei allen APIs für .NET Core und .NET 5 sowie höhere Versionen im Zusammenhang mit dem GAC Fehler auf, oder die APIs führen keinen Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="34a66-105">As such, all .NET Core and .NET 5+ APIs that deal with the GAC either fail or perform no operation.</span></span>

<span data-ttu-id="34a66-106">Einige GAC-bezogene APIs werden als veraltet markiert und generieren zur Kompilierzeit die Warnung `SYSLIB0005`, damit Entwickler zunehmend andere APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="34a66-106">To help steer developers away from these APIs, some GAC-related APIs are marked as obsolete, and generate a `SYSLIB0005` warning at compile time.</span></span> <span data-ttu-id="34a66-107">Diese APIs werden unter Umständen aus zukünftigen Versionen von .NET entfernt.</span><span class="sxs-lookup"><span data-stu-id="34a66-107">These APIs may be removed in a future version of .NET.</span></span>

## <a name="change-description"></a><span data-ttu-id="34a66-108">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="34a66-108">Change description</span></span>

<span data-ttu-id="34a66-109">Die folgenden APIs sind als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="34a66-109">The following APIs are marked obsolete.</span></span>

| <span data-ttu-id="34a66-110">API</span><span class="sxs-lookup"><span data-stu-id="34a66-110">API</span></span> | <span data-ttu-id="34a66-111">Als veraltet markiert in...</span><span class="sxs-lookup"><span data-stu-id="34a66-111">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | <span data-ttu-id="34a66-112">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="34a66-112">5.0 RC1</span></span> |

<span data-ttu-id="34a66-113">In .NET Framework 2.x bis 4.x gibt die Eigenschaft <xref:System.Reflection.Assembly.GlobalAssemblyCache> `true` zurück, wenn die abgefragte Assembly aus dem GAC geladen wurde. `false` wird zurückgegeben, wenn die Assembly aus einem anderen Speicherort auf dem Datenträger geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="34a66-113">In .NET Framework 2.x - 4.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property returns `true` if the queried assembly was loaded from the GAC, and `false` if it was loaded from a different location on disk.</span></span> <span data-ttu-id="34a66-114">In .NET Core 2.x bis 3.x gibt <xref:System.Reflection.Assembly.GlobalAssemblyCache> immer `false` zurück, was deutlich macht, dass der GAC in .NET Core nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="34a66-114">In .NET Core 2.x - 3.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> always returns `false`, reflecting that the GAC does not exist in .NET Core.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="34a66-115">In .NET 5.0 und höheren Versionen gibt die Eigenschaft <xref:System.Reflection.Assembly.GlobalAssemblyCache> auch weiterhin immer `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="34a66-115">In .NET 5.0 and later versions, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property continues to always return `false`.</span></span> <span data-ttu-id="34a66-116">Der Getter für die Eigenschaft ist jedoch ebenfalls als veraltet markiert, um Aufrufer darauf hinzuweisen, dass sie nicht mehr auf die Eigenschaft zugreifen sollen.</span><span class="sxs-lookup"><span data-stu-id="34a66-116">However, the property getter is also marked as obsolete to indicate to callers that they should stop accessing the property.</span></span> <span data-ttu-id="34a66-117">Bibliotheken und Apps sollten die <xref:System.Reflection.Assembly.GlobalAssemblyCache>-API nicht beim Festlegen des Laufzeitverhaltens verwenden, da diese in .NET Core und .NET 5.0 sowie höheren Versionen immer `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="34a66-117">Libraries and apps should not use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> API to make determinations about run-time behavior, as it always returns `false` in .NET Core and .NET 5.0 and later versions.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="34a66-118">Dies ist eine Änderung, die nur die Kompilierzeit betrifft.</span><span class="sxs-lookup"><span data-stu-id="34a66-118">This is a compile-time only change.</span></span> <span data-ttu-id="34a66-119">Hinsichtlich der Laufzeit gibt es keine Änderung im Vergleich zu früheren Versionen von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="34a66-119">There is no run-time change from previous versions of .NET Core.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="34a66-120">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="34a66-120">Reason for change</span></span>

<span data-ttu-id="34a66-121">Der globale Assemblycache (GAC) ist nicht als Konzept in .NET Core und .NET 5.0 und höheren Versionen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="34a66-121">The global assembly cache (GAC) does not exist as a concept in .NET Core and .NET 5.0 and later versions.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="34a66-122">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="34a66-122">Version introduced</span></span>

<span data-ttu-id="34a66-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="34a66-123">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="34a66-124">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="34a66-124">Recommended action</span></span>

- <span data-ttu-id="34a66-125">Wenn die Anwendung die <xref:System.Reflection.Assembly.GlobalAssemblyCache>-Eigenschaft abfragt, sollten Sie den Aufruf entfernen.</span><span class="sxs-lookup"><span data-stu-id="34a66-125">If your application queries the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property, consider removing the call.</span></span> <span data-ttu-id="34a66-126">Wenn Sie den Wert <xref:System.Reflection.Assembly.GlobalAssemblyCache> verwenden, um zur Laufzeit zwischen Flows zu wählen, bei denen sich die Assembly entweder im GAC oder nicht im GAC befindet, sollten Sie sich überlegen, ob der Flow auch für eine .NET Core- oder .NET 5.0-Anwendung (oder höher) geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="34a66-126">If you use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> value to choose between an "assembly in the GAC"-flow vs. an "assembly not in the GAC"-flow at run time, reconsider whether the flow still makes sense for a .NET Core or .NET 5.0+ application.</span></span>

- <span data-ttu-id="34a66-127">Wenn Sie die veralteten APIs weiterhin verwenden müssen, können Sie die Warnung `SYSLIB0005` im Code unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="34a66-127">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0005` warning in code.</span></span>

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  <span data-ttu-id="34a66-128">Sie können die Warnung auch in Ihrer Projektdatei unterdrücken, wodurch die Warnung für alle Quelldateien im Projekt deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="34a66-128">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="34a66-129">Durch das Unterdrücken von `SYSLIB0005` wird nur die Veraltungswarnung <xref:System.Reflection.Assembly.GlobalAssemblyCache> deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="34a66-129">Suppressing `SYSLIB0005` disables only the <xref:System.Reflection.Assembly.GlobalAssemblyCache> obsoletion warning.</span></span> <span data-ttu-id="34a66-130">Andere Warnungen werden nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="34a66-130">It does not disable any other warnings.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="34a66-131">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="34a66-131">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
