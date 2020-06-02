---
title: 'Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation Diensts'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 872844487578843492e05dd2abb87b50e0bec91c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291395"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation Diensts

In diesem Tutorial wird die dritte von fünf Aufgaben beschrieben, die zum Erstellen einer Basic Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Einstieg in Windows Communication Foundation Anwendungen](getting-started-tutorial.md).

Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht darin, einen WCF-Dienst in einer Konsolenanwendung zu hosten. Ein WCF-Dienst macht einen oder mehrere *Endpunkte*verfügbar, von denen jeder einen oder mehrere Dienst Vorgänge verfügbar macht. Ein Dienst Endpunkt gibt die folgenden Informationen an:

- Eine Adresse, an der Sie den Dienst finden können.
- Eine Bindung, die die Informationen enthält, die beschreiben, wie ein Client mit dem Dienst kommunizieren muss.
- Ein Vertrag, der die Funktionalität definiert, die der Dienst für seine Clients bereitstellt.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Erstellen und konfigurieren Sie ein Konsolen-App-Projekt zum Hosting eines WCF-Diensts.
> - Hinzufügen von Code zum Hosten des WCF-Diensts
> - Aktualisieren Sie die Konfigurationsdatei.
> - Starten Sie den WCF-Dienst, und prüfen Sie, ob er ausgeführt wird

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Erstellen und Konfigurieren eines Konsolen-App-Projekts zum Hosting des Diensts

1. Erstellen eines Konsolen-App-Projekts in Visual Studio:

    1. Wählen Sie im Menü **Datei** die **Open**Option  >  **Projekt/Projekt** Mappe öffnen aus, und navigieren Sie zur zuvor erstellten Lösung **GettingStarted** (*GettingStarted. sln*). Wähle **Öffnen** aus.

    2. Wählen Sie im Menü **Ansicht** die Option **Projektmappen-Explorer**aus.

    3. Wählen Sie im Fenster **Projektmappen-Explorer** die Lösung **GettingStarted** (oberer Knoten) aus, und klicken Sie dann im Kontextmenü auf **Add**  >  **Neues Projekt** hinzufügen.

    4. Wählen Sie im Fenster **Neues Projekt hinzufügen** auf der linken Seite unter **Visual c#** die Kategorie **Windows-Desktop** aus, oder **Visual Basic**.

    5. Wählen Sie die Vorlage **Konsolen-app (.NET Framework)** aus, und geben Sie als **Name den Namen** *gettingstartedhost* ein. Klicken Sie auf **OK**.

2. Fügen Sie dem **gettingstartedlib** -Projekt einen Verweis im **gettingstartedhost** -Projekt hinzu:

    1. Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **Verweise** unter dem **gettingstartedhost** -Projekt aus, und klicken Sie dann im Kontextmenü auf **Verweis hinzufügen** .

    2. **Wählen Sie**im Dialogfeld **Verweis hinzufügen** unter Projekte auf der linken Seite des Fensters **Projekt** Mappe aus.

    3. Wählen Sie im mittleren Bereich des Fensters **gettingstartedlib** aus, und klicken Sie dann auf **OK**.

       Durch diese Aktion werden die Typen, die im **gettingstartedlib** -Projekt definiert sind, für das **gettingstartedhost** -Projekt verfügbar.

3. Fügen Sie der Assembly einen Verweis im **gettingstartedhost** -Projekt hinzu <xref:System.ServiceModel> :

    1. Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **Verweise** unter dem **gettingstartedhost** -Projekt aus, und klicken Sie dann im Kontextmenü auf **Verweis hinzufügen** .

    2. Wählen Sie im Fenster **Verweis hinzufügen** unter Assemblys auf der linken Seite des Fensters **Framework** **aus.**

    3. Wählen Sie **System. Service Model**aus, und klicken Sie dann auf **OK**.

    4. Speichern Sie die Projekt Mappe, indem Sie **Datei**  >  **Alle speichern**auswählen.

