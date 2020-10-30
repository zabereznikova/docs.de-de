---
title: Veraltete Features in .NET 5.0 und höher
description: In diesem Artikel erfahren Sie mehr über APIs, die in .NET 5.0 und höher als veraltet markiert sind und SYSLIB-Compilerwarnungen auslösen.
ms.date: 10/20/2020
ms.openlocfilehash: 13f5fb10cfe693ed621b3f45fc22e024875890c8
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333093"
---
# <a name="obsolete-features-in-net-5"></a>Veraltete Features in .NET 5.0

Ab .NET 5.0 verwenden einige APIs, die neuerdings als veraltet gekennzeichnet sind, zwei neue Eigenschaften für <xref:System.ObsoleteAttribute>.

- Die Eigenschaft <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> weist den Compiler an, Buildwarnungen mithilfe einer benutzerdefinierten Diagnose-ID zu generieren. Die benutzerdefinierte ID ermöglicht, dass Warnungen vor veralteten Elementen ausdrücklich und unabhängig voneinander unterdrückt werden können. Im Fall von veralteten Elementen in .NET 5.0 und höher lautet das Format für die benutzerdefinierte Diagnose-ID `SYSLIBxxxx`.

- Die Eigenschaft <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> weist den Compiler an, einen URL-Link einzuschließen, um mehr über das veraltete Element zu erfahren.

Wenn aufgrund einer veralteten API Buildwarnungen oder -fehler auftreten, müssen Sie die Anweisungen für die Diagnose-ID ausführen, die im Abschnitt [Referenz](#reference) aufgeführt sind. Warnungen oder Fehler für diese veralteten Elemente *können nicht* mithilfe der [Standarddiagnose-ID (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) für veraltete Typen oder Member unterdrückt werden. Verwenden Sie stattdessen die benutzerdefinierten Diagnose-ID-Werte im Format `SYSLIBxxxx`. Weitere Informationen finden Sie unter [Unterdrücken von Warnungen](#suppress-warnings).

## <a name="reference"></a>Verweis

In der folgenden Tabelle finden Sie einen Index für die `SYSLIBxxxx`-Warnungen für veraltete Elemente in .NET 5.0 und höher.

| Diagnose-ID | BESCHREIBUNG |
| - | - |
| [SYSLIB0001](syslib0001.md) | Die UTF-7-Codierung ist unsicher und sollte nicht verwendet werden. Verwenden Sie stattdessen UTF-8. |
| [SYSLIB0002](syslib0002.md) | <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird von der Runtime nicht berücksichtigt und darf nicht verwendet werden. |
| [SYSLIB0003](syslib0003.md) | Die Codezugriffssicherheit (Code Access Security, CAS) wird von der Runtime nicht unterstützt oder nicht berücksichtigt. |
| [SYSLIB0004](syslib0004.md) | Das Feature „Eingeschränkte Ausführungsregion (Constrained Execution Region, CER)“ wird nicht unterstützt. |
| [SYSLIB0005](syslib0005.md) | Der globale Assemblycache (GAC) wird nicht unterstützt. |
| [SYSLIB0006](syslib0006.md) | <xref:System.Threading.Thread.Abort?displayProperty=nameWithType> wird nicht unterstützt und löst <xref:System.PlatformNotSupportedException> aus. |
| [SYSLIB0007](syslib0007.md) | Die Standardimplementierung dieses Kryptografiealgorithmus wird nicht unterstützt. |
| [SYSLIB0008](syslib0008.md) | Die <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator>-API wird nicht unterstützt und löst <xref:System.PlatformNotSupportedException>aus. |
| [SYSLIB0009](syslib0009.md) | Die Methoden <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> und <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> werden nicht unterstützt und lösen <xref:System.PlatformNotSupportedException> aus. |
| [SYSLIB0010](syslib0010.md) | Einige Remoting-APIs werden nicht unterstützt und lösen <xref:System.PlatformNotSupportedException> aus. |
| [SYSLIB0011](syslib0011.md) | Die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Serialisierung ist veraltet und sollte nicht verwendet werden. |
| [SYSLIB0012](syslib0012.md) | <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> und <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> sind nur für die .NET Framework-Kompatibilität enthalten. Verwenden Sie stattdessen <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>. |

## <a name="suppress-warnings"></a>Unterdrücken von Warnungen

Wenn Sie die veralteten APIs verwenden müssen und die `SYSLIBxxxx`-Diagnose keine Fehler anzeigt, können Sie die Warnung im Code oder in der Projektdatei unterdrücken.

In Code:

```csharp
// Disable the warning.
#pragma warning disable SYSLIB0001
// Code that uses obsolete API.
...
// Re-enable the warning.
#pragma warning restore SYSLIB0001
```

Projektdatei:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
   <TargetFramework>net5.0</TargetFramework>
   <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
   <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> Wenn Sie eine Warnung auf diese Weise unterdrücken, wird nur die Warnung vor diesem spezifischen veralteten Element deaktiviert. Andere Warnungen, einschließlich anderer Veraltungswarnungen, bleiben weiterhin aktiviert.
