---
title: 'Tutorial: Erstellen eines Windows Communication Foundation Clients'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: ddb5167c7f71a263377fb465ec44ee21057fbf4a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928906"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Tutorial: Erstellen eines Windows Communication Foundation Clients

In diesem Tutorial werden die vier von fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden [Sie unter Tutorial: Beginnen Sie mit Windows Communication Foundation Anwendungen](getting-started-tutorial.md).

Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht darin, einen Client zu erstellen, indem Sie Metadaten von einem WCF-Dienst abrufen. Sie verwenden Visual Studio zum Hinzufügen eines Dienst Verweises, mit dem die Metadaten vom MEX-Endpunkt des dienstanders abgerufen werden. Visual Studio generiert dann eine verwaltete Quell Code Datei für einen Client Proxy in der Sprache, die Sie ausgewählt haben. Außerdem wird eine Client Konfigurationsdatei (*app. config*) erstellt. Diese Datei ermöglicht der Client Anwendung das Herstellen einer Verbindung mit dem Dienst an einem Endpunkt. 

> [!NOTE]
> Wenn Sie einen WCF-Dienst aus einem Klassen Bibliotheksprojekt in Visual Studio aufzurufen, verwenden Sie die **Dienstverweis hinzufügen** Funktion, um automatisch einen Proxy und eine zugehörige Konfigurationsdatei zu generieren. Da in Klassen Bibliotheks Projekten diese Konfigurationsdatei jedoch nicht verwendet wird, müssen Sie die Einstellungen in der generierten Konfigurationsdatei der Datei *app. config* für die ausführbare Datei hinzufügen, die die Klassenbibliothek aufruft.

> [!NOTE]
> Verwenden Sie alternativ das [Service Model Metadata Utility-Tool](#servicemodel-metadata-utility-tool) anstelle von Visual Studio, um die Proxy Klasse und die Konfigurationsdatei zu generieren.

Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren. Dieses Verfahren wird in [Tutorial: Verwenden Sie einen](how-to-use-a-wcf-client.md)-Client.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Erstellen und konfigurieren Sie ein Konsolen-App-Projekt für den WCF-Client.
> - Fügen Sie dem WCF-Dienst einen Dienst Verweis hinzu, um die Proxy Klasse und die Konfigurationsdateien zu generieren.

## <a name="create-a-windows-communication-foundation-client"></a>Erstellen eines Windows Communication Foundation Clients

1. Erstellen eines Konsolen-App-Projekts in Visual Studio: 

    1. Wählen Sie im Menü **Datei** die Option**Projekt/Projekt** Mappe **Öffnen** > aus, und navigieren Sie zur zuvor erstellten Lösung **GettingStarted** (*GettingStarted. sln*). Wählen Sie **Öffnen**aus.

    2. Wählen Sie im Menü **Ansicht** die Option **Projektmappen-Explorer**aus.

    3. Wählen Sie im Fenster **Projektmappen-Explorer** die Lösung **GettingStarted** (oberer Knoten) aus, und klicken Sie dann im Kontextmenü auf**Neues Projekt** **Hinzufügen** > . 
    
    4. Wählen Sie im Fenster **Neues Projekt hinzufügen** auf der linken Seite unter **Visual C#**  oder **Visual Basic**die Kategorie **Windows-Desktop** aus. 

    5. Wählen Sie die Vorlage **Konsolen-app (.NET Framework)** aus, und geben Sie als **Name den Namen** *gettingstartedclient* ein. Klicken Sie auf **OK**.

2. Fügen Sie der <xref:System.ServiceModel> Assembly einen Verweis im **gettingstartedclient** -Projekt hinzu: 

    1. Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **Verweise** unter dem **gettingstartedclient** -Projekt aus, und klicken Sie dann im Kontextmenü auf **Verweis hinzufügen** . 

    2. Wählen Sie im Fenster **Verweis hinzufügen** unter Assemblys auf der linken Seite des Fensters **Framework** **aus.**
    
    3. Suchen und wählen Sie **System. Service Model**aus, und klicken Sie dann auf **OK**. 

    4. Speichern Sie die Projekt Mappe, indem Sie **Datei** > **Alle speichern**auswählen.

3. Fügen Sie dem Rechner Dienst einen Dienst Verweis hinzu:

   1. Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **Verweise** unter dem **gettingstartedclient** -Projekt aus, und klicken Sie dann im Kontextmenü **Dienstverweis hinzufügen** .

   2. Klicken Sie im Fenster **Dienstverweis hinzufügen** auf **ermitteln**.

      Der Dienst "CalculatorService" wird gestartet, und Visual Studio zeigt ihn im Feld " **Dienste** " an.

   3. Wählen Sie **CalculatorService** aus, um ihn zu erweitern und die vom Dienst implementierten Dienstverträge anzuzeigen. Belassen Sie den Standard **Namespace** , und wählen Sie **OK**aus.

      Visual Studio fügt ein neues Element unter dem Ordner " **verbundene Dienste** " im **gettingstartedclient** -Projekt hinzu. 

### <a name="servicemodel-metadata-utility-tool"></a>Service Model Metadata Utility-Tool

In den folgenden Beispielen wird gezeigt, wie Sie optional das [Service Model Metadata Utility-Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden, um die Proxy Klassendatei zu generieren. Mit diesem Tool werden die Proxy Klassendatei und die Datei " *app. config* " generiert. In den folgenden Beispielen wird gezeigt, wie der Proxy C# in bzw. Visual Basic generiert wird:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>Client Konfigurationsdatei

Nachdem Sie den Client erstellt haben, erstellt Visual Studio die Konfigurationsdatei " **app. config** " im **gettingstartedclient** -Projekt, die dem folgenden Beispiel ähnelt:

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

Beachten Sie im Abschnitt [ System.ServiceModel>denEndpunkt>-Elements.\<](../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<](../configure-apps/file-schema/wcf/endpoint-element.md) **Das&lt;Endpunkt&gt;** Element definiert den Endpunkt, den der Client für den Zugriff auf den Dienst verwendet, wie folgt:

- Adresse: `http://localhost:8000/GettingStarted/CalculatorService`. Die Adresse des Endpunkts.
- Dienstvertrag: `ServiceReference1.ICalculator`. Der Dienstvertrag verarbeitet die Kommunikation zwischen dem WCF-Client und dem-Dienst. Visual Studio hat diesen Vertrag generiert, als Sie seine **Dienstverweis hinzufügen** -Funktion verwendet haben. Es handelt sich im Wesentlichen um eine Kopie des Vertrags, den Sie im gettingstartedlib-Projekt definiert haben. 
- Bindung: <xref:System.ServiceModel.WSHttpBinding>. Die Bindung gibt HTTP als Transport, interoperable Sicherheit und andere Konfigurationsdetails an.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Erstellen und konfigurieren Sie ein Konsolen-App-Projekt für den WCF-Client.
> - Fügen Sie dem WCF-Dienst einen Dienst Verweis hinzu, um die Proxy Klasse und die Konfigurationsdateien für die Client Anwendung zu generieren.

Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den generierten Client verwenden.

> [!div class="nextstepaction"]
> [Tutorial: Verwenden eines WCF-Clients](how-to-use-a-wcf-client.md)