## <a name="add-code-to-host-the-service"></a>Hinzufügen von Code zum Hosten des Diensts

Um den Dienst zu hosten, fügen Sie Code hinzu, um die folgenden Schritte auszuführen:

1. Erstellen Sie einen URI für die Basisadresse.
2. Erstellen Sie eine Klasseninstanz für das Hosting des Diensts.
3. Erstellen Sie einen Dienst Endpunkt.
4. Aktivieren des Metadatenaustauschs
5. Öffnen Sie den Dienst Host, um auf eingehende Nachrichten zu lauschen.
  
Nehmen Sie die folgenden Änderungen am Code vor:

1. Öffnen Sie die Datei **Program.cs** oder **Module1. vb** im **gettingstartedhost** -Projekt, und ersetzen Sie den Code durch den folgenden Code:

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb);

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```

    Informationen dazu, wie dieser Code funktioniert, finden Sie unter [Service Hosting Program Steps](#service-hosting-program-steps).

2. Aktualisieren Sie die Projekteigenschaften:

   1. Wählen Sie im Fenster **Projektmappen-Explorer** den Ordner **gettingstartedhost** aus, und klicken Sie dann im Kontextmenü auf **Eigenschaften** .

   2. Wählen Sie auf der Eigenschaften Seite von **gettingstartedhost** die Registerkarte **Anwendung** aus:

      - Wählen Sie für c#-Projekte in der Liste **Start Objekt** den Befehl **gettingstartedhost. Program** aus.

      - Wählen Sie für Visual Basic Projekte in der Liste **Start Objekt** den Typ **Service. Program** aus.

   3. Wählen Sie im Menü **Datei** die Option **Alle speichern**aus.

## <a name="verify-the-service-is-working"></a>Überprüfen, ob der Dienst funktioniert

1. Erstellen Sie die Projekt Mappe, und führen Sie dann die **gettingstartedhost** -Konsolenanwendung in Visual Studio aus.

    Der Dienst muss mit Administratorrechten ausgeführt werden. Da Sie Visual Studio mit Administratorrechten geöffnet haben, wird die Anwendung beim Ausführen von **gettingstartedhost** in Visual Studio ebenfalls mit Administratorrechten ausgeführt. Als Alternative können Sie eine neue Eingabeaufforderung als Administrator öffnen (Klicken Sie im Kontextmenü auf " **mehr**  >  **als Administrator ausführen** ") und " **gettingstartedhost. exe** " ausführen.

2. Öffnen Sie einen Webbrowser, und navigieren Sie zur Seite des Diensts unter `http://localhost:8000/GettingStarted/CalculatorService` .

   > [!NOTE]
   > Dienste wie diese benötigen die richtige Berechtigung zum Registrieren von HTTP-Adressen auf dem Computer für die Überwachung. Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden. Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](feature-details/configuring-http-and-https.md).

## <a name="service-hosting-program-steps"></a>Schritte zum Dienst Hostingprogramm

Die Schritte im Code, den Sie zum Hosten des Diensts hinzugefügt haben, werden wie folgt beschrieben:

