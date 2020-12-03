---
title: 'Breaking Change: Remoting-APIs sind veraltet'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den einige Remoting-APIs als veraltet gelten und eine Warnung mit einer benutzerdefinierten Diagnose-ID auslösen.
ms.date: 11/01/2020
ms.openlocfilehash: 5687b1471028b077674cfd31cb77ce95dc51bef5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759446"
---
# <a name="remoting-apis-are-obsolete"></a><span data-ttu-id="278eb-103">Remoting-APIs sind veraltet</span><span class="sxs-lookup"><span data-stu-id="278eb-103">Remoting APIs are obsolete</span></span>

<span data-ttu-id="278eb-104">Einige Remoting-bezogene APIs werden als veraltet gekennzeichnet und lösen zur Kompilierzeit die Warnung `SYSLIB0010` aus.</span><span class="sxs-lookup"><span data-stu-id="278eb-104">Some remoting-related APIs are marked as obsolete and generate a `SYSLIB0010` warning at compile time.</span></span> <span data-ttu-id="278eb-105">Diese APIs werden unter Umständen aus zukünftigen Versionen von .NET entfernt.</span><span class="sxs-lookup"><span data-stu-id="278eb-105">These APIs may be removed in a future version of .NET.</span></span>

## <a name="change-description"></a><span data-ttu-id="278eb-106">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="278eb-106">Change description</span></span>

<span data-ttu-id="278eb-107">Die folgenden APIs sind als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="278eb-107">The following remoting APIs are marked obsolete.</span></span>

| <span data-ttu-id="278eb-108">API</span><span class="sxs-lookup"><span data-stu-id="278eb-108">API</span></span> | <span data-ttu-id="278eb-109">Als veraltet markiert in...</span><span class="sxs-lookup"><span data-stu-id="278eb-109">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="278eb-110">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="278eb-110">5.0 RC1</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="278eb-111">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="278eb-111">5.0 RC1</span></span> |

<span data-ttu-id="278eb-112">In .NET Framework 2.x bis 4.x steuern die Methoden <xref:System.MarshalByRefObject.GetLifetimeService> und <xref:System.MarshalByRefObject.InitializeLifetimeService> die Lebensdauer von Instanzen, die an .NET-Remoting beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="278eb-112">In .NET Framework 2.x - 4.x, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods control the lifetime of instances involved with .NET remoting.</span></span> <span data-ttu-id="278eb-113">In .NET Core 2.x bis 3.x lösen diese Methoden zur Laufzeit immer eine Ausnahme des Typs <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="278eb-113">In .NET Core 2.x- 3.x, these methods always throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="278eb-114">In .NET 5.0 und höher sind die Methoden <xref:System.MarshalByRefObject.GetLifetimeService> und <xref:System.MarshalByRefObject.InitializeLifetimeService> durch eine Warnung als veraltet gekennzeichnet, lösen jedoch weiterhin zur Laufzeit eine Ausnahme des Typs <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="278eb-114">In .NET 5.0 and later versions, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods are marked obsolete as warning, but continue to throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

<span data-ttu-id="278eb-115">Dies ist eine Änderung, die nur die Kompilierzeit betrifft.</span><span class="sxs-lookup"><span data-stu-id="278eb-115">This is a compile-time only change.</span></span> <span data-ttu-id="278eb-116">Hinsichtlich der Laufzeit gibt es keine Änderung im Vergleich zu früheren Versionen von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="278eb-116">There is no run-time change from previous versions of .NET Core.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="278eb-117">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="278eb-117">Reason for change</span></span>

<span data-ttu-id="278eb-118">[.NET-Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) ist eine Legacytechnologie.</span><span class="sxs-lookup"><span data-stu-id="278eb-118">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology.</span></span> <span data-ttu-id="278eb-119">Sie ermöglicht das Instanziieren eines Objekts in einem anderen Prozess (möglicherweise sogar auf einem anderen Computer) und das Interagieren mit diesem Objekt, als wäre es eine gewöhnliche In-Process-.NET-Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="278eb-119">It allows instantiating an object in another process (potentially even on a different machine) and interacting with that object as if it were an ordinary, in-process .NET object instance.</span></span> <span data-ttu-id="278eb-120">Die Infrastruktur für das .NET-Remoting ist nur in .NET Framework 2.x bis 4.x vorhanden.</span><span class="sxs-lookup"><span data-stu-id="278eb-120">The .NET remoting infrastructure only exists in .NET Framework 2.x - 4.x.</span></span> <span data-ttu-id="278eb-121">.NET Core sowie .NET 5.0 und höher bieten keine Unterstützung für .NET-Remoting, und die Remoting-APIs sind entweder nicht vorhanden oder lösen in diesen Runtimes immer Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="278eb-121">.NET Core and .NET 5.0 and later versions don't have support for .NET remoting, and the remoting APIs either don't exist or always throw exceptions on these runtimes.</span></span>

<span data-ttu-id="278eb-122">Damit Entwickler zunehmend andere APIs verwenden, werden ausgewählte Remoting-APIs als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="278eb-122">To help steer developers away from these APIs, we are obsoleting selected remoting-related APIs.</span></span> <span data-ttu-id="278eb-123">Diese APIs werden unter Umständen vollständig aus zukünftigen Versionen von .NET entfernt.</span><span class="sxs-lookup"><span data-stu-id="278eb-123">These APIs may be removed entirely in a future version of .NET.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="278eb-124">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="278eb-124">Version introduced</span></span>

<span data-ttu-id="278eb-125">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="278eb-125">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="278eb-126">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="278eb-126">Recommended action</span></span>

- <span data-ttu-id="278eb-127">Sie sollten unter Umständen WCF- oder HTTP-basierte REST-Dienste verwenden, um mit Objekten in anderen Anwendungen oder auf anderen Computern zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="278eb-127">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="278eb-128">Weitere Informationen finden Sie unter [In .NET Core nicht verfügbare .NET Framework-Technologien](../../../porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="278eb-128">For more information, see [.NET Framework technologies unavailable on .NET Core](../../../porting/net-framework-tech-unavailable.md).</span></span>

- <span data-ttu-id="278eb-129">Wenn Sie die veralteten APIs weiterhin verwenden müssen, können Sie die Warnung `SYSLIB0010` im Code unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="278eb-129">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0010` warning in code.</span></span>

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  <span data-ttu-id="278eb-130">Sie können die Warnung auch in Ihrer Projektdatei unterdrücken, wodurch die Warnung für alle Quelldateien im Projekt deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="278eb-130">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="278eb-131">Durch das Unterdrücken von `SYSLIB0010` werden nur Veraltungswarnungen für die Remoting-APIs deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="278eb-131">Suppressing `SYSLIB0010` disables only the remoting API obsoletion warnings.</span></span> <span data-ttu-id="278eb-132">Andere Warnungen werden nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="278eb-132">It does not disable any other warnings.</span></span> <span data-ttu-id="278eb-133">Außerdem wird das hartcodierte Laufzeitverhalten nicht geändert, das darin besteht, <xref:System.PlatformNotSupportedException> immer auszulösen.</span><span class="sxs-lookup"><span data-stu-id="278eb-133">Additionally, it doesn't change the hardcoded run-time behavior of always throwing <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="278eb-134">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="278eb-134">Affected APIs</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
