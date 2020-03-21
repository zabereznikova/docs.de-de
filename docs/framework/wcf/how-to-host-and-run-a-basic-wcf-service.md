---
title: 'Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Dienstes'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184085"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Dienstes

In diesem Tutorial wird die dritte von fünf Aufgaben beschrieben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über die Tutorials finden Sie unter [Tutorial: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Die nächste Aufgabe zum Erstellen einer WCF-Anwendung besteht darin, einen WCF-Dienst in einer Konsolenanwendung zu hosten. Ein WCF-Dienst macht einen oder mehrere *Endpunkte*verfügbar, von denen jeder einen oder mehrere Dienstvorgänge verfügbar macht. Ein Dienstendpunkt gibt die folgenden Informationen an:

- Eine Adresse, an der Sie den Dienst finden können.
- Eine Bindung, die die Informationen enthält, die beschreiben, wie ein Client mit dem Dienst kommunizieren muss.
- Ein Vertrag, der die Funktionalität definiert, die der Dienst seinen Clients bereitstellt.

In diesem Tutorial lernen Sie Folgendes:
> [!div class="checklist"]
>
> - Erstellen und konfigurieren Sie ein Konsolen-App-Projekt zum Hosten eines WCF-Dienstes.
> - Fügen Sie Code zum Hosten des WCF-Dienstes hinzu.
> - Aktualisieren Sie die Konfigurationsdatei.
> - Starten Sie den WCF-Dienst, und überprüfen Sie, ob er ausgeführt wird.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Erstellen und Konfigurieren eines Konsolen-App-Projekts zum Hosten des Dienstes

1. Erstellen eines Konsolen-App-Projekts in Visual Studio:

    1. Wählen Sie im Menü **Datei** die Option**Projekt/Projektmappe** **öffnen** > aus, und navigieren Sie zur **Lösung "Erste Schritte",** die Sie zuvor erstellt haben (*GettingStarted.sln*). Wählen Sie **Öffnen** aus.

    2. Wählen Sie im Menü **Ansicht** **den Projektmappen-Explorer**aus.

    3. Wählen Sie im **Projektmappen-Explorer** die **Lösung "Erste Schritte"** (oberster Knoten) und dann im Kontextmenü **"Neues Projekt hinzufügen"** **aus.** > 

    4. Wählen Sie im Fenster **Neues Projekt hinzufügen** auf der linken Seite die Windows **Desktop-Kategorie** unter Visual **C oder** Visual **Basic**aus.

    5. Wählen Sie die Vorlage **"Konsolen-App" (.NET Framework)** aus, und geben Sie *GettingStartedHost* für den **Namen**ein. Wählen Sie **OK** aus.

2. Fügen Sie dem **GettingStartedLib-Projekt** einen Verweis im **GettingStartedHost-Projekt** hinzu:

    1. Wählen Sie im **Projektmappen-Explorer** den Ordner **Referenzen** unter dem **Projekt GettingStartedHost** aus, und wählen Sie dann im Kontextmenü **Referenz hinzufügen** aus.

    2. Wählen Sie im Dialogfeld **Referenz hinzufügen** unter **Projekte** auf der linken Seite des Fensters die Option **Projektmappe**aus.

    3. Wählen Sie **GettingStartedLib** im mittleren Bereich des Fensters aus, und wählen Sie dann **OK**aus.

       Mit dieser Aktion werden die im **GettingStartedLib-Projekt** definierten Typen für das **GettingStartedHost-Projekt** verfügbar.

3. Fügen Sie der <xref:System.ServiceModel> Assembly einen Verweis im **GettingStartedHost-Projekt** hinzu:

    1. Wählen Sie im **Projektmappen-Explorer** den Ordner **Referenzen** unter dem **Projekt GettingStartedHost** aus, und wählen Sie dann im Kontextmenü **Referenz hinzufügen** aus.

    2. Wählen Sie im Fenster **Referenz hinzufügen** unter **Baugruppen** auf der linken Seite des Fensters **Framework**aus.

    3. Wählen Sie **System.ServiceModel**aus , und wählen Sie dann **OK**aus.

    4. Speichern Sie die Lösung, indem Sie **Datei** > **speichern alle**auswählen.

## <a name="add-code-to-host-the-service"></a>Hinzufügen von Code zum Hosten des Dienstes

Um den Dienst zu hosten, fügen Sie Code hinzu, um die folgenden Schritte auszuführen:

1. Erstellen Sie einen URI für die Basisadresse.
2. Erstellen Sie eine Klasseninstanz zum Hosten des Dienstes.
3. Erstellen Sie einen Dienstendpunkt.
4. Aktivieren des Metadatenaustauschs
5. Öffnen Sie den Diensthost, um eingehende Nachrichten zu hören.
  
Nehmen Sie die folgenden Änderungen am Code vor:

1. Öffnen Sie die **Datei Program.cs** oder **Module1.vb** im **GettingStartedHost-Projekt,** und ersetzen Sie den Code durch den folgenden Code:

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
                    selfHost.Description.Behaviors.Add(smb)    ;

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

    Informationen zur Funktionsweise dieses Codes finden Sie unter [Servicehostingprogrammschritte](#service-hosting-program-steps).

2. Aktualisieren der Projekteigenschaften:

   1. Wählen Sie im **Projektmappen-Explorer-Fenster** den Ordner **GettingStartedHost** aus, und wählen Sie dann **Eigenschaften** im Kontextmenü aus.

   2. Wählen Sie auf der Seite **GettingStartedHost-Eigenschaften** die Registerkarte **Anwendung** aus:

      - Wählen Sie für C-Projekte aus der Liste des **Startobjekts** die Option **GettingStartedHost.Program** aus.

      - Wählen Sie für Visual Basic-Projekte **Service.Program** aus der Liste **Startobjekt** aus.

   3. Wählen Sie im Menü **Datei** die Option **Alle speichern**aus.

## <a name="verify-the-service-is-working"></a>Überprüfen, ob der Dienst funktioniert

1. Erstellen Sie die Lösung, und führen Sie dann die **GetStartedHost-Konsolenanwendung** in Visual Studio aus.

    Der Dienst muss mit Administratorrechten ausgeführt werden. Da Sie Visual Studio mit Administratorrechten geöffnet haben, wird die Anwendung beim Ausführen von **GettingStartedHost** in Visual Studio ebenfalls mit Administratorrechten ausgeführt. Alternativ können Sie eine neue Eingabeaufforderung als Administrator öffnen (im Kontextmenü **mehr** > **ausführen als Administrator** auswählen) und **GettingStartedHost.exe** darin ausführen.

2. Öffnen Sie einen Webbrowser, und navigieren `http://localhost:8000/GettingStarted/CalculatorService`Sie zur Seite des Dienstes unter .

   > [!NOTE]
   > Dienste wie dieser benötigen die entsprechende Berechtigung zum Registrieren von HTTP-Adressen auf dem Computer zum Abhören. Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden. Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](feature-details/configuring-http-and-https.md).

## <a name="service-hosting-program-steps"></a>Diensthostingprogrammschritte

Die Schritte im Code, den Sie dem Host des Dienstes hinzugefügt haben, werden wie folgt beschrieben:

- **Schritt 1**: Erstellen `Uri` Sie eine Instanz der Klasse, die die Basisadresse des Dienstes enthalten soll. Eine URL, die eine Basisadresse enthält, verfügt über einen optionalen URI, der einen Dienst identifiziert. Die Basisadresse ist wie `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`folgt formatiert: . Die Basisadresse für den Rechnerdienst verwendet den HTTP-Transport, localhost, Port 8000 und das URI-Segment " Erste Schritte".

- **Schritt 2**: Erstellen <xref:System.ServiceModel.ServiceHost> Sie eine Instanz der Klasse, die Sie zum Hosten des Dienstes verwenden. Der Konstruktor verwendet zwei Parameter: den Typ der Klasse, die den Servicevertrag implementiert, und die Basisadresse des Dienstes.

- **Schritt 3**: <xref:System.ServiceModel.Description.ServiceEndpoint> Erstellen Sie eine Instanz. Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen. Der <xref:System.ServiceModel.Description.ServiceEndpoint> Konstruktor besteht aus dem Dienstvertragsschnittstellentyp, einer Bindung und einer Adresse. Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren. Die Bindung für <xref:System.ServiceModel.WSHttpBinding>dieses Beispiel ist , die eine integrierte Bindung ist und eine Verbindung mit Endpunkten herstellt, die den WS-*-Spezifikationen entsprechen. Weitere Informationen zu WCF-Bindungen finden Sie unter Übersicht über [WCF-Bindungen](bindings-overview.md). Sie fügen die Adresse an die Basisadresse an, um den Endpunkt zu identifizieren. Der Code gibt die Adresse als CalculatorService und die `http://localhost:8000/GettingStarted/CalculatorService`vollqualifizierte Adresse für den Endpunkt als an.

    > [!IMPORTANT]
    > Für .NET Framework Version 4 und höher ist das Hinzufügen eines Dienstendpunkts optional. Wenn Sie für diese Versionen keinen Code oder keine Konfiguration hinzufügen, fügt WCF für jede Kombination aus Basisadresse und Vertrag, die vom Dienst implementiert wird, einen Standardendpunkt hinzu. Weitere Informationen zu Standardendpunkten finden Sie unter [Angeben einer Endpunktadresse](specifying-an-endpoint-address.md). Weitere Informationen zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Vereinfachte Konfiguration](simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](samples/simplified-configuration-for-wcf-services.md).

