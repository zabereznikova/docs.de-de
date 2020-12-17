---
title: 'Breaking Change: Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den Environment.OSVersion die tatsächliche Version des Betriebssystems anstelle z. B. des Betriebssystems zurückgibt, das für die Anwendungskompatibilität ausgewählt wurde.
ms.date: 11/01/2020
ms.openlocfilehash: c810d9a7a028a0c60c30d69e78a9b9c695d933ef
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009520"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion

<xref:System.Environment.OSVersion?displayProperty=nameWithType> gibt die tatsächliche Betriebssystemversion (OS) zurück, anstatt beispielsweise das Betriebssystem zurückzugeben, das für die Anwendungskompatibilität ausgewählt ist.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> eine Betriebssystemversion zurück, die möglicherweise falsch ist, wenn eine Anwendung im Windows-Kompatibilitätsmodus ausgeführt wird. Weitere Informationen finden Sie in den [Hinweisen zur GetVersionExA-Funktion](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks). Unter macOS gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> die zugrunde liegende Darwin-Kernelversion zurück.

Ab .NET 5.0 gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> die tatsächliche Version des Windows- oder macOS-Betriebssystems zurück.

In der folgenden Tabelle werden die Verhaltensunterschiede aufgeführt.

|  | Frühere .NET-Versionen | .NET 5 und höher |
|--|------------------------|---------|
| Windows | 6.2.9200.0 | 10.0.19042.0 |
| macOS | 19.6.0.0 | 10.15.7 |

## <a name="reason-for-change"></a>Grund für die Änderung

Benutzer dieser Eigenschaft erwarten, dass die tatsächliche Version des Betriebssystems zurückgegeben wird. Die meisten .NET-Apps geben die unterstützte Version nicht im Anwendungsmanifest an und verwenden daher die standardmäßig unterstützte Version des dotnet-Hosts. Folglich ist der Kompatibilitätsshim für die ausgeführte App nur selten sinnvoll. Wenn Windows eine neue Version veröffentlicht und ein älterer dotnet-Host weiterhin verwendet wird, verwenden diese Apps möglicherweise eine falsche Betriebssystemversion. Die Rückgabe der tatsächlichen Version entspricht eher den Erwartungen der Entwickler dieser API.

Mit der Einführung von <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>, <xref:System.OperatingSystem.IsMacOSVersionAtLeast%2A?displayProperty=nameWithType> und <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute?displayProperty=nameWithType> in .NET 5.0 wurde <xref:System.Environment.OSVersion?displayProperty=nameWithType> geändert, um mehr Konsistenz für Windows und macOS einzuführen.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Überprüfen und testen Sie den von <xref:System.Environment.OSVersion?displayProperty=nameWithType> verwendeten Code, um sicherzustellen, dass sich dieser wie gewünscht verhält.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Environment.OSVersion`

-->
