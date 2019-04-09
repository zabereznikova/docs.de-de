---
title: 'Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: ad9536b1f27ba3945bf76d0474de4825033a1e8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197905"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Tutorial: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts

In diesem Tutorial wird beschrieben, die dritte von fünf Schritte zur Erstellung einer grundlegenden Windows Communication Foundation (WCF)-Anwendung. Eine Übersicht über die Lernprogramme, finden Sie unter [Lernprogramm: Erste Schritte mit Windows Communication Foundation-Anwendungen](getting-started-tutorial.md).

Die nächste Aufgabe zum Erstellen einer WCF-Anwendung wird zum Hosten eines WCF-Diensts in einer Konsolenanwendung. Ein WCF-Dienst verfügbar macht, eine oder mehrere *Endpunkte*, von denen jeder macht eine oder mehrere Dienstvorgänge verfügbar. Ein Dienstendpunkt gibt die folgenden Informationen an: 
- Eine Adresse, in dem Sie den Dienst finden können.
- Eine Bindung, die Informationen enthält, die beschreibt, wie ein Client mit dem Dienst kommunizieren muss. 
- Ein Vertrag, der die Funktionalität definiert, die der Dienst seinen Clients bereitstellt.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt für das Hosten eines WCF-Diensts.
> - Fügen Sie Code zum Hosten des WCF-Diensts.
> - Aktualisieren Sie die Konfigurationsdatei an.
> - Starten Sie den WCF-Dienst, und überprüfen Sie, ob er ausgeführt wird.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt zum Hosten des Diensts

