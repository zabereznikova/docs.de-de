---
title: Unittests in .NET Core
description: Unittests in .NET Core
keywords: .NET, .NET Core
author: ardalis
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 815ac74c-4bd9-4a94-a87c-78288b27c0e2
translationtype: Human Translation
ms.sourcegitcommit: 149086110d7470d97e1ab3e5969269626290b523
ms.openlocfilehash: 94bae12916fd20f534916d97157605c6a9aa9202

---

# <a name="unit-testing-in-net-core"></a>Unittests in .NET Core

Von [Steve Smith](http://ardalis.com) und [Bill Wagner](https://github.com/BillWagner)

.NET Core wurde mit Prüfbarkeit als Hintergedanke entwickelt, sodass das Erstellen von Unittests für Ihre Anwendung einfacher als je zuvor ist. Dieser Artikel gibt eine kurze Einführung zu Unittests (und wie sich diese von anderen Arten von Tests unterscheiden).
Verknüpfte Ressourcen zeigen, wie ein Testprojekt einer Lösung zugeordnet wird und anschließend Unittests mithilfe der Befehlszeile oder Visual Studio ausgeführt werden.

## <a name="getting-started-with-testing"></a>Erste Schritte mit Tests
 
Eine Suite von automatisierten Tests ist eine der besten Möglichkeiten, um sicherzustellen, dass eine Softwareanwendung das tut, was von den Autoren verlangt wurde. Es gibt viele verschiedene Arten von Tests für Softwareanwendungen, einschließlich Integrationstests, Webtests, Auslastungstests und viele mehr. Auf der untersten Ebene befinden sich die Unittests, die einzelne Softwarekomponenten oder Methoden testen. Unittests sollen nur Code im Steuerelement des Entwicklers testen und nicht Infrastrukturprobleme wie z.B. Datenbanken, Dateisysteme oder Netzwerkressourcen. Unittests können mithilfe der [testgesteuerten Entwicklung](http://deviq.com/test-driven-development/) (Test Driven Development, TDD) geschrieben werden, oder sie können einem vorhandenen Code hinzugefügt werden, um dessen Richtigkeit zu bestätigen. In beiden Fällen sollten sie klein, gut benannt und schnell sein, da Sie im Idealfall hunderte davon ausführen möchten, bevor Sie Ihre Änderungen dem freigegebenen Coderepository des Projekts übergeben.

> [!NOTE]
> Entwickler haben oft Probleme bei der Benennung für ihre Testklassen und Methoden. Als Ausgangspunkt befolgt das ASP.NET-Produktteam [diesen Konventionen](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests).

Wenn Sie Unittests schreiben, achten Sie darauf, dass Sie nicht versehentlich Abhängigkeiten der Infrastruktur einführen. Dies führt in der Regel dazu, dass Tests langsamer und anfälliger sind und sollten deshalb für Integrationstests reserviert werden. Sie können diese versteckten Abhängigkeiten in Ihrem Anwendungscode vermeiden, indem Sie das [Explicit Dependencies Principle (Explizites Abhängigkeitsprinzip)](http://deviq.com/explicit-dependencies-principle/) befolgen und [Dependency Injection (Abhängigkeitseinfügung)](https://docs.asp.net/en/latest/fundamentals/dependency-injection.html) verwenden, um Ihre Abhängigkeiten vom Framework anzufordern. Sie können Ihre Unittests auch auf ein separates Projekt von Ihren Integrationstests beschränken, und sicherstellen, dass Ihr Unittestprojekt nicht über Referenzen für oder Abhängigkeiten auf den Infrastrukturpaketen verfügt.

Möchten Sie mehr über Unittests in .NET Core-Projekten erfahren?

Probieren Sie diese [exemplarische Vorgehensweise mit xunit und der.NET CLI (in englischer Sprache)](unit-testing-with-dotnet-test.md).

Das XUnit-Team hat ein Tutorial geschrieben, das zeigt, [wie xunit mit .NET Core und Visual Studio verwendet werden (in englischer Sprache)](http://xunit.github.io/docs/getting-started-dotnet-core.html).



<!--HONumber=Nov16_HO1-->


