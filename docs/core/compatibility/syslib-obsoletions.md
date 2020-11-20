---
title: Veraltete Features in .NET 5.0 und höher
description: In diesem Artikel erfahren Sie mehr über APIs, die in .NET 5.0 und höher als veraltet markiert sind und SYSLIB-Compilerwarnungen auslösen.
ms.date: 10/20/2020
ms.openlocfilehash: aa5716ba8fe46c7c4ae2faafe7cc963551eecef7
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440763"
---
# <a name="obsolete-features-in-net-5"></a><span data-ttu-id="6e34c-103">Veraltete Features in .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="6e34c-103">Obsolete features in .NET 5</span></span>

<span data-ttu-id="6e34c-104">Ab .NET 5.0 verwenden einige APIs, die neuerdings als veraltet gekennzeichnet sind, zwei neue Eigenschaften für <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6e34c-104">Starting in .NET 5.0, some APIs that are newly marked as obsolete make use of two new properties on <xref:System.ObsoleteAttribute>.</span></span>

- <span data-ttu-id="6e34c-105">Die Eigenschaft <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> weist den Compiler an, Buildwarnungen mithilfe einer benutzerdefinierten Diagnose-ID zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6e34c-105">The <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> property tells the compiler to generate build warnings using a custom diagnostic ID.</span></span> <span data-ttu-id="6e34c-106">Die benutzerdefinierte ID ermöglicht, dass Warnungen vor veralteten Elementen ausdrücklich und unabhängig voneinander unterdrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="6e34c-106">The custom ID allows for obsoletion warning to be suppressed specifically and separately from one another.</span></span> <span data-ttu-id="6e34c-107">Im Fall von veralteten Elementen in .NET 5.0 und höher lautet das Format für die benutzerdefinierte Diagnose-ID `SYSLIBxxxx`.</span><span class="sxs-lookup"><span data-stu-id="6e34c-107">In the case of the .NET 5+ obsoletions, the format for the custom diagnostic ID is `SYSLIBxxxx`.</span></span>

- <span data-ttu-id="6e34c-108">Die Eigenschaft <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> weist den Compiler an, einen URL-Link einzuschließen, um mehr über das veraltete Element zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="6e34c-108">The <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> property tells the compiler to include a URL link to learn more about the obsoletion.</span></span>