1. Erstellen Sie ein Konsolenanwendungsprojekt in Visual Studio: 
 
    1. Von der **Datei** , wählen Sie im Menü **öffnen** > **Projekt/Projektmappe** und navigieren Sie zu der **GettingStarted** Lösung Sie zuvor erstellt haben (*GettingStarted.sln*). Wählen Sie **öffnen**.

    2. Von der **Ansicht** , wählen Sie im Menü **Projektmappen-Explorer**.
    
    3. In der **Projektmappen-Explorer** wählen Sie im Fenster der **GettingStarted** -Lösung (obersten Knoten), und wählen Sie dann **hinzufügen** > **neues Projekt** aus dem Kontextmenü. 

    4. In der **neues Projekt hinzufügen** Fenster auf der linken Seite auf die **Windows Desktop** unter Kategorie **Visual C#**  oder **Visual Basic**. 

    5. Wählen Sie die **Konsolen-App ((.NET Framework)** Vorlage, und geben Sie *GettingStartedHost* für die **Namen**. Klicken Sie auf **OK**.

2. Fügen Sie einen Verweis in der **GettingStartedHost** Projekt die **GettingStartedLib** Projekt: 

    1. In der **Projektmappen-Explorer** wählen Sie im Fenster der **Verweise** Ordner unter dem **GettingStartedHost** Projekt, und wählen Sie dann **"Verweis hinzufügen"** aus dem Kontextmenü. 

    2. In der **Verweis hinzufügen** Dialogfeld unter **Projekte** wählen Sie auf der linken Seite des Fensters **Lösung**. 
 
    3. Wählen Sie **GettingStartedLib** im mittleren Abschnitt des Fensters, und wählen Sie dann **OK**. 

       Dadurch wird die in definierten Typen der **GettingStartedLib** Projekt zur Verfügung, um die **GettingStartedHost** Projekt.

3. Fügen Sie einen Verweis in der **GettingStartedHost** Projekt die <xref:System.ServiceModel> Assembly: 

    1. In der **Projektmappen-Explorer** wählen Sie im Fenster der **Verweise** Ordner unter dem **GettingStartedHost** Projekt, und wählen Sie dann **"Verweis hinzufügen"** aus dem Kontextmenü.
    
    2. In der **Verweis hinzufügen** Fenster unter **Assemblys** wählen Sie auf der linken Seite des Fensters **Framework**. 

    3. Wählen Sie **System.ServiceModel**, und wählen Sie dann **OK**. 
    
    4. Speichern Sie die Projektmappe durch Auswahl **Datei** > **Alles speichern**.

## <a name="add-code-to-host-the-service"></a>Fügen Sie Code zum Hosten des Diensts

Um den Dienst zu hosten, fügen Sie Code aus, um die folgenden Schritte ausführen: 
   1. Erstellen Sie einen URI für die Basisadresse.
   2. Erstellen Sie eine Klasseninstanz für den Dienst hostet.
   3. Erstellen eines Dienstendpunkts.
   4. Aktivieren des Metadatenaustauschs
   5. Öffnen Sie den Diensthost zum Lauschen auf eingehender Nachrichten.
  
Stellen Sie die folgenden Änderungen an den Code ein:

1. Öffnen der **"Program.cs"** oder **"Module1.vb"** Datei die **GettingStartedHost** Projekts, und Ersetzen Sie den Code durch den folgenden Code:

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
    
    Informationen dazu, wie dieser Code funktioniert, finden Sie unter [-Dienst hosten der Anwendung, Schritte](#service-hosting-program-steps).

2. Aktualisieren Sie die Projekteigenschaften an:

   1. In der **Projektmappen-Explorer** wählen Sie im Fenster der **GettingStartedHost** Ordner, und wählen Sie dann **Eigenschaften** aus dem Kontextmenü.

   2. Auf der **GettingStartedHost** Seite "Eigenschaften", wählen die **Anwendung** Registerkarte:

      - Für C# -Projekten auf **GettingStartedHost.Program** aus der **Startobjekt** Liste.

      - Wählen Sie für Visual Basic-Projekten **Service.Program** aus der **Startobjekt** Liste.

   3. Von der **Datei** , wählen Sie im Menü **Alles speichern**.

## <a name="verify-the-service-is-working"></a>Stellen Sie sicher, dass der Dienst funktioniert.

1. Erstellen Sie die Projektmappe, und führen Sie die **GettingStartedHost** Console Application "aus" in Visual Studio. 

    Der Dienst muss mit Administratorrechten ausgeführt werden. Da Sie beim Ausführen von Visual Studio mit Administratorrechten geöffnet **GettingStartedHost** in Visual Studio mit Administratorrechten sowie die Anwendung ausgeführt wird. Als Alternative können Sie eine neue Eingabeaufforderung als Administrator öffnen (Wählen Sie **weitere** > **als Administrator ausführen** aus dem Kontextmenü), und führen Sie **GettingStartedHost.exe**  darin.

2. Öffnen Sie einen Webbrowser und navigieren Sie zur Seite des Diensts `http://localhost:8000/GettingStarted/CalculatorService`.
   
   > [!NOTE]
   > Dienste wie dieser erfordern der erforderliche Berechtigung zum Registrieren von HTTP-Adressen auf dem Computer, für die Überwachung. Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden. Weitere Informationen zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS (Konfigurieren von HTTP und HTTPS)](feature-details/configuring-http-and-https.md). 

## <a name="service-hosting-program-steps"></a>Service hosting Programm Schritte

Die Schritte in den Code, zum Hosten des Diensts werden beschrieben hinzufügen, wie folgt:

- **Schritt 1**: Erstellen Sie eine Instanz von der `Uri` Klasse, die die Basisadresse des Diensts enthält. Eine URL, eine Basisadresse enthält, verfügt über einen optionalen URI, der einen Dienst kennzeichnet. Die Basisadresse ist wie folgt formatiert: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`. Die Basisadresse für den rechnerdienst verwendet den HTTP-Transport, Localhost, Port 8000 und das URI-Segment, GettingStarted.

- **Schritt 2**: Erstellen Sie eine Instanz von der <xref:System.ServiceModel.ServiceHost> -Klasse, die Sie verwenden, um den Dienst zu hosten. Der Konstruktor akzeptiert zwei Parameter: den Typ der Klasse, die den Dienstvertrag und die Basisadresse des Diensts implementiert.

- **Schritt 3**: Erstellen Sie eine <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanz. Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen. Die <xref:System.ServiceModel.Description.ServiceEndpoint> Konstruktor besteht aus den Schnittstellentyp des Dienstvertrags, eine Bindung und eine Adresse. Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren. Die Bindung für dieses Beispiel ist <xref:System.ServiceModel.WSHttpBinding>, das ist eine integrierte Bindung und eine Verbindung mit Endpunkten, die die WS - entsprechen * Spezifikationen. Weitere Informationen zu WCF-Bindungen finden Sie unter [WCF-bindungsübersicht](bindings-overview.md). Sie fügen die Adresse, an der Basisadresse, um den Endpunkt zu identifizieren. Der Code gibt die Adresse als CalculatorService und die vollqualifizierte Adresse für den Endpunkt als `http://localhost:8000/GettingStarted/CalculatorService`.

    > [!IMPORTANT]
    > Für .NET Framework Version 4 und höher, ist das Hinzufügen eines Dienstendpunkts optional. Wenn Sie nicht Ihr Code oder Konfiguration hinzufügen, fügt WCF für diesen Versionen ein Standardendpunkt für jede Kombination aus Basisadresse und vom Dienst implementierten Vertrag. Weitere Informationen zu Standardendpunkten, finden Sie unter [angeben einer Endpunktadresse](specifying-an-endpoint-address.md). Weitere Informationen zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Dank vereinfachter Konfiguration](simplified-configuration.md) und [Dank vereinfachter Konfiguration für WCF-Dienste](samples/simplified-configuration-for-wcf-services.md).

