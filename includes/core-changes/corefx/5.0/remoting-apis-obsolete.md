---
ms.openlocfilehash: 35041a035041fd4ad5402e1bc0dd137a74d4f949
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434967"
---
### <a name="remoting-apis-are-obsolete"></a><span data-ttu-id="53de9-101">Remoting-APIs sind veraltet</span><span class="sxs-lookup"><span data-stu-id="53de9-101">Remoting APIs are obsolete</span></span>

<span data-ttu-id="53de9-102">Einige Remoting-bezogene APIs werden als veraltet gekennzeichnet und lösen zur Kompilierzeit die Warnung `SYSLIB0010` aus.</span><span class="sxs-lookup"><span data-stu-id="53de9-102">Some remoting-related APIs are marked as obsolete and generate a `SYSLIB0010` warning at compile time.</span></span> <span data-ttu-id="53de9-103">Diese APIs werden unter Umständen aus zukünftigen Versionen von .NET entfernt.</span><span class="sxs-lookup"><span data-stu-id="53de9-103">These APIs may be removed in a future version of .NET.</span></span>

#### <a name="change-description"></a><span data-ttu-id="53de9-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="53de9-104">Change description</span></span>

<span data-ttu-id="53de9-105">Die folgenden APIs sind als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="53de9-105">The following remoting APIs are marked obsolete.</span></span>

| <span data-ttu-id="53de9-106">API</span><span class="sxs-lookup"><span data-stu-id="53de9-106">API</span></span> | <span data-ttu-id="53de9-107">Als veraltet markiert in...</span><span class="sxs-lookup"><span data-stu-id="53de9-107">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="53de9-108">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="53de9-108">5.0 RC1</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="53de9-109">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="53de9-109">5.0 RC1</span></span> |

<span data-ttu-id="53de9-110">In .NET Framework 2.x bis 4.x steuern die Methoden <xref:System.MarshalByRefObject.GetLifetimeService> und <xref:System.MarshalByRefObject.InitializeLifetimeService> die Lebensdauer von Instanzen, die an .NET-Remoting beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="53de9-110">In .NET Framework 2.x - 4.x, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods control the lifetime of instances involved with .NET remoting.</span></span> <span data-ttu-id="53de9-111">In .NET Core 2.x bis 3.x lösen diese Methoden zur Laufzeit immer eine Ausnahme des Typs <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="53de9-111">In .NET Core 2.x- 3.x, these methods always throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="53de9-112">In .NET 5.0 und höher sind die Methoden <xref:System.MarshalByRefObject.GetLifetimeService> und <xref:System.MarshalByRefObject.InitializeLifetimeService> durch eine Warnung als veraltet gekennzeichnet, lösen jedoch weiterhin zur Laufzeit eine Ausnahme des Typs <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="53de9-112">In .NET 5.0 and later versions, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods are marked obsolete as warning, but continue to throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

<span data-ttu-id="53de9-113">Dies ist eine Änderung, die nur die Kompilierzeit betrifft.</span><span class="sxs-lookup"><span data-stu-id="53de9-113">This is a compile-time only change.</span></span> <span data-ttu-id="53de9-114">Hinsichtlich der Laufzeit gibt es keine Änderung im Vergleich zu früheren Versionen von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="53de9-114">There is no run-time change from previous versions of .NET Core.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="53de9-115">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="53de9-115">Reason for change</span></span>

<span data-ttu-id="53de9-116">[.NET-Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) ist eine Legacytechnologie.</span><span class="sxs-lookup"><span data-stu-id="53de9-116">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology.</span></span> <span data-ttu-id="53de9-117">Sie ermöglicht das Instanziieren eines Objekts in einem anderen Prozess (möglicherweise sogar auf einem anderen Computer) und das Interagieren mit diesem Objekt, als wäre es eine gewöhnliche In-Process-.NET-Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="53de9-117">It allows instantiating an object in another process (potentially even on a different machine) and interacting with that object as if it were an ordinary, in-process .NET object instance.</span></span> <span data-ttu-id="53de9-118">Die Infrastruktur für das .NET-Remoting ist nur in .NET Framework 2.x bis 4.x vorhanden.</span><span class="sxs-lookup"><span data-stu-id="53de9-118">The .NET remoting infrastructure only exists in .NET Framework 2.x - 4.x.</span></span> <span data-ttu-id="53de9-119">.NET Core sowie .NET 5.0 und höher bieten keine Unterstützung für .NET-Remoting, und die Remoting-APIs sind entweder nicht vorhanden oder lösen in diesen Runtimes immer Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="53de9-119">.NET Core and .NET 5.0 and later versions don't have support for .NET remoting, and the remoting APIs either don't exist or always throw exceptions on these runtimes.</span></span>

<span data-ttu-id="53de9-120">Damit Entwickler zunehmend andere APIs verwenden, werden ausgewählte Remoting-APIs als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="53de9-120">To help steer developers away from these APIs, we are obsoleting selected remoting-related APIs.</span></span> <span data-ttu-id="53de9-121">Diese APIs werden unter Umständen vollständig aus zukünftigen Versionen von .NET entfernt.</span><span class="sxs-lookup"><span data-stu-id="53de9-121">These APIs may be removed entirely in a future version of .NET.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="53de9-122">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="53de9-122">Version introduced</span></span>

<span data-ttu-id="53de9-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="53de9-123">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="53de9-124">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="53de9-124">Recommended action</span></span>

- <span data-ttu-id="53de9-125">Sie sollten unter Umständen WCF- oder HTTP-basierte REST-Dienste verwenden, um mit Objekten in anderen Anwendungen oder auf anderen Computern zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="53de9-125">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="53de9-126">Weitere Informationen finden Sie unter [In .NET Core nicht verfügbare .NET Framework-Technologien](../../../../docs/core/porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="53de9-126">For more information, see [.NET Framework technologies unavailable on .NET Core](../../../../docs/core/porting/net-framework-tech-unavailable.md).</span></span>

- <span data-ttu-id="53de9-127">Wenn Sie die veralteten APIs weiterhin verwenden müssen, können Sie die Warnung `SYSLIB0010` im Code unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="53de9-127">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0010` warning in code.</span></span>

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  <span data-ttu-id="53de9-128">Sie können die Warnung auch in Ihrer Projektdatei unterdrücken, wodurch die Warnung für alle Quelldateien im Projekt deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="53de9-128">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="53de9-129">Durch das Unterdrücken von `SYSLIB0010` werden nur Veraltungswarnungen für die Remoting-APIs deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="53de9-129">Suppressing `SYSLIB0010` disables only the remoting API obsoletion warnings.</span></span> <span data-ttu-id="53de9-130">Andere Warnungen werden nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="53de9-130">It does not disable any other warnings.</span></span> <span data-ttu-id="53de9-131">Außerdem wird das hartcodierte Laufzeitverhalten nicht geändert, das darin besteht, <xref:System.PlatformNotSupportedException> immer auszulösen.</span><span class="sxs-lookup"><span data-stu-id="53de9-131">Additionally, it doesn't change the hardcoded run-time behavior of always throwing <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="53de9-132">Kategorie</span><span class="sxs-lookup"><span data-stu-id="53de9-132">Category</span></span>

<span data-ttu-id="53de9-133">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="53de9-133">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="53de9-134">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="53de9-134">Affected APIs</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
