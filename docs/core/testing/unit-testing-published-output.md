---
title: Test einer veröffentlichten Ausgabe mit „dotnet vtest“
description: Erfahren Sie, wie Sie mit dem Befehl „dotnet vstest“ Tests für veröffentlichte Bibliotheken statt für den Quellcode ausführen.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 93b2e1a433b5d5b9694257d4d12e47d9107f4cd7
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117025"
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
> Hinweis: Wenn Ihre App Zielversionen für ein anderes Framework als `netcoreapp` festlegt, können Sie den Befehl `dotnet vstest` trotzdem ausführen, indem Sie das Zielframework mit einem Frameworkflag übergeben. Beispiel: `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. In Visual Studio 2017 Update 5 wird das gewünschte Framework automatisch erkannt.

## <a name="see-also"></a>Siehe auch

- [Komponententests mit „dotnet-test“ und xUnit](unit-testing-with-dotnet-test.md)
- [Komponententests mit „dotnet-test“ und NUnit](unit-testing-with-nunit.md)
- [Komponententests mit „dotnet-test“ und MSTest](unit-testing-with-mstest.md)
