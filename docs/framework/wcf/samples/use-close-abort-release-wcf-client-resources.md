---
title: Freigeben von WCF-Clientressourcen mit „Close“ und „Abort“
description: Der Löschvorgang kann fehlschlagen und Ausnahmen auslösen, wenn das Netzwerk ausfällt. Dies kann zu unerwünschtem Verhalten führen. Verwenden Sie stattdessen schließen und Abbrechen, um Client Ressourcen freizugeben, wenn das Netzwerk nicht ausgeführt werden konnte.
ms.date: 11/12/2018
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
ms.openlocfilehash: b338b760f461d7b773f43dd1f5e6dbce98f9e15a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599918"
---
# <a name="close-and-abort-release-resources-safely-when-network-connections-have-dropped"></a>Releaseressourcen beim Ablegen von Netzwerkverbindungen sicher schließen und Abbrechen

Dieses Beispiel veranschaulicht die Verwendung der `Close` -Methode und der- `Abort` Methode zum Bereinigen von Ressourcen bei Verwendung eines typisierten Clients. Die- `using` Anweisung verursacht Ausnahmen, wenn die Netzwerkverbindung nicht stabil ist. Dieses Beispiel basiert auf den ersten [Schritten, mit](getting-started-sample.md) denen ein Rechner Dienst implementiert wird. In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

In diesem Beispiel werden zwei häufige Probleme veranschaulicht, die beim Verwenden der C#-Anweisung "using" mit typisierten Clients auftreten. Außerdem wird Code bereitgestellt, mit dem die Bereinigung nach Ausnahmen korrekt ausgeführt werden kann.

Die C#-Anweisung "using" führt zu einem Aufruf von `Dispose`(). Dies ist das Gleiche wie `Close`(). Dies kann zu Ausnahmen führen, wenn ein Netzwerkfehler auftritt. Da der Aufruf von `Dispose`() implizit an der schließenden Klammer des "using"-Blocks erfolgt, wird diese Quelle für Ausnahmen beim Schreiben oder Lesen des Codes häufig nicht bemerkt. Dies stellt eine potenzielle Quelle für Anwendungsfehler dar.

Das erste Problem (in der `DemonstrateProblemUsingCanThrow`-Methode dargestellt) liegt darin, dass die schließende Klammer eine Ausnahme auslöst und der Code nach der schließenden Klammer nicht ausgeführt wird:

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
} // <-- this line might throw
Console.WriteLine("Hope this code wasn't important, because it might not happen.");
```

Selbst wenn nichts im using-Block eine Ausnahme auslöst oder alle Ausnahmen im using-Block abgefangen werden, wird `Console.WriteLine` möglicherweise nicht ausgeführt, da der implizite `Dispose`()-Aufruf an der schließenden Klammer eine Ausnahme auslösen kann.

Das zweite Problem (in der `DemonstrateProblemUsingCanThrowAndMask`-Methode veranschaulicht) ist eine weitere Implikation der schließenden Klammer, die eine Ausnahme auslöst:

```csharp
using (CalculatorClient client = new CalculatorClient())
{
    ...
    throw new ApplicationException("Hope this exception was not important, because "+
                                   "it might be masked by the Close exception.");
} // <-- this line might throw an exception.
```

Da `Dispose`() in einem "finally"-Block auftritt, tritt `ApplicationException` nur außerhalb des using-Blocks auf, wenn bei `Dispose`() ein Fehler auftritt. Wenn der Code außen wissen muss, wann die `ApplicationException` auftritt, kann das "using"-Konstrukt zu Problemen führen, da diese Ausnahme maskiert wird.

Abschließend wird im Beispiel veranschaulicht, wie die Bereinigung ordnungsgemäß ausgeführt wird, nachdem Ausnahmen in `DemonstrateCleanupWithExceptions` aufgetreten sind. Dabei wird ein try/catch-Block verwendet, um Fehler zu melden und `Abort` aufzurufen. Weitere Informationen zum Abfangen von Ausnahmen von Client aufrufen finden Sie im Beispiel [erwartete Ausnahmen](expected-exceptions.md) .

```csharp
try
{
    ...
    client.Close();
}
catch (CommunicationException e)
{
    ...
    client.Abort();
}
catch (TimeoutException e)
{
    ...
    client.Abort();
}
catch (Exception e)
{
    ...
    client.Abort();
    throw;
}
```

> [!NOTE]
> Die using-Anweisung und ServiceHost: Viele selbst gehostete Anwendungen führen wenige andere Aktionen als das Hosten eines Diensts aus, und ServiceHost.Close löst selten Ausnahmen aus. In solchen Anwendungen kann die using-Anweisung mit ServiceHost daher sicher verwendet werden. Achten Sie jedoch darauf, dass ServiceHost.Close eine `CommunicationException` auslösen kann. Wenn die Anwendung daher nach dem Schließen von ServiceHost fortgesetzt wird, sollten Sie die Verwendung der using-Anweisung vermeiden und sich an das zuvor beschriebene Muster halten.

Wenn Sie das Beispiel ausführen, werden die Antworten und Ausnahmen für den Vorgang im Konsolenfenster des Clients angezeigt.

Im Clientprozess werden drei Szenarios ausgeführt, die jeweils versuchen, `Divide` aufzurufen. Im ersten Szenario wird veranschaulicht, dass Code aufgrund einer Ausnahme von `Dispose`() übersprungen wird. Im zweiten Szenario wird veranschaulicht, dass eine wichtige Ausnahme aufgrund einer Ausnahme von `Dispose`() maskiert wird. Das dritte Szenario zeigt die ordnungsgemäße Bereinigung.

Die erwartete Ausgabe vom Clientprozess lautet wie folgt:

```console
=
= Demonstrating problem:  closing brace of using statement can throw.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.
=
Got System.ServiceModel.CommunicationException from Divide.
Got System.ServiceModel.Security.MessageSecurityException
=
= Demonstrating cleanup with Exceptions.
=
Calling client.Add(0.0, 0.0);
        client.Add(0.0, 0.0); returned 0
Calling client.Divide(0.0, 0.0);
Got System.ServiceModel.CommunicationException from Divide.

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.

3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`
