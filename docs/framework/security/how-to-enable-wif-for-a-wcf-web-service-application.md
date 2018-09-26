---
title: 'Gewusst wie: Aktivieren von WIF für eine WCF-Webdienstanwendung'
ms.date: 03/30/2017
ms.assetid: bfc64b3d-64e9-4093-a6a4-72e933917af7
author: BrucePerlerMS
ms.openlocfilehash: c3d22d812fdd5a1fc7567b3da34e7fd5a59531cd
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47207230"
---
# <a name="how-to-enable-wif-for-a-wcf-web-service-application"></a>Gewusst wie: Aktivieren von WIF für eine WCF-Webdienstanwendung
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   Microsoft® Windows® Communication Foundation (WCF)  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser Vorgehensweise werden ausführliche schrittweise Prozeduren zum Aktivieren von WIF in einem WCF-Webdienst vorgestellt. Sie enthält auch Anweisungen für Tests der Anwendung, mit denen überprüft werden kann, ob der Webdienst Ansprüche ordnungsgemäß darstellt, wenn die Anwendung ausgeführt wird. Diese Vorgehensweise enthält keine ausführlichen Anweisungen zum Erstellen eines Sicherheitstokendiensts (STS). Stattdessen wird der Entwicklungs-STS verwendet, der aus dem Identitäts- und Zugriffstool stammt. Der Entwicklungs-STS führt keine echte Authentifizierung durch und ist nur für Testzwecke vorgesehen. Sie müssen das Identitäts- und Zugriffs-Tool installieren, um diese Vorgehensweise nachzuvollziehen. Es kann auf der folgenden Seite heruntergeladen werden: [Identity and Access Tool (Identitäts- und Zugriffstool)](https://go.microsoft.com/fwlink/?LinkID=245849)  
  
## <a name="contents"></a>Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1 – Erstellen eines einfachen WCF-Diensts  
  
-   Schritt 2 – Erstellen einer Clientanwendung für den WCF-Dienst  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="objectives"></a>Ziele  
  
-   Erstellen eines WCF-Diensts, für den Token ausgestellt werden müssen  
  
-   Erstellen eines WCF-Clients, für den ein Token aus einem STS erforderlich ist, der an den WCF-Dienst weitergeleitet wird  
  
## <a name="overview"></a>Übersicht  
 In dieser Vorgehensweise wird veranschaulicht, wie ein Entwickler Verbundauthentifizierung bei der Entwicklung eines WCF-Diensts verwenden kann. Die Verwendung eines Verbunds in WCF-Diensten hat folgende Vorteile:  
  
1.  Ausklammern der Authentifizierungslogik aus dem WCF-Dienstcode  
  
2.  Wiederverwenden vorhandener Projektmappen für die Identitätsverwaltung  
  
3.  Interoperabilität mit anderen Identitätsprojektmappen  
  
4.  Flexibilität und Agilität für zukünftige Änderungen  
  
 Mit WIF und dem zugeordneten Identitäts- und Zugriffs-Tool kann ein WCF-Dienst einfacher mit Verbundauthentifizierung entwickelt und getestet werden. Die ist in den folgenden Schritten dargestellt.  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1 – Erstellen eines einfachen WCF-Diensts  
  
-   Schritt 2 – Erstellen einer Clientanwendung für den WCF-Dienst  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="step-1--create-a-simple-wcf-service"></a>Schritt 1 – Erstellen eines einfachen WCF-Diensts  
 In diesem Schritt erstellen Sie einen neuen WCF-Dienst, für den der im Identitäts- und Zugriffs-Tool enthaltene Entwicklungs-STS verwendet wird.  
  
#### <a name="to-create-a-simple-wcf-service"></a>So erstellen Sie einen einfachen WCF-Dienst  
  
1.  Starten Sie Visual Studio im erweiterten Modus als Administrator.  
  
2.  Klicken Sie in Visual Studio auf **Datei**, **Neu** und anschließend auf **Projekt**.  
  
3.  Klicken Sie im Fenster **Neues Projekt** auf **WCF-Dienstanwendung**.  
  
4.  Geben Sie im Feld **Name** die Zeichenfolge `TestService` ein, und drücken Sie auf **OK**.  
  
5.  Klicken Sie mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestService**, und klicken Sie dann auf **Identität und Zugriff**.  
  
6.  Das Fenster **Identität und Zugriff** wird geöffnet. Klicken Sie unter **Anbieter** auf **Anwendung mit dem lokalen Entwicklungs-STS testen**, und klicken Sie auf **Übernehmen**. Mit dem Identitäts- und Zugriffs-Tool wird der Dienst so konfiguriert, dass WIF verwendet wird und die Authentifizierung in den lokalen Entwicklungs-STS (**LocalSTS**) ausgelagert wird. Dazu werden der Datei *Web.config* Konfigurationselemente hinzugefügt.  
  
7.  Fügen Sie in der Datei *Service1.svc.cs* eine `using`-Anweisung für den Namespace **System.Security.Claims** hinzu, und ersetzen Sie den vorhandenen Code durch folgenden Code. Speichern Sie die Datei anschließend:  
  
    ```csharp  
    public class Service1 : IService1  
    {  
        public string ComputeResponse(string input)  
        {  
            // Get the caller's identity from ClaimsPrincipal.Current  
            ClaimsPrincipal claimsPrincipal = OperationContext.Current.ClaimsPrincipal;  
  
            // Start generating the output  
            StringBuilder builder = new StringBuilder();  
            builder.AppendLine("Computed by ClaimsAwareWebService");  
            builder.AppendLine("Input received from client:" + input);  
  
            if (claimsPrincipal != null)  
            {  
                // Display the claims from the caller. Do not use this code in a production application.  
                ClaimsIdentity identity = claimsPrincipal.Identity as ClaimsIdentity;  
                builder.AppendLine("Client Name:" + identity.Name);  
                builder.AppendLine("IsAuthenticated:" + identity.IsAuthenticated);  
                builder.AppendLine("The service received the following issued claims of the client:");  
  
                // Iterate over the caller’s claims and append to the output  
                foreach (Claim claim in claimsPrincipal.Claims)  
                {  
                    builder.AppendLine("ClaimType :" + claim.Type + "   ClaimValue:" + claim.Value);  
                }  
            }  
  
            return builder.ToString();  
        }  
    }  
    ```  
  
     Die `ComputeResponse`-Methode zeigt die Eigenschaften verschiedener Ansprüche an, die von **LocalSTS** ausgegeben werden.  
  
8.  Ersetzen Sie in der Datei *IService1.cs* den vorhandenen Code durch folgenden Code. Speichern Sie die Datei anschließend:  
  
    ```csharp  
    [ServiceContract]  
    public interface IService1  
    {  
        [OperationContract]  
        string ComputeResponse(string input);  
    }  
    ```  
  
9. Erstellen Sie das Projekt.  
  
10. Drücken Sie **STRG+F5**, um den Dienst auszuführen, ohne den Debugger zu starten. Eine Webseite für den Dienst wird geöffnet. Hier können Sie im Infobereich (Taskleiste) überprüfen, ob **LocalSTS** ausgeführt wird.  
  
    > [!IMPORTANT]
    >  Sowohl **TestService** als auch **LocalSTS** müssen ausgeführt werden, wenn Sie im nächsten Schritt der Clientanwendung den Dienstverweis hinzufügen.  
  
## <a name="step-2--create-a-client-application-for-the-wcf-service"></a>Schritt 2 – Erstellen einer Clientanwendung für den WCF-Dienst  
 In diesem Schritt erstellen Sie eine Konsolenanwendung, in der der Entwicklungs-STS für die Authentifizierung des WCF-Diensts verwendet wird, den Sie im vorherigen Schritt erstellt haben.  
  
#### <a name="to-create-a-client-application"></a>So erstellen Sie eine Clientanwendung  
  
1.  Klicken Sie in Visual Studio mit der rechten Maustaste auf die Projektmappe, und klicken Sie dann auf **Hinzufügen** und **Neues Projekt**.  
  
2.  Wählen Sie im Fenster **Neues Projekt hinzufügen** aus der Vorlagenliste **Visual C#** den Eintrag **Konsolenanwendung** aus, geben Sie `Client` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird im Projektmappenordner erstellt.  
  
3.  Klicken Sie mit der rechten Maustaste unter dem Projekt **Client** auf **Verweise**, und klicken Sie dann auf **Dienstverweis hinzufügen**.  
  
4.  Klicken Sie im Fenster **Dienstverweis hinzufügen** auf den Dropdownpfeil der Schaltfläche **Ermitteln**, und klicken Sie auf **Dienste in der Projektmappe**. Die **Adresse** wird automatisch mit dem WCF-Dienst aufgefüllt, den Sie zuvor erstellt haben, und der **Namespace** wird auf **ServiceReference1** festgelegt. Klicken Sie auf **OK**.  
  
    > [!IMPORTANT]
    >  Sowohl **TestService** als auch **LocalSTS** müssen ausgeführt werden, wenn Sie dem Client den Dienstverweis hinzufügen.  
  
5.  Visual Studio generiert Proxyklassen für den WCF-Dienst und fügt alle erforderlichen Referenzinformationen hinzu. Auch werden der Datei *App.config* Elemente hinzugefügt, mit denen der Client so konfiguriert wird, dass für die Authentifizierung im Dienst ein Token aus dem STS abgerufen wird. Wenn dieser Prozess abgeschlossen ist, wird die Datei **Program.cs** geöffnet. Fügen Sie eine `using`-Anweisung für **System.ServiceModel** und eine weitere für **Client.ServiceReference1** hinzu. Ersetzen Sie dann die **Main**-Methode durch folgenden Code, und speichern Sie die Datei anschließend:  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        // Create the client for the service  
        Service1Client client = new Service1Client();  
        Console.WriteLine("-------------WCF Client Application--------------\n");  
  
        while (!ShouldQuitApplication())  
        {  
            try  
            {  
                Console.WriteLine(client.ComputeResponse("Hello World"));  
            }  
            catch (CommunicationException e)  
            {  
                Console.WriteLine(e.Message);  
                Console.WriteLine(e.StackTrace);  
                Exception ex = e.InnerException;  
                while (ex != null)  
                {  
                    Console.WriteLine("===========================");  
                    Console.WriteLine(ex.Message);  
                    Console.WriteLine(ex.StackTrace);  
                    ex = ex.InnerException;  
                }  
            }  
            catch (TimeoutException)  
            {  
                Console.WriteLine("Timed out...");  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("An unexpected exception occurred.");  
                Console.WriteLine(e.StackTrace);  
            }  
        }  
  
        client.Close();  
  
        if (client != null)  
        {  
            client.Abort();  
        }  
    }  
  
    static bool ShouldQuitApplication()  
    {  
        Console.WriteLine("---------------------------------------------------------------------");  
        Console.WriteLine("Press Enter key to invoke service, any other key to quit application:");  
        Console.WriteLine("----------------------------------------------------------------------");  
  
        ConsoleKeyInfo keyInfo = Console.ReadKey();  
        if (keyInfo.Key == ConsoleKey.Enter)  
            return false;  
        return true;  
    }  
    ```  
  
6.  Öffnen Sie die Datei *App.config*, fügen Sie folgenden XML-Code als erstes untergeordnetes Element unter dem `<system.serviceModel>`-Element hinzu, und speichern Sie die Datei anschließend:  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
         <behavior>  
           <clientCredentials>  
             <serviceCertificate>  
               <authentication certificateValidationMode="None"/>  
             </serviceCertificate>  
           </clientCredentials>  
         </behavior>  
       </endpointBehaviors>  
     </behaviors>  
    ```  
  
     Damit wird die Zertifikatsvalidierung deaktiviert.  
  
