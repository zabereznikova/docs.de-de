---
title: 'Gewusst wie: Asynchrones Aufrufen eines Webdiensts'
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: d288cc1f2991a8f504dc9f1b206bba76fa378b75
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "76794565"
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a>Gewusst wie: Asynchrones Aufrufen eines Webdiensts (Visual Basic)

Dieses Beispiel hängt einen Handler an das asynchrone Handlerereignis eines Webdiensts an, sodass dieses das Ergebnis eines asynchronen Methodenaufrufs abrufen kann. Dieses Beispiel verwendet den Webdienst DemoTemperatureService unter `http://www.xmethods.net`.

Wenn Sie im Projekt in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) von Visual Studio auf einen Webdienst verweisen, wird dieser dem `My.WebServices`-Objekt hinzugefügt und die IDE generiert eine Client-Proxyklasse für den Zugriff auf einen festgelegten Webdienst.

Mit der Proxyklasse ist es möglich, die Webdienstmethoden synchron aufzurufen, während die Anwendung darauf wartet, dass die Funktion abgeschlossen wird. Außerdem erstellt das Proxy weitere Member zur asynchronen Unterstütztung der Methode. Für jede Webdienstfunktion, *NameOfWebServiceFunction*, erstellt das Proxy eine *NameOfWebServiceFunction*`Async`-Unterroutine, ein *NameOfWebServiceFunction*`Completed`-Ereignis und eine *NameOfWebServiceFunction*`CompletedEventArgs`-Klasse. Dieses Beispiel demonstriert, wie Sie die asynchronen Member für den Zugriff auf die `getTemp`-Funktion des Webdiensts DemoTemperatureService verwenden.

> [!NOTE]
> Dieser Code funktioniert nicht in Webanwendungen, denn ASP.NET unterstützt nicht das Objekt `My.WebServices`.

## <a name="call-a-web-service-asynchronously"></a>Asynchrones Aufrufen eines Webdiensts

1. Referenzieren Sie den Webdienst DemoTemperatureService unter `http://www.xmethods.net`. Die Adresse lautet

    ```http
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl
    ```

2. Fügen Sie einen Ereignishandler für das `getTempCompleted`-Ereignis hinzu:

    ```vb
    Private Sub getTempCompletedHandler(ByVal sender As Object,
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)

        MsgBox("Temperature: " & e.Result)
    End Sub
    ```

    > [!NOTE]
    > Die Anweisung `Handles` lässt sich nicht für das Zuordnen eines Ereignishandlers zu den Ereignissen des `My.WebServices`-Objekts verwenden.

3. Fügen Sie ein Feld hinzu um nachverfolgen zu können, ob der Ereignishandler dem `getTempCompleted`-Ereignis hinzugefügt wurde:

    ```vb
    Private handlerAttached As Boolean = False
    ```

4. Fügen Sie eine Methode hinzu, um den Ereignishandler zum `getTempCompleted`-Ereignis hinzufügen – sofern nötig – und zum Aufruf der `getTempAsync`-Methode:

    ```vb
    Sub CallGetTempAsync(ByVal zipCode As Integer)
        If Not handlerAttached Then
            AddHandler My.WebServices.
                TemperatureService.getTempCompleted,
                AddressOf Me.TS_getTempCompleted
            handlerAttached = True
        End If
        My.WebServices.TemperatureService.getTempAsync(zipCode)
    End Sub
    ```

    Für einen asynchronen Aufruf der `getTemp`-Webmethode rufen Sie die `CallGetTempAsync`-Methode auf. Wenn die Webmethode fertig ist, wird ihr Rückgabewert an den `getTempCompletedHandler`-Ereignishandler übergeben.

## <a name="see-also"></a>Weitere Informationen

- [Zugreifen auf Anwendungswebdienste](accessing-application-web-services.md)
- [My.WebServices-Objekt](../../language-reference/objects/my-webservices-object.md)
