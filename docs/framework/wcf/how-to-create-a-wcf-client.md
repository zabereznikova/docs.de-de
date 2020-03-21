---
title: 'Tutorial: Erstellen eines Windows Communication Foundation-Clients'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184102"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Tutorial: Erstellen eines Windows Communication Foundation-Clients

In diesem Tutorial wird die vierte von fünf Aufgaben beschrieben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht darin, einen Client zu erstellen, indem Metadaten von einem WCF-Dienst abgerufen werden. Sie verwenden Visual Studio, um einen Dienstverweis hinzuzufügen, der die Metadaten vom MEX-Endpunkt des Diensts abruft. Visual Studio generiert dann eine verwaltete Quellcodedatei für einen Clientproxy in der von Ihnen gewählten Sprache. Außerdem wird eine Clientkonfigurationsdatei (*App.config*) erstellt. Diese Datei ermöglicht es der Clientanwendung, eine Verbindung mit dem Dienst an einem Endpunkt herzustellen.

> [!NOTE]
> Wenn Sie einen WCF-Dienst aus einem Klassenbibliotheksprojekt in Visual Studio aufrufen, verwenden Sie die Funktion **Dienstreferenz hinzufügen,** um automatisch einen Proxy und eine zugehörige Konfigurationsdatei zu generieren. Da Klassenbibliotheksprojekte diese Konfigurationsdatei jedoch nicht verwenden, müssen Sie die Einstellungen in der generierten Konfigurationsdatei der *Datei App.config* für die ausführbare Datei hinzufügen, die die Klassenbibliothek aufruft.

> [!NOTE]
> Alternativ können Sie das [ServiceModel-Metadaten-Dienstprogramm](#servicemodel-metadata-utility-tool) anstelle von Visual Studio verwenden, um die Proxyklasse und Konfigurationsdatei zu generieren.

Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren. Dieses Verfahren wird in [Tutorial beschrieben: Verwenden eines Clients](how-to-use-a-wcf-client.md).

In diesem Tutorial lernen Sie Folgendes:
> [!div class="checklist"]
>
> - Erstellen und konfigurieren Sie ein Konsolen-App-Projekt für den WCF-Client.
> - Fügen Sie dem WCF-Dienst einen Dienstverweis hinzu, um die Proxyklasse und die Konfigurationsdateien zu generieren.

## <a name="create-a-windows-communication-foundation-client"></a>Erstellen eines Windows Communication Foundation-Clients

1. Erstellen eines Konsolen-App-Projekts in Visual Studio:

    1. Wählen Sie im Menü **Datei** die Option**Projekt/Projektmappe** **öffnen** > aus, und navigieren Sie zur **Lösung "Erste Schritte",** die Sie zuvor erstellt haben (*GettingStarted.sln*). Wählen Sie **Öffnen** aus.

    2. Wählen Sie im Menü **Ansicht** **den Projektmappen-Explorer**aus.

    3. Wählen Sie im **Projektmappen-Explorer** die **Lösung "Erste Schritte"** (oberster Knoten) und dann im Kontextmenü **"Neues Projekt hinzufügen"** **aus.** > 

    4. Wählen Sie im Fenster **Neues Projekt hinzufügen** auf der linken Seite die Windows **Desktop-Kategorie** unter Visual **C oder** Visual **Basic**aus.

    5. Wählen Sie die Vorlage **"Konsolen-App" (.NET Framework)** aus, und geben Sie *GettingStartedClient* für den **Namen ein.** Wählen Sie **OK** aus.

2. Fügen Sie der <xref:System.ServiceModel> Assembly einen Verweis im **GettingStartedClient-Projekt** hinzu:

    1. Wählen Sie im **Projektmappen-Explorer** den Ordner **Referenzen** unter dem **GettingStartedClient-Projekt** aus, und wählen Sie dann im Kontextmenü **Referenz hinzufügen** aus.

    2. Wählen Sie im Fenster **Referenz hinzufügen** unter **Baugruppen** auf der linken Seite des Fensters **Framework**aus.

    3. Suchen und wählen Sie **System.ServiceModel**aus, und wählen Sie dann **OK**aus.

    4. Speichern Sie die Lösung, indem Sie **Datei** > **speichern alle**auswählen.

3. Hinzufügen einer Dienstreferenz zum Rechnerdienst:

   1. Wählen Sie im **Projektmappen-Explorer** den Ordner **Referenzen** unter dem **GettingStartedClient-Projekt** aus, und wählen Sie dann im Kontextmenü **Dienstreferenz hinzufügen** aus.

   2. Wählen Sie im Fenster **Dienstreferenz hinzufügen** die Option **Ermitteln**aus.

      Der CalculatorService-Dienst wird gestartet, und Visual Studio zeigt ihn im Feld **Dienste** an.

   3. Wählen Sie **CalculatorService** aus, um ihn zu erweitern und die vom Dienst implementierten Serviceverträge anzuzeigen. Verlassen Sie den **Standardnamespace** und wählen Sie **OK**.

      Visual Studio fügt im **GettingStartedClient-Projekt** ein neues Element unter dem Ordner **Verbundene Dienste** hinzu.

### <a name="servicemodel-metadata-utility-tool"></a>ServiceModel Metadata Utility-Tool

Die folgenden Beispiele zeigen, wie Sie optional das [ServiceModel Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden, um die Proxyklassendatei zu generieren. Dieses Tool generiert die Proxyklassendatei und die *Datei App.config.* Die folgenden Beispiele zeigen, wie Sie den Proxy in C- bzw. Visual Basic generieren:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>Clientkonfigurationsdatei

Nachdem Sie den Client erstellt haben, erstellt Visual Studio die **App.config-Konfigurationsdatei** im **GettingStartedClient-Projekt,** die dem folgenden Beispiel ähnlich sein sollte:

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

Beachten Sie im [ \<Abschnitt system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) den [ \<Endpunkt>-Element.](../configure-apps/file-schema/wcf/endpoint-element.md) Das ** &lt;Endpunktelement&gt; ** definiert den Endpunkt, den der Client für den Zugriff auf den Dienst verwendet, wie folgt:

- Adresse: `http://localhost:8000/GettingStarted/CalculatorService`. Die Adresse des Endpunkts.
- Servicevertrag: `ServiceReference1.ICalculator`. Der Servicevertrag verarbeitet die Kommunikation zwischen dem WCF-Client und dem Dienst. Visual Studio hat diesen Vertrag generiert, als Sie die Funktion **Dienstreferenz hinzufügen** verwendet haben. Es handelt sich im Wesentlichen um eine Kopie des Vertrags, den Sie im GettingStartedLib-Projekt definiert haben.
- Bindung: <xref:System.ServiceModel.WSHttpBinding>. Die Bindung gibt HTTP als Transport, interoperable Sicherheit und andere Konfigurationsdetails an.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Folgendes gelernt:
> [!div class="checklist"]
>
> - Erstellen und konfigurieren Sie ein Konsolen-App-Projekt für den WCF-Client.
> - Fügen Sie dem WCF-Dienst einen Dienstverweis hinzu, um die Proxyklasse und die Konfigurationsdateien für die Clientanwendung zu generieren.

Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie den generierten Client verwenden.

> [!div class="nextstepaction"]
> [Tutorial: Verwenden eines WCF-Clients](how-to-use-a-wcf-client.md)
