---
title: Test einer veröffentlichten Ausgabe mit „dotnet vtest“
description: Erfahren Sie, wie Sie mit dem Befehl „dotnet vstest“ Tests für veröffentlichte Ausgaben ausführen.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: dbce1b6e616916e60e56318b773e8fcecbc55580
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33210252"
---
# <a name="test-published-output-with-dotnet-vstest"></a>Test einer veröffentlichten Ausgabe mit „dotnet vtest“

Mit dem Befehl `dotnet vstest` können Sie Tests für bereits veröffentlichte Ausgaben ausführen. Dieser kann für xUnit-, MSTest- und NUnit-Tests verwendet werden. Suchen Sie einfach die DLL-Datei, die Teil Ihrer veröffentlichten Ausgabe war, und führen Sie sie aus:

```
dotnet vstest <MyPublishedTests>.dll
```

`<MyPublishedTests>` ist dabei der Name des veröffentlichten Testprojekts.

## <a name="example-of-running-tests-on-a-published-dll"></a>Beispiel für das Ausführen von Tests für eine veröffentlichte DLL

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> Hinweis: Wenn Ihre App Zielversionen für ein anderes Framework als `netcoreapp` festlegt, können Sie den Befehl `dotnet vstest` trotzdem ausführen, indem Sie das Zielframework mit einem Frameworkflag übergeben. Beispielsweise `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. In Visual Studio 2017 Update 5 wird das gewünschte Framework automatisch erkannt.

## <a name="see-also"></a>Siehe auch
 [Komponententests mit „dotnet-test“ und xUnit](unit-testing-with-dotnet-test.md)  
 [Komponententests mit „dotnet-test“ und MSTest](unit-testing-with-mstest.md)  
