---
title: .NET Core-CLI-Testkommunikationsprotokoll
description: .NET Core-CLI-Testkommunikationsprotokoll
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 88cba792-3640-41de-b55d-00f575e9d5e2
translationtype: Human Translation
ms.sourcegitcommit: 81e7604f0a646e5de9c2ed35ff3b6ef6d7fb2e71
ms.openlocfilehash: a35385cbb08614493fdcfc74504b00178dc532ea

---

#<a name="net-core-cli-test-communication-protocol"></a>.NET Core-CLI-Testkommunikationsprotokoll

## <a name="introduction"></a>Einführung
Jedes Mal, wenn Sie einen Port an dotnet test übergeben, wird der Befehl in der Entwurfszeit durchgeführt. Dies bedeutet, dass dotnet test sich mit diesem Port mithilfe von TCP verbindet, und dann einen eingerichteten Satz an Meldungen mit allem austauchen, was mit diesem Port verbunden ist. In diesem Fall erhält der Runner auch einen neuen Port, der von dotnet test für die Kommunikation verwendet wird. Der Runner verwendet auch TCP, um mit dotnet test zu kommunizieren, da es im Entwurfsmodus nicht ausreichend ist, die Ergebnisse nur in der Konsole auszugeben. Der Befehl muss die Adapterstrukturmeldungen senden, die die Ergebnisse der Testausführung enthalten.

### <a name="communication-protocol-at-design-time"></a>Kommunikationsprotokoll zur Entwurfszeit

1. Da dotnet test während der Entwurfszeit beim Starten mit einem Port verbunden ist, muss der Adapter diesen Port abhören, da andernfalls dotnet test fehlschlägt. Der Adapter kann dadurch alle von ihm benötigten Ports reservieren, indem er sich an sie bindet und sie abhört, bevor dotnet test durchgeführt wurde und versucht hat, die Ports für den Runner zu erhalten.
2. Wenn dotnet test gestartet wird, wird eine TestSession.Connected-Meldung an den Adapter gesendet, die angibt, dass dotnet test von nun an Meldungen empfangen kann.
3. Es ist möglich, eine optionale Meldung zur [Versionsprüfung](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/ProtocolVersionMessage.cs) zu senden, die die Adapterversion des Protokolls enthält. Dotnet test sendet die Version des Protokolls zurück, die unterstützt wird.

Alle Meldungen verfügen über das Format, das hier beschrieben wird: [Message.cs](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/Message.cs). Die Nutzlastformate für jede Meldung wird in Verknüpfungen zu den Klassen beschrieben, die verwendet werden, um die Informationen in der Beschreibung des Protokolls zu serialisieren/deserialisieren.

#### <a name="test-execution"></a>Testausführung
![Testausführung](./media/test-protocol/dotnet-test-execute.png)

1. Nach der optionalen Versionskontrolle sendet der Adapter eine TestExecution.GetTestRunnerProcessStartInfo zusammen mit dem [Test](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs), der darin ausgeführt werden soll. Dotnet test sendet einen Dateinamen sowie Argumente innerhalb einer [TestStartInfo](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.DotNet.Tools.Test/TestStartInfo.cs)-Nutzlast, die vom Adapter verwendet werden können, um den Runner zu starten. In der Vergangenheit wurde die Liste mit auszuführenden Tests als Teil dieses Arguments versendet, jedoch wurde das Größenlimit der Befehlszeile für einige Testprojekte überschritten.
  1. Als Teil des Arguments senden wir einen Port, mit dem sich der Runner verbinden und Tests ausführen soll und ein -wait-Befehlsflag, das angibt, dass der Runner sich mit dem Port verbinden muss und auf Befehle warten soll, anstatt weiter die Testes auszuführen.
2. Zu diesem Zeitpunkt kann der Adapter den Runner starten (und ihn für das Debuggen anhängen, falls gewünscht).
3. Nachdem der Runner gestartet wurde, wird an dotnet test eine TestRunner.WaitCommand-Meldung gesendet, die angibt, dass nun Befehle empfangen werden können. Dotnet test sendet daraufhin einen TestRunner.Execute-Befehl, zusammen mit einer Liste mit auszuführenden [Tests](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs). Damit wird das oben beschriebene Größenlimit für die Befehlszeile umgangen.
4. Der Runner sendet dann an dotnet test (was an den Adapter übergeben wird) für jeden Test TestExecution.TestStarted , da jeder Test mit der [Test](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Test.cs)-Information gestartet wird.
5. Der Runner sendet dotnet test außerdem ein TestExecution.TestResult für jeden Test mit dem [individuellen Ergebnis](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/TestResult.cs) des Test (und dieser leitet es an den Adapter weiter).
6. Nach dem alle Tests abgeschlossen sind, sendet der Runner eine TestRunner.Completed-Meldung an dotnet test, die dotnet test wiederum als TestExecution.Completed an den Adapter sendet.
7. Nachdem der Adapter fertig ist, sendet er TestSession.Terminate an dotnet test, wodurch dotnet test heruntergefahren wird.

#### <a name="test-discovery"></a>Testermittlung
![Testermittlung](./media/test-protocol/dotnet-test-discover.png)

1. Nach der optionalen Versionsüberprüfung sendet der Adapter eine TestDiscovery.Start-Meldung. Da der Adapter in diesem Fall nicht an den Prozess angefügt werden muss, startet dotnet test den Runner selbst. Da zudem keine lange Liste von Argumenten an den Runner übergeben werden muss, muss kein wait-Befehlsflag an den Runner übergeben werden. Dotnet test übergibt nur ein Listenargument an den Runner, d.h. der Runner sollte die Tests nicht ausführen, sondern nur auflisten.
2. Der Runner sendet dann TestDiscovery.TestFound für jeden gefundenen [Test](https://github.com/dotnet/cli/blob/rel/1.0.0/src/Microsoft.Extensions.Testing.Abstractions/Test.cs) an dotnet test (und dieser leitet es an den Adapter weiter).
3. Nach dem alle Tests ermittelt sind, sendet der Runner eine TestRunner.Completed-Meldung an dotnet test, die dotnet test wiederum als TestDiscovery.Completed an den Adapter sendet.
4. Nachdem der Adapter fertig ist, sendet er TestSession.Terminate an dotnet test, wodurch dotnet test heruntergefahren wird.


<!--HONumber=Nov16_HO1-->


