---
title: Testen in .NET
description: Dieser Artikel bietet eine kurze Übersicht über die Konzepte, die Terminologie und die Tools für Tests in .NET.
author: IEvangelist
ms.author: dapine
ms.date: 10/19/2020
ms.openlocfilehash: 137a8f4e3bc9e3be529d5034c233d283cf158b31
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824856"
---
# <a name="testing-in-net"></a>Testen in .NET

In diesem Artikel wird das Konzept des Testens vorgestellt, und es wird gezeigt, wie verschiedene Arten von Tests zum Überprüfen von Code verwendet werden können. Zum Testen von .NET-Anwendungen stehen verschiedene Tools zur Verfügung, z. B. die [.NET-CLI](#net-cli) und [IDEs (integrierte Entwicklungsumgebungen)](#ide).

## <a name="test-types"></a>Testtypen

Automatisierte Tests sind ideal, um sicherzustellen, dass Anwendungscode so funktioniert, wie es von den Programmierern beabsichtigt war. In diesem Artikel werden Komponententests, Integrationstests und Auslastungstests behandelt.

### <a name="unit-tests"></a>Komponententests

Bei einem *Komponententest* handelt es sich um einen Test, der einzelne Softwarekomponenten oder Methoden, auch als „Arbeitseinheit“ bezeichnet, ausgeführt werden. Komponententests sollten nur Code testen, für den der Entwickler zuständig ist. Es werden keine Aspekte der Infrastruktur getestet. Ein Beispiel für einen Aspekt der Infrastruktur ist etwa die Interaktion mit Datenbanken, Dateisystemen und Netzwerkressourcen.

Weitere Informationen zum Erstellen von Komponententests finden Sie unter [Testtools](#testing-tools).

### <a name="integration-tests"></a>Integrationstests

Ein *Integrationstest* unterscheidet sich von einem Komponententest insofern, dass er die Funktionsfähigkeit von zwei oder mehr Softwarekomponenten gemeinsam überprüft, d. h. deren „Integration“. Diese Tests decken ein breiteres Spektrum des zu testenden Systems ab, während Komponententests auf einzelne Komponenten beschränkt sind. Häufig werden bei Integrationstests auch Aspekte der Infrastruktur berücksichtigt.

### <a name="load-tests"></a>Auslastungstests

Bei einem *Auslastungstest* wird ermittelt, ob ein System eine bestimmte Auslastung verarbeiten kann, z. B. eine bestimmte Anzahl gleichzeitiger Benutzer, die eine Anwendung verwenden, und eine verzögerungsfreie Verarbeitung von Interaktionen. Weitere Informationen zu Auslastungstests für Webanwendungen finden Sie unter [Auslastungs-/Belastungstests in ASP.NET Core](/aspnet/core/test/load-tests).

## <a name="test-considerations"></a>Überlegungen zu Tests

Beachten Sie die [bewährten Methoden](unit-testing-best-practices.md) für das Schreiben von Tests. Beispielsweise wird bei der [testgesteuerten Entwicklung (Test Driven Development, TDD)](https://deviq.com/test-driven-development) ein Komponententest vor dem Code geschrieben, der damit getestet werden soll. Stellen Sie sich die TDD wie eine Gliederung für ein Buch vor, bevor es geschrieben wird. Dadurch sollen Entwickler einfacheren, lesbareren und effizienteren Code schreiben können.

## <a name="testing-tools"></a>Testtools

.NET ist eine mehrsprachige Entwicklungsplattform, und Sie können verschiedene Testtypen für [C#](../../csharp/index.yml), [F#](../../fsharp/index.yml) und [Visual Basic](../../visual-basic/index.yml) schreiben. Für jede dieser Sprachen können Sie aus mehreren Testframeworks wählen.

### <a name="xunit"></a>xUnit

[xUnit](https://xunit.net) ist ein kostenloses Open-Source-Tool für Komponententests für .NET mit Unterstützung durch die Community. xUnit.net wurde vom ursprünglichen Erfinder von NUnit v2 geschrieben und stellt die neueste Technologie für Komponententests für .NET-Apps dar. xUnit.net kann mit ReSharper, CodeRush, TestDriven.NET und [Xamarin](https://dotnet.microsoft.com/apps/xamarin) verwendet werden. Es handelt sich dabei um ein Projekt der [.NET Foundation](https://dotnetfoundation.org), das deren Verhaltensregeln folgt.

Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Komponententests mit C#](unit-testing-with-dotnet-test.md)
- [Komponententests mit F#](unit-testing-fsharp-with-dotnet-test.md)
- [Komponententests mit Visual Basic](unit-testing-visual-basic-with-dotnet-test.md)

### <a name="nunit"></a>NUnit

[NUnit](https://nunit.org) ist ein Komponententest-Framework für alle .NET-Sprachen. Ausgangspunkt war eine Portierung von JUnit. Die aktuelle Produktionsversion wurde neu programmiert und um viele neue Features und Unterstützung für eine Vielzahl von .NET-Plattformen erweitert. NUnit ist ein Projekt der [.NET Foundation](https://dotnetfoundation.org).

Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Komponententests mit C#](unit-testing-with-nunit.md)
- [Komponententests mit F#](unit-testing-fsharp-with-nunit.md)
- [Komponententests mit Visual Basic](unit-testing-visual-basic-with-nunit.md)

### <a name="mstest"></a>MSTest

[MSTest](https://github.com/Microsoft/testfx-docs) ist das Microsoft-Testframework für alle .NET-Sprachen. Es ist erweiterbar und funktioniert sowohl mit der .NET-CLI als auch mit Visual Studio. Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Komponententests mit C#](unit-testing-with-mstest.md)
- [Komponententests mit F#](unit-testing-fsharp-with-mstest.md)
- [Komponententests mit Visual Basic](unit-testing-visual-basic-with-mstest.md)

### <a name="net-cli"></a>.NET CLI

Mit dem Befehl [dotnet test](../tools/dotnet-test.md) in der [.NET-CLI](../tools/index.md) können Sie Komponententests für Lösungen ausführen. Die .NET-CLI macht die meisten Funktionen verfügbar, die in [integrierten Entwicklungsumgebungen (IDEs)](#ide) über die Benutzeroberfläche verfügbar sind. Die .NET-CLI ist plattformübergreifend und kann im Rahmen von Continuous Integration- und Continuous Delivery-Pipelines verwendet werden. Die .NET-CLI unterstützt skriptgesteuerte Prozesse, um häufige Aufgaben zu automatisieren.

### <a name="ide"></a>IDE

Visual Studio, Visual Studio für Mac und Visual Studio Code bieten grafische Benutzeroberflächen für Testfunktionen. In den IDEs stehen mehr Funktionen als bei der CLI zur Verfügung, z. B. [Live Unit Testing](/visualstudio/test/live-unit-testing). Weitere Informationen finden Sie unter [Einschließen und Ausschließen von Testprojekten und Testmethoden](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).

## <a name="see-also"></a>Weitere Informationen:

Weitere Informationen finden Sie in den folgenden Artikeln:

- [Bewährte Methoden für Komponententests mit .NET](unit-testing-best-practices.md)
- [Integrationstests in ASP.NET Core](/aspnet/core/test/integration-tests#test-app-prerequisites)
- [Ausführen von selektiven Komponententests](selective-unit-tests.md)
- [Verwenden von Code Coverage für Komponententests](unit-testing-code-coverage.md)
