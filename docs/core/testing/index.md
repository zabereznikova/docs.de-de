---
title: Komponententests in .NET Core und .NET Standard
description: Dieser Artikel bietet eine kurze Übersicht über Komponententests für .NET Core- und .NET Standard-Projekte.
author: ardalis
ms.author: wiwagn
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: e15f80b173389cdff86c6e62013e9c0f21171dd6
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703108"
---
# <a name="unit-testing-in-net-core-and-net-standard"></a>Komponententests in .NET Core und .NET Standard

Mit .NET Core können Sie im Handumdrehen Komponententests erstellen. Dieser Artikel gibt eine kurze Einführung zu Komponententests (und wie sich diese von anderen Arten von Tests unterscheiden). Über die am Ende der Seite verlinkten Ressourcen erfahren Sie, wie Sie einer Projektmappe ein neues Testprojekt hinzufügen. Nachdem Sie Ihre Testprojekte erstellt haben, können Sie Ihre Komponententests über die Befehlszeile oder Visual Studio durchführen.

Wenn Sie ein **ASP.NET Core**-Projekt testen, finden Sie weitere Informationen unter [Integrationstests in ASP.NET Core](/aspnet/core/test/integration-tests#test-app-prerequisites).

.NET Core 2.0 und höher unterstützt [.NET Standard 2.0](../../standard/net-standard.md). Wir verwenden die dazugehörigen Bibliotheken, um Komponententests zu veranschaulichen.

Sie können in .NET Core 2.0 oder höher integrierte Vorlagen für Komponententestprojekte für C#, F# und Visual Basic als Ausgangspunkt für Ihr eigenes Projekt verwenden.

## <a name="what-are-unit-tests"></a>Was sind Komponententests?

Mit automatisierten Tests können Sie sicherstellen, dass eine Softwareanwendung das tut, was die Autoren möchten. Es gibt mehrere Arten von Tests für Softwareanwendungen. Dazu zählen u.a. Integrationstests, Webtests und Auslastungstests. **Komponententests** testen einzelne Softwarekomponenten und Methoden. Komponententests sollten nur den Code testen, für den der Entwickler zuständig ist. Sie sollten keine Aspekte der Infrastruktur testen. Aspekte der Infrastruktur sind z.B. Datenbanken, Dateisysteme und Netzwerkressourcen.

Beachten Sie, dass es bewährte Methode für das Schreiben von Tests gibt. Bei der [testgesteuerten Entwicklung (Test Driven Development, TDD)](https://deviq.com/test-driven-development/) wird ein Komponententest vor dem Code geschrieben, den er prüfen soll. Stellen Sie sich die TDD wie eine Gliederung für ein Buch vor, bevor dieses geschrieben wird. Dadurch sollen Entwickler einfacheren, lesbareren und effizienteren Code schreiben können.

> [!NOTE]
> Das ASP.NET-Team hält sich an [diese Konventionen](https://github.com/dotnet/aspnetcore/wiki/Engineering-guidelines#unit-tests-and-functional-tests), um Entwicklern das Festlegen von aussagekräftigen Namen für Testklassen und -methoden zu erleichtern.

Achten Sie beim Schreiben von Komponententests darauf, dass diese nicht von der Infrastruktur abhängig sind. Dadurch werden die Tests langsam und fehleranfällig. Diese Abhängigkeiten sollten nur bei Integrationstests bestehen. Sie können diese Abhängigkeiten in Ihrem Code vermeiden, indem Sie das [Prinzip der expliziten Abhängigkeit](https://deviq.com/explicit-dependencies-principle/) und [Dependency Injection](/aspnet/core/fundamentals/dependency-injection) einsetzen. Sie können die Komponententests und die Integrationstests in unterschiedlichen Projekten erstellen. Dadurch wird sichergestellt, dass Ihr Komponententestprojekt keine Verweise auf oder Abhängigkeiten von Infrastrukturpaketen aufweist.

## <a name="next-steps"></a>Nächste Schritte

Mehr Informationen zu Unittests in .NET Core-Projekten:

.NET Core-Komponententestprojekte werden für folgende Programmiersprachen unterstützt:

- [C#](../../csharp/index.yml)
- [F#](../../fsharp/index.yml)
- [Visual Basic](../../visual-basic/index.yml)

Sie können auch zwischen mehreren Komponententestframeworks auswählen:

- [xUnit](https://xunit.net/)
- [NUnit](https://nunit.org)
- [MSTest](https://github.com/Microsoft/testfx-docs)

In den folgenden exemplarischen Vorgehensweisen erfahren Sie mehr:

:::zone pivot="mstest"

- Erstellen von Komponententests mit [*MSTest* und *C#* mit der .NET Core-CLI](unit-testing-with-mstest.md).
- Erstellen von Komponententests mit [*MSTest* und *F#* mit der .NET Core-CLI](unit-testing-fsharp-with-mstest.md).
- Erstellen von Komponententests mit [*MSTest* und *Visual Basic* mit der .NET Core-CLI](unit-testing-visual-basic-with-mstest.md).

:::zone-end
:::zone pivot="xunit"

- Erstellen von Komponententests mit [*xUnit* und *C#* mit der .NET Core-CLI](unit-testing-with-dotnet-test.md).
- Erstellen von Komponententests mit [*xUnit* und *F#* mit der .NET Core-CLI](unit-testing-fsharp-with-dotnet-test.md).
- Erstellen von Komponententests mit [*xUnit* und *Visual Basic* mit der .NET Core-CLI](unit-testing-visual-basic-with-dotnet-test.md).

:::zone-end
:::zone pivot="nunit"

- Erstellen von Komponententests mit [*NUnit* und *C#* mit der .NET Core-CLI](unit-testing-with-nunit.md).
- Erstellen von Komponententests mit [*NUnit* und *F#* mit der .NET Core-CLI](unit-testing-fsharp-with-nunit.md).
- Erstellen von Komponententests mit [*NUnit* und *Visual Basic* mit der .NET Core-CLI](unit-testing-visual-basic-with-nunit.md).

:::zone-end

In den folgenden Artikeln erfahren Sie mehr:

- Visual Studio Enterprise bietet nützliche Testtools für .NET Core. Weitere Informationen finden Sie in den Artikel zu [Live Unit Testing](/visualstudio/test/live-unit-testing) und [Codeabdeckung](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage).
- Weitere Informationen zum Durchführen selektiver Komponententests finden Sie unter [Ausführen von selektiven Komponententests](selective-unit-tests.md) und [Including and excluding test projects and test methods](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods) (Einbeziehen und Ausschließen von Testprojekten und Testmethoden).
- [Verwenden von XUnit mit .NET Core und Visual Studio](https://xunit.github.io/docs/getting-started-dotnet-core.html)
