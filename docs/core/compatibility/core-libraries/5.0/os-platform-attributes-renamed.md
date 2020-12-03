---
title: 'Breaking Change: OSPlatform-Attribute umbenannt oder entfernt'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die in einer Vorschauversion eingeführten Betriebssystem-Plattformattribute entfernt oder umbenannt wurden.
ms.date: 11/01/2020
ms.openlocfilehash: 7e709b84005a7b807e390e12d9f36d8b4f73a9df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759417"
---
# <a name="osplatform-attributes-renamed-or-removed"></a><span data-ttu-id="a0984-103">OSPlatform-Attribute umbenannt oder entfernt</span><span class="sxs-lookup"><span data-stu-id="a0984-103">OSPlatform attributes renamed or removed</span></span>

<span data-ttu-id="a0984-104">Die folgenden Attribute, die in .NET 5.0 Preview 8 eingeführt wurden, wurden entfernt oder umbenannt: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute` und `ObsoletedInOSPlatformAttribute`.</span><span class="sxs-lookup"><span data-stu-id="a0984-104">The following attributes that were introduced in .NET 5.0 Preview 8 have been removed or renamed: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, and `ObsoletedInOSPlatformAttribute`.</span></span>

## <a name="change-description"></a><span data-ttu-id="a0984-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a0984-105">Change description</span></span>

<span data-ttu-id="a0984-106">In NET 5.0 Preview 8 wurden die folgenden Attribute im Namespace <xref:System.Runtime.Versioning> eingeführt:</span><span class="sxs-lookup"><span data-stu-id="a0984-106">.NET 5.0 Preview 8 introduced the following attributes in the <xref:System.Runtime.Versioning> namespace:</span></span>

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

<span data-ttu-id="a0984-107">Wenn in .NET 5.0 Preview 8 ein Projekt auf eine betriebssystemspezifische Variante von .NET 5 abzielt, indem ein [Zielframeworkmoniker](../../../../standard/frameworks.md) wie z. B. `net5.0-windows` verwendet wird, fügt der Build das Attribut `System.Runtime.Versioning.MinimumOSPlatformAttribute` auf Assembly-Ebene hinzu.</span><span class="sxs-lookup"><span data-stu-id="a0984-107">In .NET 5.0 Preview 8, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level `System.Runtime.Versioning.MinimumOSPlatformAttribute` attribute.</span></span>

<span data-ttu-id="a0984-108">In .NET 5.0 RC1 wurde `ObsoletedInOSPlatformAttribute` entfernt, und `MinimumOSPlatformAttribute` und `RemovedInOSPlatformAttribute` wurden wie folgt umbenannt:</span><span class="sxs-lookup"><span data-stu-id="a0984-108">In .NET 5.0 RC1, the `ObsoletedInOSPlatformAttribute` has been removed, and `MinimumOSPlatformAttribute` and `RemovedInOSPlatformAttribute` have been renamed as follows:</span></span>

| <span data-ttu-id="a0984-109">Name in Preview 8</span><span class="sxs-lookup"><span data-stu-id="a0984-109">Preview 8 name</span></span> | <span data-ttu-id="a0984-110">Name ab RC1</span><span class="sxs-lookup"><span data-stu-id="a0984-110">RC1 and later name</span></span> |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

<span data-ttu-id="a0984-111">Wenn ab .NET 5.0 RC1 ein Projekt auf eine betriebssystemspezifische Variante von .NET 5 abzielt, indem ein [Zielframeworkmoniker](../../../../standard/frameworks.md) wie z. B. `net5.0-windows` verwendet wird, fügt der Build das Attribut <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> auf Assembly-Ebene hinzu.</span><span class="sxs-lookup"><span data-stu-id="a0984-111">In .NET 5.0 RC1 and later, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> attribute.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="a0984-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="a0984-112">Reason for change</span></span>

<span data-ttu-id="a0984-113">In NET 5.0 Preview 8 wurden Attribute in <xref:System.Runtime.Versioning> eingeführt, um unterstützte Plattformen für APIs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a0984-113">.NET 5.0 Preview 8 introduced attributes in <xref:System.Runtime.Versioning> to specify supported platforms for APIs.</span></span> <span data-ttu-id="a0984-114">Die Attribute werden vom [Analysetool für die Plattformkompatibilität](../../../../core/compatibility/code-analysis.md#ca1416-platform-compatibility) genutzt, um Buildwarnungen zu erzeugen, wenn plattformspezifische APIs auf Plattformen eingesetzt werden, die diese APIs nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a0984-114">The attributes are consumed by the [Platform compatibility analyzer](../../../../core/compatibility/code-analysis.md#ca1416-platform-compatibility) to produce build warnings when platform-specific APIs are consumed on platforms that don't supported those APIs.</span></span>

<span data-ttu-id="a0984-115">In .NET 5.0 RC1 wurde dem Analysetool für die Plattformkompatibilität ein zusätzliches Feature für den Ausschluss von Plattformen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a0984-115">For .NET 5.0 RC1, an additional feature was added to the platform compatibility analyzer for platform exclusion.</span></span> <span data-ttu-id="a0984-116">Diese Feature ermöglicht, dass APIs auf Betriebssystemplattformen als gänzlich nicht unterstützt markiert werden.</span><span class="sxs-lookup"><span data-stu-id="a0984-116">The feature allows APIs to be marked as entirely unsupported on OS platforms.</span></span> <span data-ttu-id="a0984-117">Dieses Feature hat Änderungen an den Attributen veranlasst, einschließlich der Verwendung geeigneterer Namen.</span><span class="sxs-lookup"><span data-stu-id="a0984-117">That feature prompted changes to the attributes, including using more suitable names.</span></span> <span data-ttu-id="a0984-118">`ObsoletedInOSPlatformAttribute` wurde entfernt, da es nicht mehr benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="a0984-118">The `ObsoletedInOSPlatformAttribute` was removed because it was no longer needed.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a0984-119">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a0984-119">Version introduced</span></span>

<span data-ttu-id="a0984-120">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="a0984-120">5.0 RC1</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a0984-121">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="a0984-121">Recommended action</span></span>

<span data-ttu-id="a0984-122">Wenn Sie Ihr Projekt von .NET 5.0 Preview 8 auf .NET 5.0 RC1 umstellen, kann es aufgrund dieser Änderungen zu Build- oder Laufzeitfehlern kommen.</span><span class="sxs-lookup"><span data-stu-id="a0984-122">When you retarget your project from .NET 5.0 Preview 8 to .NET 5.0 RC1, you might encounter build or run-time errors due to these changes.</span></span> <span data-ttu-id="a0984-123">Beispielsweise führt die Umbenennung von `MinimumOSPlatformAttribute` wahrscheinlich zu Fehlern, da das Attribut zur Buildzeit auf plattformspezifische Assemblys angewendet wird und alte Buildartefakte weiterhin auf den alten API-Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="a0984-123">For example, the renaming of `MinimumOSPlatformAttribute` is likely to produce errors, because the attribute is applied to platform-specific assemblies at build time, and old build artifacts will still reference the old API name.</span></span>

<span data-ttu-id="a0984-124">Beispiele für Fehler zur Buildzeit:</span><span class="sxs-lookup"><span data-stu-id="a0984-124">Example build-time errors:</span></span>

- <span data-ttu-id="a0984-125">**Fehler CS0246: Der Typ- oder Namespacename MinimumOSPlatformAttribute wurde nicht gefunden (fehlt eine using-Direktive oder ein Assemblyverweis?)**</span><span class="sxs-lookup"><span data-stu-id="a0984-125">**error CS0246: The type or namespace name 'MinimumOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="a0984-126">**Fehler CS0246: Der Typ- oder Namespacename RemovedInOSPlatformAttribute wurde nicht gefunden (fehlt eine using-Direktive oder ein Assemblyverweis?)**</span><span class="sxs-lookup"><span data-stu-id="a0984-126">**error CS0246: The type or namespace name 'RemovedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="a0984-127">**Fehler CS0246: Der Typ- oder Namespacename ObsoletedInOSPlatformAttribute wurde nicht gefunden (fehlt eine using-Direktive oder ein Assemblyverweis?)**</span><span class="sxs-lookup"><span data-stu-id="a0984-127">**error CS0246: The type or namespace name 'ObsoletedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="a0984-128">Beispiel für Laufzeitfehler:</span><span class="sxs-lookup"><span data-stu-id="a0984-128">Example run-time error:</span></span>

<span data-ttu-id="a0984-129">**„Unbehandelte Ausnahme. System.TypeLoadException: Der Typ System.Runtime.Versioning.MinimumOSPlatformAttribute konnte nicht aus Assembly System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a geladen werden.**</span><span class="sxs-lookup"><span data-stu-id="a0984-129">**Unhandled exception. System.TypeLoadException: Could not load type 'System.Runtime.Versioning.MinimumOSPlatformAttribute' from assembly 'System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'.**</span></span>

<span data-ttu-id="a0984-130">So beheben Sie diese Fehler</span><span class="sxs-lookup"><span data-stu-id="a0984-130">To resolve these errors:</span></span>

- <span data-ttu-id="a0984-131">Ändern Sie alle Verweise auf `MinimumOSPlatformAttribute` in <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a0984-131">Update any references of `MinimumOSPlatformAttribute` to <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="a0984-132">Ändern Sie alle Verweise auf `RemovedInOSPlatformAttribute` in <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a0984-132">Update any references of `RemovedInOSPlatformAttribute` to <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="a0984-133">Entfernen Sie alle Verweise auf `ObsoletedInOSPlatformAttribute`.</span><span class="sxs-lookup"><span data-stu-id="a0984-133">Remove any references to `ObsoletedInOSPlatformAttribute`.</span></span>
- <span data-ttu-id="a0984-134">Erstellen Sie Ihr Projekt neu (oder führen Sie Bereinigung und Build durch), um alte Buildartefakte zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a0984-134">Rebuild your project (or perform clean + build) to delete old build artifacts.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="a0984-135">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a0984-135">Affected APIs</span></span>

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->
