---
title: Test einer veröffentlichten Ausgabe mit „dotnet vtest“
description: Erfahren Sie, wie Sie mit dem Befehl „dotnet vstest“ Tests für veröffentlichte Bibliotheken statt für den Quellcode ausführen.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: e4fd25dc9ff30bdfe85cd1167a1dc41ea20a5f80
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771922"
---
# <a name="test-published-output-with-dotnet-vstest"></a>Test einer veröffentlichten Ausgabe mit „dotnet vtest“

Mit dem Befehl `dotnet vstest` können Sie Tests für bereits veröffentlichte Ausgaben ausführen. Dieser kann für xUnit-, MSTest- und NUnit-Tests verwendet werden. Suchen Sie einfach die DLL-Datei, die Teil Ihrer veröffentlichten Ausgabe war, und führen Sie sie aus:

```dotnetcli
dotnet vstest <MyPublishedTests>.dll
```

`<MyPublishedTests>` ist dabei der Name des veröffentlichten Testprojekts.

## <a name="example"></a>Beispiel

Mit den folgenden Befehlen wird das Ausführen von Tests für eine veröffentlichte DLL demonstriert.

```dotnetcli
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> Hinweis: Wenn Ihre App für ein anderes Framework als `netcoreapp` vorgesehen ist, können Sie den Befehl `dotnet vstest` trotzdem ausführen, indem Sie das Zielframework mit einem Frameworkflag übergeben. Beispielsweise `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`. In Visual Studio 2017 Update 5 oder höher wird das gewünschte Framework automatisch erkannt.

## <a name="see-also"></a>Siehe auch

- [Komponententests mit „dotnet-test“ und xUnit](unit-testing-with-dotnet-test.md)
- [Komponententests mit „dotnet-test“ und NUnit](unit-testing-with-nunit.md)
- [Komponententests mit „dotnet-test“ und MSTest](unit-testing-with-mstest.md)
