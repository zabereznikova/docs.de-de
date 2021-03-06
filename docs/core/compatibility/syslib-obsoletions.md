---
title: Veraltete Features in .NET 5.0 und höher
description: In diesem Artikel erfahren Sie mehr über APIs, die in .NET 5.0 und höher als veraltet markiert sind und SYSLIB-Compilerwarnungen auslösen.
ms.date: 10/20/2020
ms.openlocfilehash: 336958c93e3db8f66cfbec89476a666e5e103b70
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593304"
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
| [SYSLIB0001](syslib-warnings/syslib0001.md) | Die UTF-7-Codierung ist unsicher und sollte nicht verwendet werden. Verwenden Sie stattdessen UTF-8. |
| [SYSLIB0002](syslib-warnings/syslib0002.md) | <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird von der Runtime nicht berücksichtigt und darf nicht verwendet werden. |
| [SYSLIB0003](syslib-warnings/syslib0003.md) | Die Codezugriffssicherheit (Code Access Security, CAS) wird von der Runtime nicht unterstützt oder nicht berücksichtigt. |
| [SYSLIB0004](syslib-warnings/syslib0004.md) | Das Feature „Eingeschränkte Ausführungsregion (Constrained Execution Region, CER)“ wird nicht unterstützt. |
| [SYSLIB0005](syslib-warnings/syslib0005.md) | Der globale Assemblycache (GAC) wird nicht unterstützt. |
| [SYSLIB0006](syslib-warnings/syslib0006.md) | <xref:System.Threading.Thread.Abort?displayProperty=nameWithType> wird nicht unterstützt und löst <xref:System.PlatformNotSupportedException> aus. |
| [SYSLIB0007](syslib-warnings/syslib0007.md) | Die Standardimplementierung dieses Kryptografiealgorithmus wird nicht unterstützt. |
| [SYSLIB0008](syslib-warnings/syslib0008.md) | Die <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator>-API wird nicht unterstützt und löst <xref:System.PlatformNotSupportedException>aus. |
| [SYSLIB0009](syslib-warnings/syslib0009.md) | Die Methoden <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> und <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> werden nicht unterstützt und lösen <xref:System.PlatformNotSupportedException> aus. |
| [SYSLIB0010](syslib-warnings/syslib0010.md) | Einige Remoting-APIs werden nicht unterstützt und lösen <xref:System.PlatformNotSupportedException> aus. |
| [SYSLIB0011](syslib-warnings/syslib0011.md) | Die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>-Serialisierung ist veraltet und sollte nicht verwendet werden. |
| [SYSLIB0012](syslib-warnings/syslib0012.md) | <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> und <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> sind nur für die .NET Framework-Kompatibilität enthalten. Verwenden Sie stattdessen <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>. |

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
   <!-- To suppress multiple warnings, you can use multiple NoWarn elements -->
   <NoWarn>$(NoWarn);SYSLIB0002</NoWarn>
   <NoWarn>$(NoWarn);SYSLIB0003</NoWarn>
   <!-- Alternatively, you can suppress multiple warnings by using a semicolon-delimited list -->
   <NoWarn>$(NoWarn);SYSLIB0001;SYSLIB0002;SYSLIB0003</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> Wenn Sie eine Warnung auf diese Weise unterdrücken, werden nur von Ihnen festgelegte Veraltungswarnungen deaktiviert. Andere Warnungen, einschließlich anderer Veraltungswarnungen, mit unterschiedlichen Diagnose-IDs bleiben weiterhin aktiviert.
