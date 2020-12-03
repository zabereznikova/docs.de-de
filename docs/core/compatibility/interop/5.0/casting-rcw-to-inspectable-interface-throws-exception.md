---
title: 'Breaking Change: Umwandeln eines RCW in `InterfaceIsIInspectable` löst eine Ausnahme aus'
description: Hier erfahren Sie mehr über den Interop-Breaking-Change in .NET 5.0, durch den das Umwandeln eines RCW in eine `InterfaceIsIInspectable`-Schnittstelle die Ausnahme „PlatformNotSupportedException“ auslöst.
ms.date: 09/13/2020
ms.openlocfilehash: 7c0f37057aebcc41d0c00d949b921ec3a4bdf012
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759480"
---
# <a name="casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception"></a><span data-ttu-id="86260-103">Umwandlung des RCW in eine `InterfaceIsIInspectable`-Schnittstelle löst PlatformNotSupportedException aus</span><span class="sxs-lookup"><span data-stu-id="86260-103">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>

<span data-ttu-id="86260-104">Wenn ein RCW (Runtime Callable Wrapper) in eine als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> gekennzeichnete Schnittstelle umgewandelt wird, wird jetzt <xref:System.PlatformNotSupportedException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="86260-104">Casting a runtime callable wrapper (RCW) to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> now throws a <xref:System.PlatformNotSupportedException>.</span></span> <span data-ttu-id="86260-105">Diese Änderung folgt der [Entfernung der WinRT-Unterstützung aus .NET](built-in-support-for-winrt-removed.md).</span><span class="sxs-lookup"><span data-stu-id="86260-105">This change is a follow up to the [removal of WinRT support from .NET](built-in-support-for-winrt-removed.md).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="86260-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="86260-106">Version introduced</span></span>

<span data-ttu-id="86260-107">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="86260-107">5.0 RC2</span></span>

## <a name="change-description"></a><span data-ttu-id="86260-108">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="86260-108">Change description</span></span>

<span data-ttu-id="86260-109">In .NET-Versionen vor .NET 5.0 Preview 6 funktioniert das Umwandeln eines RCW in eine als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> gekennzeichnete Schnittstelle wie gewohnt.</span><span class="sxs-lookup"><span data-stu-id="86260-109">In .NET versions prior to .NET 5.0 preview 6, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> works as expected.</span></span> <span data-ttu-id="86260-110">In .NET 5.0 Preview 6 bis Preview 8 und in .NET 5.0 RC1 können Sie einen RCW erfolgreich in eine <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>-Schnittstelle umwandeln.</span><span class="sxs-lookup"><span data-stu-id="86260-110">In .NET 5.0 previews 6-8 and RC1, you can successfully cast an RCW to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface.</span></span> <span data-ttu-id="86260-111">Möglicherweise gilt das Ausführen von Methoden für die Schnittstelle jedoch als Zugriffsverletzung, da die zugrunde liegende Unterstützung in [.NET 5.0 Preview 6](built-in-support-for-winrt-removed.md) aus der Runtime entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="86260-111">However, you might get access violations when you execute methods on the interface, because the underlying support in the runtime [was removed in .NET 5.0 preview 6](built-in-support-for-winrt-removed.md).</span></span>

<span data-ttu-id="86260-112">In .NET 5.0 RC2 und höher löst das Umwandeln eines RCW in eine als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> gekennzeichnete Schnittstelle zur Umwandlungszeit <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="86260-112">In .NET 5.0 RC2 and later versions, casting an RCW to an interface marked as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> throws a <xref:System.PlatformNotSupportedException> at cast time.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="86260-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="86260-113">Reason for change</span></span>

<span data-ttu-id="86260-114">Die Unterstützung von <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> wurde in einer [früheren Vorschauversion von .NET 5.0](built-in-support-for-winrt-removed.md) entfernt.</span><span class="sxs-lookup"><span data-stu-id="86260-114">The support for <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> was [removed in a previous .NET 5.0 preview](built-in-support-for-winrt-removed.md).</span></span> <span data-ttu-id="86260-115">Das Umwandeln in eine <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>-Schnittstelle wurde dabei jedoch versehentlich nicht bedacht.</span><span class="sxs-lookup"><span data-stu-id="86260-115">However, casting to an <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> interface was accidentally overlooked.</span></span> <span data-ttu-id="86260-116">Da die zugrunde liegende Unterstützung in der Runtime nicht mehr vorhanden ist, erzeugt das Auslösen von <xref:System.PlatformNotSupportedException> einen ordnungsgemäßen Fehlerpfad.</span><span class="sxs-lookup"><span data-stu-id="86260-116">Since the underlying support in the runtime no longer exists, throwing a <xref:System.PlatformNotSupportedException> enables a graceful failure path.</span></span> <span data-ttu-id="86260-117">Durch die ausgelöste Ausnahme ist zudem leichter erkennbar, dass das Feature nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="86260-117">Throwing an exception also makes it more discoverable that this feature is no longer supported.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="86260-118">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="86260-118">Recommended action</span></span>

- <span data-ttu-id="86260-119">Wenn Sie die Schnittstelle in der WinMD-Datei (Windows-Runtimemetadaten) definieren können, verwenden Sie das C#/WinRT-Tool.</span><span class="sxs-lookup"><span data-stu-id="86260-119">If you can define the interface in a Windows runtime metadata (WinMD) file, use the C#/WinRT tool instead.</span></span>

- <span data-ttu-id="86260-120">Kennzeichnen Sie die Schnittstelle andernfalls als <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> anstelle von <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, und fügen Sie am Anfang der Schnittstelle drei Platzhaltereinträge für die <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>-Methoden hinzu.</span><span class="sxs-lookup"><span data-stu-id="86260-120">Otherwise, mark the interface as <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIUnknown> instead of <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable>, and add three dummy entries to the start of the interface for the <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable> methods.</span></span> <span data-ttu-id="86260-121">Der folgende Codeausschnitt zeigt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="86260-121">The following code snippet shows an example.</span></span>

  ```csharp
  [InterfaceType(ComInterfaceType.InterfaceIsIUnknown)]
  interface IMine
  {
      // Do not call these three methods.
      // They're exclusively to fill in the slots in the vtable.
      void GetIIdsSlot();
      void GetRuntimeClassNameSlot();
      void GetTrustLevelSlot();

      // The original members of the IMine interface go here.
      ...
  }
  ```

## <a name="affected-apis"></a><span data-ttu-id="86260-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="86260-122">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Runtime.InteropServices.ComInterfaceType.InterfaceIsIInspectable`

### Category

Interop

-->
