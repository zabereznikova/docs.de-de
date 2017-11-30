---
title: "Testen von veröffentlichten Dotnet in der Vstest-Ausgabe"
description: "Informationen Sie zum Ausführen von Tests in der veröffentlichten Ausgabe mit dem Dotnet in der Vstest-Befehl."
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3965e4ca-75b8-4969-b3af-ca993c397a15
ms.openlocfilehash: 217787d41a9da6000941ded6caaa4f44d124644b
ms.sourcegitcommit: 8a4f8e6a7f1341764abcd188a332cc28d1e2d8ec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a>Testen von veröffentlichten Dotnet in der Vstest-Ausgabe

Sie können bei der Ausgabe bereits veröffentlichten Tests ausführen, mit der `dotnet vstest` Befehl. Diese Methode kann auf xUnit, MSTest und NUnit Tests verwendet. Einfach suchen Sie die DLL-Datei, die Teil der veröffentlichten Ausgabe war, und führen Sie:
```
dotnet vstest <MyPublishedTests>.dll
```
wobei `<MyPublishedTests>` ist der Name des veröffentlichten Testprojekts.

### <a name="example-of-running-tests-on-a-published-dll"></a>Beispiel für das Ausführen von Tests auf einer veröffentlichten DLL

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] Hinweis: Wenn Ihre app anders als ein Framework abzielt `netcoreapp` können Sie weiterhin Ausführen der `dotnet vstest` Befehl durch das Zielframework durch ein Framework-Flag übergeben. Beispielsweise `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. In Visual Studio 2017 Update 5 wird das gewünschte Framework automatisch erkannt.

### <a name="related-topics"></a>Verwandte Themen
- [UnitTests mit Test Dotnet und xUnit](unit-testing-with-dotnet-test.md)
- [UnitTests mit Test Dotnet und MSTest](unit-testing-with-mstest.md)