- **Schritt 4**: Aktivieren des Metadatenaustauschs. Clients verwenden Metadatenaustausch, um Proxys zum Aufrufen der Dienstvorgänge zu generieren. Um den Metadatenaustausch <xref:System.ServiceModel.Description.ServiceMetadataBehavior> zu aktivieren, <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> erstellen `true`Sie eine `ServiceMetadataBehavior` Instanz, <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> legen <xref:System.ServiceModel.ServiceHost> Sie ihre Eigenschaft auf , und fügen Sie das Objekt der Auflistung der Instanz hinzu.

- **Schritt 5** <xref:System.ServiceModel.ServiceHost> : Öffnen Sie, um eingehende Nachrichten zu hören. Die Anwendung wartet darauf, dass Sie **die Eingabetaste**drücken. Nachdem die Anwendung instanziiert <xref:System.ServiceModel.ServiceHost>hat, führt sie einen try/catch-Block aus. Weitere Informationen zum sicheren Abfangen <xref:System.ServiceModel.ServiceHost>von Ausnahmen, die von ausgelöst werden, finden Sie unter [Verwenden von Schließen und Abbrechen zum Freigeben von WCF-Clientressourcen](samples/use-close-abort-release-wcf-client-resources.md).

> [!IMPORTANT]
> Wenn Sie eine WCF-Dienstbibliothek hinzufügen, hostet Visual Studio sie für Sie, wenn Sie sie durch Starten eines Diensthosts debuggen. Um Konflikte zu vermeiden, können Sie verhindern, dass Visual Studio die WCF-Dienstbibliothek hostet.
>
> 1. Wählen Sie das **Projekt GettingStartedLib** im **Projektmappen-Explorer** aus, und wählen Sie **Eigenschaften** im Kontextmenü aus.
> 2. Wählen Sie **WCF-Optionen aus,** und deaktivieren Sie **WCF-Diensthost starten, wenn Sie ein anderes Projekt in derselben Projektmappe debuggen.**

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Folgendes gelernt:
> [!div class="checklist"]
>
> - Erstellen und konfigurieren Sie ein Konsolen-App-Projekt zum Hosten eines WCF-Dienstes.
> - Fügen Sie Code zum Hosten des WCF-Dienstes hinzu.
> - Aktualisieren Sie die Konfigurationsdatei.
> - Starten Sie den WCF-Dienst, und überprüfen Sie, ob er ausgeführt wird.

Fahren Sie mit dem nächsten Tutorial fort, um zu erfahren, wie Sie einen WCF-Client erstellen.

> [!div class="nextstepaction"]
> [Tutorial: Erstellen eines WCF-Clients](how-to-create-a-wcf-client.md)
