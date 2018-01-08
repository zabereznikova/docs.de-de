---
title: "Test einer veröffentlichten Ausgabe mit „dotnet vtest“"
description: "Erfahren Sie, wie Sie mit dem Befehl „dotnet vstest“ Tests für veröffentlichte Ausgaben ausführen."
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 373c557d3fc640ed9071a732bba9f082ca6a4d33
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
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
