---
title: Hello World mit dem Routingdienst
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 3d91634d72481427f04e958f6dc2734829b6158b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253855"
---
# <a name="hello-world-with-the-routing-service"></a>Hello World mit dem Routingdienst

In diesem Beispiel wird der Windows Communication Foundation (WCF)-Routing Dienst veranschaulicht. Der Routing Dienst ist eine WCF-Komponente, mit der Sie ganz einfach einen Inhalts basierten Router in Ihre Anwendung integrieren können. In diesem Beispiel wird das standardmäßige WCF-Rechner Beispiel für die Kommunikation über den Routing Dienst angepasst. In diesem Beispiel ist der Rechnerclient so konfiguriert, dass er Nachrichten an einen vom Router verfügbar gemachten Endpunkt sendet. Der Routingdienst ist so konfiguriert, dass er alle gesendeten Nachrichten akzeptiert und diese an einen Endpunkt weiterleitet, der dem Rechnerdienst entspricht. Somit werden vom Client gesendete Nachrichten vom Router empfangen und zum eigentlichen Rechnerdienst umgeleitet. Nachrichten vom Rechnerdienst werden an den Router zurückgesendet, der sie dann zurück an den Rechnerclient übergibt.

### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. Öffnen Sie mit Visual Studio 2012 die Datei "helloroutingservice. sln".

2. Drücken Sie F5 oder STRG+UMSCHALT+B.

    > [!NOTE]
    > Wenn Sie F5 drücken, wird der Rechnerclient automatisch gestartet. Wenn Sie STRG+UMSCHALT+B (Erstellen) drücken, müssen Sie die folgenden Anwendungen selbst starten.
    >
    > 1. Rechnerclient (./CalculatorClient/bin/client.exe)
    > 2. Rechnerdienst (./CalculatorService/bin/service.exe)
    > 3. Routingdienst (./RoutingService/bin/RoutingService.exe)

3. Drücken Sie die EINGABETASTE, um den Client zu starten.

     Die folgende Ausgabe wird angezeigt:

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a>Konfigurierbar über Code oder App.Config

 Das Beispiel wird so konfiguriert geliefert, dass die Datei App.config das Verhalten des Routers definiert. Sie können außerdem den Namen der Datei App.config ändern, damit er nicht erkannt wird, und die Auskommentierung des Methodenaufrufs von ConfigureRouterViaCode() aufheben. Beide Methoden führen zum gleichen Routerverhalten.

### <a name="scenario"></a>Szenario

 In diesem Beispiel wird der Router in der Funktion als einfaches Nachrichtensystem veranschaulicht. Der Routingdienst funktioniert als transparenter Proxyknoten, der so konfiguriert wurde, dass er Nachrichten direkt an einen vorkonfigurierten Satz von Zielendpunkten übergibt.

### <a name="real-world-scenario"></a>Reales Szenario

 Contoso möchte mehr Flexibilität bei der Benennung, Adressierung, Konfiguration und Sicherheit der Dienste. Aus diesem Grund wird ein einfaches Nachrichtensystem vor die Dienste gesetzt, das als öffentlicher Endpunkt fungiert. So können zusätzliche Sicherheitsmaßnahmen vor den eigentlichen Diensten eingefügt werden, und skalierte Lösungen sowie die Dienstversionsverwaltung können später einfacher implementiert werden.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Hosting- und -Persistenzbeispiele](/previous-versions/appfabric/ff383418(v=azure.10))