- **Schritt 4**: Aktivieren des Metadatenaustauschs Clients verwenden Metadatenaustausch, um Proxys zu generieren, für die Dienstvorgänge aufruft. Zum Aktivieren von Metadatenaustausch erstellen eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior> Instanz, legen die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> Eigenschaft `true`, und fügen die `ServiceMetadataBehavior` -Objekt der <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> Auflistung von der <xref:System.ServiceModel.ServiceHost> Instanz.

- **Schritt 5**: Open <xref:System.ServiceModel.ServiceHost> zum Lauschen auf eingehender Nachrichten. Die Anwendung wartet, bis Sie drücken **EINGABETASTE**. Nachdem die Anwendung instanziiert <xref:System.ServiceModel.ServiceHost>, es wird einen Try/Catch-Block ausgeführt. Weitere Informationen zum sicheren Abfangen von Ausnahmen durch <xref:System.ServiceModel.ServiceHost>, finden Sie unter [verwenden schließen "und" Abort, um WCF-Client-Ressourcen freizugeben](samples/use-close-abort-release-wcf-client-resources.md).

> [!IMPORTANT]
> Wenn Sie eine WCF-Dienstbibliothek hinzufügen, hostet Visual Studio es für Sie, wenn Sie es Debuggen, indem Sie ein Diensthost ab. Um Konflikte zu vermeiden, können Sie verhindern, dass Visual Studio Hosten von WCF-Dienstbibliothek. 
> 1. Wählen Sie die **GettingStartedLib** Projekt **Projektmappen-Explorer** , und wählen Sie **Eigenschaften** aus dem Kontextmenü.
> 2. Wählen Sie **WCF-Optionen** , und deaktivieren Sie **starten WCF-Diensthost beim Debuggen von einem anderen Projekt in der gleichen Projektmappe**.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> - Erstellen Sie und konfigurieren Sie ein Konsolenanwendungsprojekt für das Hosten eines WCF-Diensts.
> - Fügen Sie Code zum Hosten des WCF-Diensts.
> - Aktualisieren Sie die Konfigurationsdatei an.
> - Starten Sie den WCF-Dienst, und überprüfen Sie, ob er ausgeführt wird.

Fahren Sie fort mit dem nächsten Tutorial erfahren, wie beim Erstellen eines WCF-Clients.

> [!div class="nextstepaction"]
> [Tutorial: Erstellen Sie einen WCF-client](how-to-create-a-wcf-client.md)
