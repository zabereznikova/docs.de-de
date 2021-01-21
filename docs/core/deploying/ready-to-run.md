---
title: Übersicht über die ReadyToRun-Bereitstellung
description: Erfahren Sie, was ReadyToRun-Bereitstellungen sind und warum Sie diese als Teil Ihrer App-Veröffentlichung mit .NET 5 und .NET Core 3.0 und höher in Erwägung ziehen sollten.
author: davidwrighton
ms.author: davidwr
ms.date: 09/21/2020
ms.openlocfilehash: 2d4aaac2534bbb1279eb88d8e24e1f5f022afe7d
ms.sourcegitcommit: 3a8f1979a98c6c19217a1930e0af5908988eb8ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536098"
---
# <a name="readytorun-compilation"></a>ReadyToRun-Kompilierung

Die Start- und Wartezeiten für .NET-Anwendungen können verbessert werden, indem Sie Ihre Anwendungsassemblys im R2R-Format (ReadyToRun) kompilieren. R2R ist eine Form der AOT-Kompilierung (Ahead-Of-Time).

R2R-Binärdateien verbessern die Startleistung, indem sie den Arbeitsaufwand des JIT-Compilers (Just-in-time) reduzieren, der anfällt, wenn Ihre Anwendung geladen wird. Die Binärdateien enthalten ähnlichen nativen Code im Vergleich zu dem, was der JIT-Compiler produzieren würde. R2R-Binärdateien sind jedoch größer, da sie sowohl IL-Code (Intermediate Language, Zwischensprache), der für einige Szenarios noch benötigt wird, als auch die native Version des gleichen Codes enthalten. R2R ist nur bei Veröffentlichung einer App verfügbar, die auf bestimmte Laufzeitumgebungen (RID) wie Linux x64 oder Windows x64 ausgerichtet ist.

Damit Ihr Projekt als ReadyToRun kompiliert werden kann, muss die PublishReadyToRun-Eigenschaft bei der Anwendungsveröffentlichung auf `true` festgelegt sein.

Es gibt zwei Möglichkeiten, Ihre App als ReadyToRun zu veröffentlichen:

01. Geben Sie das Flag „PublishReadyToRun“ direkt im Befehl „dotnet publish“ an. Weitere Informationen finden Sie unter [dotnet publish](../tools/dotnet-publish.md).

    ```dotnetcli
    dotnet publish -c Release -r win-x64 -p:PublishReadyToRun=true
    ```

02. Geben Sie die Eigenschaft im Projekt an.

    - Fügen Sie Ihrem Projekt die Einstellung `<PublishReadyToRun>` hinzu.

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

    - Veröffentlichen Sie die Anwendung ohne spezielle Parameter.

    ```dotnetcli
    dotnet publish -c Release -r win-x64
    ```

## <a name="impact-of-using-the-readytorun-feature"></a>Auswirkungen der Verwendung des ReadyToRun-Features

Die Ahead-of-Time-Kompilierung hat komplexe Auswirkungen auf die Anwendungsleistung, die sich möglicherweise nur schwer vorhersagen lassen. Im allgemeinen wächst die Größe einer Assembly auf das Zwei- bis Dreifache an. Durch diese Zunahme der physischen Dateigröße kann sich die Leistung beim Laden der Assembly von einem Datenträger verringern und der Arbeitssatz des Prozesses erhöhen. Auf der anderen Seite wird die Anzahl von Methoden, die zur Laufzeit kompiliert werden, in der Regel erheblich reduziert. Unterm Strich können die meisten Anwendungen mit umfangreichem Code durch die Aktivierung von ReadyToRun von großen Leistungsvorteilen profitieren. Bei Anwendungen, die nur eine geringe Codemenge umfassen, können durch die Aktivierung von ReadyToRun wahrscheinlich keine wesentliche Verbesserung erzielen, weil die .NET-Runtimebibliotheken bereits mit ReadyToRun vorkompiliert wurden.

Die hier beschriebene Startverbesserung gilt nicht nur für den Anwendungsstart, sondern auch für die erste Verwendung von Code in der Anwendung. So kann beispielsweise die Antwortlatenz bei der ersten Verwendung der Web-API in einer ASP.NET-Anwendung mithilfe von ReadyToRun reduziert werden.

### <a name="interaction-with-tiered-compilation"></a>Interaktion mit mehrstufiger Kompilierung

Der durch die Ahead-of-Time-Kompilierung generierte Code ist nicht so stark optimiert wie Code, der durch die JIT-Kompilierung erzeugt wird. Um dieses Problem zu beheben, werden bei der mehrstufigen Kompilierung häufig verwendete ReadyToRun-Methoden durch JIT-generierte Methoden ersetzt.

## <a name="how-is-the-set-of-precompiled-assemblies-chosen"></a>Wie wird der Satz vorkompilierter Assemblys ausgewählt?

Das SDK führt eine Vorkompilierung der Assemblys aus, die mit der Anwendung verteilt werden. Bei eigenständigen Anwendungen schließt dieser Satz von Assemblys das Framework mit ein. C++-/CLI-Binärdateien sind für die ReadyToRun-Kompilierung nicht geeignet.

## <a name="how-is-the-set-of-methods-to-precompile-chosen"></a>Wie wird der Satz von Methoden für die Vorkompilierung ausgewählt?

Der Compiler versucht, so viele Methoden wie möglich vorab zu kompilieren. Aus verschiedenen Gründen ist jedoch nicht zu erwarten, dass die Verwendung des ReadyToRun-Features eine JIT-Ausführung verhindert. Hierzu gehören:

- Verwendung generischer Typen, die in separaten Assemblys definiert sind
- Interop mit nativem Code
- Verwendung intrinsischer Hardwarefunktionen, deren Verwendung auf einem Zielcomputer vom Compiler nicht als sicher eingestuft werden kann
- Bestimmte ungewöhnliche IL-Muster
- Dynamische Methodenerstellung über Reflexion oder LINQ

## <a name="cross-platformarchitecture-restrictions"></a>Plattformübergreifende bzw. architekturbezogene Einschränkungen

Für einige SDK-Plattformen kann der ReadyToRun-Compiler eine Crosskompilierung für andere Zielplattformen durchführen. Die unterstützten Kompilierungsziele werden in der folgenden Tabelle beschrieben.

| SDK-Plattform | Unterstützte Plattformen |
| ------------ | --------------------------- |
| Windows X64  | Windows X86, Windows X64, Windows ARM32, Windows ARM64 |
| Windows X86  | Windows X86, Windows ARM32 |
| Linux X64    | Linux X86, Linux X64, Linux ARM32, Linux ARM64 |
| Linux ARM32  | Linux ARM32 |
| Linux ARM64  | Linux ARM64 |
| macOS X64    | macOS X64 |
