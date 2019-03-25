---
title: 'Tutorial: Erstellen eines Windows Communication Foundation-Clients'
ms.dat8: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 051275e56a8e63c6ab8136dbb9e24bdcf4c387df
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411856"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Tutorial: Erstellen eines Windows Communication Foundation-Clients

In diesem Tutorial wird die vierte von fünf Schritte zur Erstellung einer grundlegenden Windows Communication Foundation (WCF)-Anwendung beschrieben. Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht, erstellen Sie einen Client vom Abrufen von Metadaten aus einem WCF-Dienst. Verwenden Sie Visual Studio einen Dienstverweis hinzufügen, der Metadaten vom MEX-Endpunkt des Diensts erhält. Visual Studio generiert dann eine verwaltete Quellcodedatei für einen Clientproxy in der Sprache, die Sie ausgewählt haben. Erstellt auch eine Clientkonfigurationsdatei (*"App.config"*). Diese Datei können die Clientanwendung eine Verbindung mit dem Dienst an einem Endpunkt herstellen. 

> [!NOTE]
> Wenn Sie einen WCF-Dienst aus einem Klassenbibliotheksprojekt in Visual Studio aufrufen, verwenden Sie die **Dienstverweis hinzufügen** Funktion, um automatisch einen Proxy und eine zugeordnete Konfigurationsdatei zu generieren. Aber da Klassenbibliotheksprojekte diese Konfigurationsdatei nicht verwenden, müssen Sie die Einstellungen in der generierten Konfigurationsdatei zum Hinzufügen der *"App.config"* -Datei für die ausführbare Datei, die die Klassenbibliothek aufruft.

> [!NOTE]
> Verwenden Sie alternativ die [ServiceModel Metadata Utility-Tool](#servicemodel-metadata-utility-tool) anstelle von Visual Studio, um den Proxycode und der Konfigurationsdatei zu generieren.

Die Clientanwendung verwendet die generierte Proxyklasse, um mit dem Dienst zu kommunizieren. Dieses Verfahren wird beschrieben, [Lernprogramm: Verwenden Sie einen Client](how-to-use-a-wcf-client.md).

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt für den WCF-Client.
> - Fügen Sie einen Dienstverweis auf den WCF-Dienst, um den Proxy-Klasse und die Konfigurationsdateien zu generieren.


## <a name="create-a-windows-communication-foundation-client"></a>Erstellen eines Windows Communication Foundation-Clients

1. Erstellen Sie ein Konsolenanwendungsprojekt in Visual Studio: 

    1. Von der **Datei** , wählen Sie im Menü **öffnen** > **Projekt/Projektmappe** und navigieren Sie zu der **GettingStarted** Lösung Sie zuvor erstellt haben (*GettingStarted.sln*). Wählen Sie **öffnen**.

    2. Von der **Ansicht** , wählen Sie im Menü **Projektmappen-Explorer**.

    3. In der **Projektmappen-Explorer** wählen Sie im Fenster der **GettingStarted** -Lösung (obersten Knoten), und wählen Sie dann **hinzufügen** > **neues Projekt** aus dem Kontextmenü. 
    
    4. In der **neues Projekt hinzufügen** Fenster auf der linken Seite auf die **Windows Desktop** unter Kategorie **Visual C#**  oder **Visual Basic**. 

    5. Wählen Sie die **Konsolen-App ((.NET Framework)** Vorlage, und geben Sie *"gettingstartedclient"* für die **Namen**. Klicken Sie auf **OK**.

2. Fügen Sie einen Verweis in der **"gettingstartedclient"** Projekt die <xref:System.ServiceModel> Assembly: 

    1.  In der **Projektmappen-Explorer** wählen Sie im Fenster der **Verweise** Ordner unter dem **"gettingstartedclient"** Projekt, und wählen Sie dann **"Verweis hinzufügen"** aus dem Kontextmenü. 

    2. In der **Verweis hinzufügen** Fenster unter **Assemblys** wählen Sie auf der linken Seite des Fensters **Framework**.
    
    3. Suchen und auswählen **System.ServiceModel**, und wählen Sie dann **OK**. 

    4. Speichern Sie die Projektmappe durch Auswahl **Datei** > **Alles speichern**.

3. Fügen Sie einen Dienstverweis auf den rechnerdienst hinzu:

   1. In der **Projektmappen-Explorer** wählen Sie im Fenster der **Verweise** Ordner unter dem **"gettingstartedclient"** Projekt, und wählen Sie dann **Dienstverweis hinzufügen**  aus dem Kontextmenü.

   2. In der **Hinzufügen eines Dienstverweises** wählen Sie im Fenster **Discover**.

      Der CalculatorService-Dienst gestartet wird und die Visual Studio wird in der **Services** Feld.

   3. Wählen Sie **CalculatorService** erweitern und die vom Dienst implementierten Dienstverträge anzuzeigen. Übernehmen Sie den Standardwert **Namespace** , und wählen Sie **OK**.

      Visual Studio fügt ein neues Element mit dem **verbundene Dienste** Ordner in der **"gettingstartedclient"** Projekt. 


### <a name="servicemodel-metadata-utility-tool"></a>ServiceModel Metadata Utility-tool

Die folgenden Beispiele zeigen, wie Sie optional die [ServiceModel Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) die Proxy-Klassendatei zu generieren. Dieses Tool generiert die proxyklassendatei und *"App.config"* Datei. Die folgenden Beispiele zeigen, wie Sie den Proxy in zu generieren C# und Visual Basic bzw.:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>Clientkonfigurationsdatei

Nachdem Sie den Client erstellt haben, erstellt Visual Studio die **"App.config"** Konfigurationsdatei in die **"gettingstartedclient"** -Projekt, das ähnlich wie im folgenden Beispiel werden soll:

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

Unter den [ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) Abschnitt der [ \<Endpunkt >](../configure-apps/file-schema/wcf/endpoint-element.md) Element. Die **&lt;Endpunkt&gt;** -Element definiert den Endpunkt, den der Client verwendet wird, Zugriff auf den Dienst wie folgt:
- Adresse: `http://localhost:8000/GettingStarted/CalculatorService`. Die Adresse des Endpunkts.
- Servicevertrag: `ServiceReference1.ICalculator`. Die Dienstvertrag verarbeitet die Kommunikation zwischen dem WCF-Client und dem Dienst. Visual Studio generiert diesen Vertrag aus, wenn Sie verwendet die **Hinzufügen eines Dienstverweises** Funktion. Es ist im Wesentlichen eine Kopie des Vertrags, die Sie im GettingStartedLib-Projekt definiert. 
- Bindung: <xref:System.ServiceModel.WSHttpBinding>. Die Bindung gibt HTTP als Transport, interoperable Sicherheit und andere Einzelheiten der Konfiguration an.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt für den WCF-Client.
> - Fügen Sie einen Dienstverweis auf den WCF-Dienst, um die Proxy-Klasse und die Konfigurationsdateien für die Clientanwendung zu generieren.

Fahren Sie fort mit dem nächsten Tutorial erfahren, wie den generierten Client verwendet werden soll.

> [!div class="nextstepaction"]
> [Tutorial: Verwenden Sie einen WCF-client](how-to-use-a-wcf-client.md)


