---
title: 'Breaking Change: Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den Environment.OSVersion die tatsächliche Version des Betriebssystems anstelle z. B. des Betriebssystems zurückgibt, das für die Anwendungskompatibilität ausgewählt wurde.
ms.date: 11/01/2020
ms.openlocfilehash: b78ca1c7be50f76b99b5558a976d8f00e2f560c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759566"
---
# <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Rückgabe der korrekten Betriebssystemversion durch Environment.OSVersion

<xref:System.Environment.OSVersion?displayProperty=nameWithType> gibt die tatsächliche Betriebssystemversion (OS) zurück, anstatt beispielsweise das Betriebssystem zurückzugeben, das für die Anwendungskompatibilität ausgewählt ist.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> eine Betriebssystemversion zurück, die möglicherweise falsch ist, wenn eine Anwendung im Windows-Kompatibilitätsmodus ausgeführt wird. Weitere Informationen finden Sie in den [Hinweisen zur GetVersionExA-Funktion](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks).

Ab .NET 5.0 gibt <xref:System.Environment.OSVersion?displayProperty=nameWithType> die tatsächliche Version des Betriebssystems zurück.

## <a name="reason-for-change"></a>Grund für die Änderung

Benutzer dieser Eigenschaft erwarten, dass die tatsächliche Version des Betriebssystems zurückgegeben wird. Die meisten .NET-Apps geben die unterstützte Version nicht im Anwendungsmanifest an und verwenden daher die standardmäßig unterstützte Version des dotnet-Hosts. Folglich ist der Kompatibilitätsshim für die ausgeführte App nur selten sinnvoll. Wenn Windows eine neue Version veröffentlicht und ein älterer dotnet-Host weiterhin verwendet wird, verwenden diese Apps möglicherweise eine falsche Betriebssystemversion. Die Rückgabe der tatsächlichen Version entspricht eher den Erwartungen der Entwickler dieser API.

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