7.  Klicken Sie mit der rechten Maustaste auf die Projektmappe **TestService**, und klicken Sie auf **Startprojekte festlegen...**. Die Eigenschaftenseite **Startprojekt** wird geöffnet. Wählen Sie auf der Eigenschaftenseite **Startprojekt** die Option **Mehrere Startprojekte** aus, klicken Sie dann für jedes Projekt in das Feld **Aktion**, und wählen Sie im Dropdownmenü **Starten** aus. Klicken Sie auf **OK**, um die Einstellungen zu speichern.  
  
8.  Erstellen Sie die Projektmappe.  
  
## <a name="step-3--test-your-solution"></a>Schritt 3: Testen Ihrer Projektmappe  
 In diesem Schritt testen Sie die für WIF aktivierte WCF-Anwendung und überprüfen, ob Ansprüche dargestellt werden.  
  
#### <a name="to-test-your-wif-enabled-wcf-application-for-claims"></a>So testen Sie die für WIF aktivierte WCF-Anwendung auf Ansprüche  
  
1.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen. Ein Konsolenfenster mit folgendem Text wird angezeigt: **Press Enter key to invoke service, any other key to quit application:** (EINGABETASTE drücken, um den Dienst aufzurufen. Drücken Sie eine andere Taste, um die Anwendung zu beenden:)  
  
2.  Drücken Sie die **EINGABETASTE**. Folgende Anspruchsinformationen sollten in der Konsole angezeigt werden:  
  
    ```  
    Computed by Service1  
    Input received from client: Hello World  
    Client Name: Terry  
    IsAuthenticated: True  
    The service received the following issued claims of the client:  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name    ClaimValue:Terry  
    ClaimType :http://schema.xmlsoap.org/ws/2005/05/identity/claims/surname    ClaimValue:Adams  
    ClaimType :http://schemas.microsoft.com/ws/2008/06/identity/claims/role    ClaimValue:developer  
    ClaimType :http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress    ClaimValue:terry@contoso.com  
    ```  
  
    > [!IMPORTANT]
    >  Sowohl **TestService** als auch **LocalSTS** müssen ausgeführt werden, bevor Sie die **EINGABETASTE** drücken. Eine Webseite für den Dienst wird geöffnet. Hier können Sie im Infobereich (Taskleiste) überprüfen, ob **LocalSTS** ausgeführt wird.  
  
3.  Wenn diese Ansprüche in der Konsole angezeigt werden, wurde die Authentifizierung im STS erfolgreich durchgeführt, und es werden Ansprüche vom WCF-Dienst angezeigt.