- **Schritt 1**: Erstellen Sie eine Instanz der- `Uri` Klasse, die die Basisadresse des dienstanweises enthält. Eine URL, die eine Basisadresse enthält, verfügt über einen optionalen URI, der einen Dienst identifiziert. Die Basisadresse wird wie folgt formatiert: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>` . Die Basisadresse für den Rechner Dienst verwendet den HTTP-Transport, localhost, Port 8000 und das URI-Segment "GettingStarted".

- **Schritt 2**: Erstellen Sie eine Instanz der- <xref:System.ServiceModel.ServiceHost> Klasse, die Sie zum Hosten des Diensts verwenden. Der Konstruktor benötigt zwei Parameter: den Typ der Klasse, die den Dienstvertrag implementiert, und die Basisadresse des Dienstanbieter.

- **Schritt 3**: Erstellen Sie eine- <xref:System.ServiceModel.Description.ServiceEndpoint> Instanz. Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen. Der <xref:System.ServiceModel.Description.ServiceEndpoint> Konstruktor besteht aus dem Dienstvertragstyp, einer Bindung und einer Adresse. Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren. Die Bindung für dieses Beispiel ist, bei der es sich um <xref:System.ServiceModel.WSHttpBinding> eine integrierte Bindung handelt und eine Verbindung mit Endpunkten herstellt, die den WS-*-Spezifikationen entsprechen. Weitere Informationen zu WCF-Bindungen finden Sie unter [Übersicht über WCF-Bindungen](bindings-overview.md). Sie fügen die Adresse an die Basisadresse an, um den Endpunkt zu identifizieren. Der Code gibt die Adresse als CalculatorService und die voll qualifizierte Adresse für den Endpunkt als an `http://localhost:8000/GettingStarted/CalculatorService` .

    > [!IMPORTANT]
    > Für .NET Framework Version 4 und höher ist das Hinzufügen eines Dienst Endpunkts optional. Wenn Sie den Code oder die Konfiguration nicht hinzufügen, fügt WCF für diese Versionen einen Standard Endpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wird. Weitere Informationen zu Standard Endpunkten finden Sie unter [Angeben einer Endpunkt Adresse](specifying-an-endpoint-address.md). Weitere Informationen zu Standard Endpunkten, Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](samples/simplified-configuration-for-wcf-services.md).

- **Schritt 4**: Aktivieren Sie den Metadatenaustausch. Clients verwenden den Metadatenaustausch zum Generieren von Proxys zum Aufrufen der Dienst Vorgänge. Um den Metadatenaustausch zu aktivieren, erstellen Sie eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior> -Instanz, legen Sie Ihre <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> -Eigenschaft auf fest `true` , und fügen Sie das-Objekt der-Auflistung `ServiceMetadataBehavior` der- <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> <xref:System.ServiceModel.ServiceHost> Instanz

- **Schritt 5**: Öffnen <xref:System.ServiceModel.ServiceHost> Sie, um auf eingehende Nachrichten zu lauschen. Die Anwendung wartet darauf, dass Sie die **Eingabe**Taste drücken. Nachdem die Anwendung instanziiert <xref:System.ServiceModel.ServiceHost> wurde, wird ein try/catch-Block ausgeführt. Weitere Informationen zum sicheren Abfangen von Ausnahmen <xref:System.ServiceModel.ServiceHost> , die von ausgelöst werden, finden [Sie unter Verwenden von schließen und Abbrechen zum Freigeben von WCF-Client Ressourcen](samples/use-close-abort-release-wcf-client-resources.md).

> [!IMPORTANT]
> Wenn Sie eine WCF-Dienst Bibliothek hinzufügen, wird Sie von Visual Studio für Sie gehostet, wenn Sie Sie durchstarten eines Dienst Hosts Debuggen. Um Konflikte zu vermeiden, können Sie verhindern, dass Visual Studio die WCF-Dienst Bibliothek gehostet.
>
> 1. Wählen Sie das **gettingstartedlib** -Projekt in **Projektmappen-Explorer** aus, und wählen Sie im Kontextmenü **Eigenschaften** aus.
> 2. Wählen Sie **WCF-Optionen** aus, und deaktivieren Sie **beim Debuggen eines anderen Projekts in derselben Projekt Mappe den WCF-Dienst Host starten**

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> - Erstellen und konfigurieren Sie ein Konsolen-App-Projekt zum Hosting eines WCF-Diensts.
> - Hinzufügen von Code zum Hosten des WCF-Diensts
> - Aktualisieren Sie die Konfigurationsdatei.
> - Starten Sie den WCF-Dienst, und prüfen Sie, ob er ausgeführt wird

Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie einen WCF-Client erstellen.

> [!div class="nextstepaction"]
> [Tutorial: Erstellen eines WCF-Clients](how-to-create-a-wcf-client.md)