<span data-ttu-id="6e34c-109">Wenn aufgrund einer veralteten API Buildwarnungen oder -fehler auftreten, müssen Sie die Anweisungen für die Diagnose-ID ausführen, die im Abschnitt [Referenz](#reference) aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="6e34c-109">If you encounter build warnings or errors due to usage of an obsolete API, follow the specific guidance provided for the diagnostic ID listed in the [Reference](#reference) section.</span></span> <span data-ttu-id="6e34c-110">Warnungen oder Fehler für diese veralteten Elemente *können nicht* mithilfe der [Standarddiagnose-ID (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) für veraltete Typen oder Member unterdrückt werden. Verwenden Sie stattdessen die benutzerdefinierten Diagnose-ID-Werte im Format `SYSLIBxxxx`.</span><span class="sxs-lookup"><span data-stu-id="6e34c-110">Warnings or errors for these obsoletions *can't* be suppressed using the [standard diagnostic ID (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) for obsolete types or members; use the custom `SYSLIBxxxx` diagnostic ID values instead.</span></span> <span data-ttu-id="6e34c-111">Weitere Informationen finden Sie unter [Unterdrücken von Warnungen](#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="6e34c-111">For more information, see [Suppress warnings](#suppress-warnings).</span></span>

## <a name="reference"></a><span data-ttu-id="6e34c-112">Verweis</span><span class="sxs-lookup"><span data-stu-id="6e34c-112">Reference</span></span>

<span data-ttu-id="6e34c-113">In der folgenden Tabelle finden Sie einen Index für die `SYSLIBxxxx`-Warnungen für veraltete Elemente in .NET 5.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="6e34c-113">The following table provides an index to the `SYSLIBxxxx` obsoletions in .NET 5+.</span></span>

| <span data-ttu-id="6e34c-114">Diagnose-ID</span><span class="sxs-lookup"><span data-stu-id="6e34c-114">Diagnostic ID</span></span> | <span data-ttu-id="6e34c-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e34c-115">Description</span></span> |
| - | - |
| [<span data-ttu-id="6e34c-116">SYSLIB0001</span><span class="sxs-lookup"><span data-stu-id="6e34c-116">SYSLIB0001</span></span>](syslib0001.md) | <span data-ttu-id="6e34c-117">Die UTF-7-Codierung ist unsicher und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e34c-117">The UTF-7 encoding is insecure and should not be used.</span></span> <span data-ttu-id="6e34c-118">Verwenden Sie stattdessen UTF-8.</span><span class="sxs-lookup"><span data-stu-id="6e34c-118">Consider using UTF-8 instead.</span></span> |
| [<span data-ttu-id="6e34c-119">SYSLIB0002</span><span class="sxs-lookup"><span data-stu-id="6e34c-119">SYSLIB0002</span></span>](syslib0002.md) | <span data-ttu-id="6e34c-120"><xref:System.Security.Permissions.PrincipalPermissionAttribute> wird von der Runtime nicht berücksichtigt und darf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e34c-120"><xref:System.Security.Permissions.PrincipalPermissionAttribute> is not honored by the runtime and must not be used.</span></span> |
| [<span data-ttu-id="6e34c-121">SYSLIB0003</span><span class="sxs-lookup"><span data-stu-id="6e34c-121">SYSLIB0003</span></span>](syslib0003.md) | <span data-ttu-id="6e34c-122">Die Codezugriffssicherheit (Code Access Security, CAS) wird von der Runtime nicht unterstützt oder nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="6e34c-122">Code access security (CAS) is not supported or honored by the runtime.</span></span> |
| [<span data-ttu-id="6e34c-123">SYSLIB0004</span><span class="sxs-lookup"><span data-stu-id="6e34c-123">SYSLIB0004</span></span>](syslib0004.md) | <span data-ttu-id="6e34c-124">Das Feature „Eingeschränkte Ausführungsregion (Constrained Execution Region, CER)“ wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e34c-124">The constrained execution region (CER) feature is not supported.</span></span> |
| [<span data-ttu-id="6e34c-125">SYSLIB0005</span><span class="sxs-lookup"><span data-stu-id="6e34c-125">SYSLIB0005</span></span>](syslib0005.md) | <span data-ttu-id="6e34c-126">Der globale Assemblycache (GAC) wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e34c-126">The global assembly cache (GAC) is not supported.</span></span> |
| [<span data-ttu-id="6e34c-127">SYSLIB0006</span><span class="sxs-lookup"><span data-stu-id="6e34c-127">SYSLIB0006</span></span>](syslib0006.md) | <span data-ttu-id="6e34c-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> wird nicht unterstützt und löst <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="6e34c-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="6e34c-129">SYSLIB0007</span><span class="sxs-lookup"><span data-stu-id="6e34c-129">SYSLIB0007</span></span>](syslib0007.md) | <span data-ttu-id="6e34c-130">Die Standardimplementierung dieses Kryptografiealgorithmus wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6e34c-130">The default implementation of this cryptography algorithm is not supported.</span></span> |
| [<span data-ttu-id="6e34c-131">SYSLIB0008</span><span class="sxs-lookup"><span data-stu-id="6e34c-131">SYSLIB0008</span></span>](syslib0008.md) | <span data-ttu-id="6e34c-132">Die <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator>-API wird nicht unterstützt und löst <xref:System.PlatformNotSupportedException>aus.</span><span class="sxs-lookup"><span data-stu-id="6e34c-132">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="6e34c-133">SYSLIB0009</span><span class="sxs-lookup"><span data-stu-id="6e34c-133">SYSLIB0009</span></span>](syslib0009.md) | <span data-ttu-id="6e34c-134">Die Methoden <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> und <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> werden nicht unterstützt und lösen <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="6e34c-134">The <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> and <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> methods are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="6e34c-135">SYSLIB0010</span><span class="sxs-lookup"><span data-stu-id="6e34c-135">SYSLIB0010</span></span>](syslib0010.md) | <span data-ttu-id="6e34c-136">Einige Remoting-APIs werden nicht unterstützt und lösen <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="6e34c-136">Some remoting APIs are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="6e34c-137">SYSLIB0011</span><span class="sxs-lookup"><span data-stu-id="6e34c-137">SYSLIB0011</span></span>](syslib0011.md) | <span data-ttu-id="6e34c-138">Die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Serialisierung ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e34c-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is obsolete and should not be used.</span></span> |
| [<span data-ttu-id="6e34c-139">SYSLIB0012</span><span class="sxs-lookup"><span data-stu-id="6e34c-139">SYSLIB0012</span></span>](syslib0012.md) | <span data-ttu-id="6e34c-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> und <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> sind nur für die .NET Framework-Kompatibilität enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e34c-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> and <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> are only included for .NET Framework compatibility.</span></span> <span data-ttu-id="6e34c-141">Verwenden Sie stattdessen <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6e34c-141">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span> |

## <a name="suppress-warnings"></a><span data-ttu-id="6e34c-142">Unterdrücken von Warnungen</span><span class="sxs-lookup"><span data-stu-id="6e34c-142">Suppress warnings</span></span>

<span data-ttu-id="6e34c-143">Wenn Sie die veralteten APIs verwenden müssen und die `SYSLIBxxxx`-Diagnose keine Fehler anzeigt, können Sie die Warnung im Code oder in der Projektdatei unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="6e34c-143">If you must use the obsolete APIs and the `SYSLIBxxxx` diagnostic does not surface as an error, you can suppress the warning in code or in your project file.</span></span>

<span data-ttu-id="6e34c-144">In Code:</span><span class="sxs-lookup"><span data-stu-id="6e34c-144">In code:</span></span>

```csharp
// Disable the warning.
#pragma warning disable SYSLIB0001
// Code that uses obsolete API.
...
// Re-enable the warning.
#pragma warning restore SYSLIB0001
```

<span data-ttu-id="6e34c-145">Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="6e34c-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
   <TargetFramework>net5.0</TargetFramework>
   <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
   <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
   <!-- To suppress multiple warnings, you can use multiple NoWarn elements -->
   <NoWarn>$(NoWarn);SYSLIB0002</NoWarn>
   <NoWarn>$(NoWarn);SYSLIB0003</NoWarn>
   <!-- Alternatively, you can suppress multiple warnings by using a semicolon-delimited list -->
   <NoWarn>$(NoWarn);SYSLIB0001;SYSLIB0002;SYSLIB0003</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="6e34c-146">Wenn Sie eine Warnung auf diese Weise unterdrücken, werden nur von Ihnen festgelegte Veraltungswarnungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6e34c-146">Suppressing warnings in this way only disables the obsoletion warnings you specify.</span></span> <span data-ttu-id="6e34c-147">Andere Warnungen, einschließlich anderer Veraltungswarnungen, mit unterschiedlichen Diagnose-IDs bleiben weiterhin aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6e34c-147">It doesn't disable any other warnings, including obsoletion warnings with different diagnostic IDs.</span></span>
