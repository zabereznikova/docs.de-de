---
title: 'Gewusst wie: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts'
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a13e5a0044c51700acce6b123688868443f635ae
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Gewusst wie: Hosten und Ausführen eines grundlegenden Windows Communication Foundation-Diensts
Dies ist die dritte von sechs Aufgaben, die zum Erstellen einer grundlegenden [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Anwendung erforderlich sind. Einen Überblick über alle sechs Aufgaben finden Sie unter der [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md) Thema.  
  
 In diesem Thema wird beschrieben, wie ein [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Dienst in einer Konsolenanwendung gehostet wird. Dieses Verfahren umfasst die folgenden Schritte:  
  
-   Erstellen eines Konsolenanwendungsprojekts zum Hosten des Diensts  
  
-   Erstellen eines Diensthosts für den Dienst  
  
-   Aktivieren des Metadatenaustauschs  
  
-   Öffnen des Diensthosts  
  
 Eine vollständige Liste des für diese Aufgabe geschriebenen Codes wird in einem Beispiel im Anschluss an das Verfahren bereitgestellt.  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a>So erstellen Sie eine neue Konsolenanwendung zum Hosten des Diensts  
  
1.  Erstellen Sie ein neues Konsolenanwendungsprojekt mit der rechten Maustaste auf die erste Schritte-Projektmappe, wenn Sie auswählen, **hinzufügen**, **neues Projekt**. In der **neues Projekt hinzufügen** -Dialogfeld auf der linken Seite der Dialogfeld Select **Windows** unter **c#** oder **VB**. Wählen Sie im mittleren Abschnitt des Dialogfelds **Konsolenanwendung**. Nennen Sie das Projekt GettingStartedHost.  
  
2.  Legen Sie das Zielframework des GettingStartedHost-Projekts auf .NET Framework 4.5 per Rechtsklick auf **"gettingstartedhost"** im Projektmappen-Explorer auswählen und **Eigenschaften**. Im Dropdownfeld mit der Bezeichnung **Zielframework** wählen **.NET Framework 4.5**. Festlegen des Zielframeworks für ein VB-Projekt weicht etwas im Eigenschaftendialogfeld GettingStartedHost-Projekts klicken Sie auf die **Kompilieren** Registerkarte auf der linken Seite des Bildschirms, und klicken Sie dann auf die **erweiterte kompilieren Optionen** Schaltfläche auf der unteren linken Ecke des Dialogfelds. Wählen Sie dann **.NET Framework 4.5** im Dropdownfeld mit der Bezeichnung **Zielframework**.  
  
     Festlegen des Zielframeworks führt dazu, dass [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] um die Projektmappe erneut zu laden, drücken Sie die **OK** Aufforderung.  
  
3.  GettingStartedHost-Projekts einen Verweis auf das GettingStartedLib-Projekt hinzugefügt, indem Sie mit der mit der rechten Maustaste auf die **Verweise** Ordner unter dem GettingStartedHost-Projekt im Projektmappen-Explorer und wählen **Verweis hinzufügen** . In der **Verweis hinzufügen** wählen Sie im Dialogfeld **Lösung** auf der linken Seite des Dialogfeld und wählen GettingStartedLib im mittleren Abschnitt des Dialogfeld und klicken Sie auf **hinzufügen**. Dadurch werden die in GettingStartedLib definierten Typen für das GettingStartedHost-Projekt verfügbar.  
  
4.  Fügen Sie einen Verweis auf System.ServiceModel dem GettingStartedHost-Projekt, indem Sie mit der rechten Maustaste die **Verweis** Ordner unter dem GettingStartedHost-Projekt im Projektmappen-Explorer und wählen **hinzufügen** Verweis. In der **Verweis hinzufügen** Dialogfeld wählen **Framework** auf der linken Seite des Dialogfelds. Geben Sie im Textfeld Assemblys suchen`System.ServiceModel` ein. Wählen Sie im mittleren Abschnitt des Dialogfelds **System.ServiceModel**, klicken Sie auf die **hinzufügen** aus, und klicken Sie auf die **schließen** Schaltfläche. Speichern Sie die Projektmappe, indem Sie unterhalb des Hauptmenüs auf die Schaltfläche Alle speichern klicken.  
  
### <a name="to-host-the-service"></a>So hosten Sie den Dienst  
  
-   Öffnen Sie die Datei Program.cs oder Module.vb, und geben Sie den folgenden Code ein:  
  
    ```csharp
    // program.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
    using GettingStartedLib;  
    using System.ServiceModel.Description;   
  
    namespace GettingStartedHost  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                // Step 1 Create a URI to serve as the base address.  
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");  
  
                // Step 2 Create a ServiceHost instance  
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
  
                try  
                {  
                    // Step 3 Add a service endpoint.  
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");  
  
                    // Step 4 Enable metadata exchange.  
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
                    smb.HttpGetEnabled = true;  
                    selfHost.Description.Behaviors.Add(smb);  
  
                    // Step 5 Start the service.  
                    selfHost.Open();  
                    Console.WriteLine("The service is ready.");  
                    Console.WriteLine("Press <ENTER> to terminate service.");  
                    Console.WriteLine();  
                    Console.ReadLine();  
  
                    // Close the ServiceHostBase to shutdown the service.  
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
    'Module1.vb  
    Imports System  
    Imports System.ServiceModel  
    Imports System.ServiceModel.Description  
    Imports GettingStartedLibVB.GettingStartedLib  
  
    Module Service  
  
        Class Program  
            Shared Sub Main()  
                ' Step 1 Create a URI to serve as the base address  
                Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
                ' Step 2 Create a ServiceHost instance  
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)  
                Try  
  
                    ' Step 3 Add a service endpoint  
                    ' Add a service endpoint  
                    selfHost.AddServiceEndpoint( _  
                        GetType(ICalculator), _  
                        New WSHttpBinding(), _  
                        "CalculatorService")  
  
                    ' Step 4 Enable metadata exchange.  
                    Dim smb As New ServiceMetadataBehavior()  
                    smb.HttpGetEnabled = True  
                    selfHost.Description.Behaviors.Add(smb)  
  
                    ' Step 5 Start the service  
                    selfHost.Open()  
                    Console.WriteLine("The service is ready.")  
                    Console.WriteLine("Press <ENTER> to terminate service.")  
                    Console.WriteLine()  
                    Console.ReadLine()  
  
                    ' Close the ServiceHostBase to shutdown the service.  
                    selfHost.Close()  
                Catch ce As CommunicationException  
                    Console.WriteLine("An exception occurred: {0}", ce.Message)  
                    selfHost.Abort()  
                End Try  
            End Sub  
        End Class  
  
    End Module  
    ```  
  
    1.  Schritt 1: Erstellt eine Instanz der URI-Klasse, die die Basisadresse des Diensts enthält. Dienste werden über eine URL identifiziert, die eine Basisadresse und einen optionalen URI enthält. Die Basisadresse weist das folgende Format: [transport] :// [-Computernamen oder die Domäne] [: optionale # port] / [optionale URI-Segment] die Basisadresse für den rechnerdienst verwendet den HTTP-Transport, "localhost", Port 8000 und der URI-segment "Erste Schritte"  
  
    2.  Schritt 2: Erstellt eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse zum Hosten des Diensts. Der Konstruktor akzeptiert zwei Parameter: den Typ der Klasse, die den Dienstvertrag implementiert, und die Basisadresse des Diensts.  
  
    3.  Schritt 3: erstellt eine <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` Instanz. Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen. Die <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` Konstruktor akzeptiert daher den Schnittstellentyp des Dienstvertrags, einer Bindung und eine Adresse. Der Dienstvertrag ist `ICalculator`, den Sie definiert haben und im Diensttyp implementieren. Die in diesem Beispiel verwendete Bindung ist <xref:System.ServiceModel.WSHttpBinding>. Dies ist eine integrierte Bindung, die für die Verbindung mit Endpunkten verwendet wird, die den WS-*-Spezifikationen entsprechen. Weitere Informationen zu WCF-Bindungen, finden Sie unter [WCF-Bindungsübersicht](../../../docs/framework/wcf/bindings-overview.md). Die Adresse wird an die Basisadresse angefügt, um den Endpunkt zu identifizieren. In diesem Code die angegebene Adresse ist "CalculatorService" aus, damit die vollqualifizierte Adresse für den Endpunkt ist `"http://localhost:8000/GettingStarted/CalculatorService"` Hinzufügen eines Dienstendpunkts ist optional, wenn mithilfe von .NET Framework 4.0 oder höher. Wenn im Code oder in der Konfiguration keine Endpunkte hinzugefügt wurden, fügt WCF in diesen Versionen einen Standardendpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wurden. Weitere Informationen zu Endpunkten finden Sie unter [angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
        > [!IMPORTANT]
        >  Das Hinzufügen eines Dienstendpunkts ist optional, wenn .NET Framework 4 oder höher verwendet wird. Wenn im Code oder in der Konfiguration keine Endpunkte hinzugefügt wurden, fügt WCF in diesen Versionen einen Standardendpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wurden. Weitere Informationen zu Endpunkten finden Sie unter [angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
    4.  Schritt 4: Aktiviert den Metadatenaustausch. Clients verwenden den Metadatenaustausch, um Proxys zu generieren, die zum Aufrufen von Dienstvorgängen verwendet werden. Zum Aktivieren von Metadatenaustausch erstellen eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior> Instanz, legen Sie es des <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> Eigenschaft `true`, und Hinzufügen des Verhaltens zur der <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  --> `System.ServiceModel.ServiceHost.Behaviors%2A` Auflistung von der <xref:System.ServiceModel.ServiceHost> Instanz.  
  
    5.  Schritt 5: Öffnet den <xref:System.ServiceModel.ServiceHost>, um auf eingehende Nachrichten zu lauschen. Der Code wartet darauf, dass der Benutzer die EINGABETASTE drückt. Wenn dies nicht erfolgt, wird die App sofort geschlossen und der Dienst heruntergefahren. Beachten Sie auch, dass ein try/catch-Block verwendet wird. Nachdem der <xref:System.ServiceModel.ServiceHost> instanziiert wurde, wird der gesamte sonstige Code in einen try/catch-Block eingefügt. Weitere Informationen zu sicher ausgelöste Ausnahmen abfangen <xref:System.ServiceModel.ServiceHost>, finden Sie unter [Vermeiden von Problemen mit der Using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)  
  
### <a name="to-verify-the-service-is-working"></a>So überprüfen Sie, ob der Dienst funktioniert  
  
1.  Führen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] die GettingStartedHost-Konsolenanwendung aus. Beim Ausführen unter [!INCLUDE[wv](../../../includes/wv-md.md)] und höher muss der Dienst mit Administratorrechten ausgeführt werden. Da Visual Studio mit Administratorrechten ausgeführt wurde, wird "gettingstartedhost" auch mit Administratorrechten ausführen. Sie können auch eine neue Eingabeaufforderung mit Administratorrechten starten und "service.exe" damit ausführen.  
  
2.  Öffnen Sie Internet Explorer, und navigieren Sie unter `http://localhost:8000/GettingStarted/CalculatorService` zur Debuggingseite des Diensts.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält den Dienstvertrag und die Implementierung aus den vorangegangenen Schritten im Lernprogramm und hostet den Dienst in einer Konsolenanwendung.  
  
 Um dies mit einem Befehlszeilen-Compiler kompilieren, kompilieren Sie "IService1.cs" und "Service1.cs" in einer Klasse Bibliothek verweisen auf `System.ServiceModel.dll`. Und kompilieren Sie Program.cs in eine Konsolenanwendung.  
  
```csharp
// IService1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
namespace GettingStartedLib  
{  
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
        public interface ICalculator  
        {  
            [OperationContract]  
            double Add(double n1, double n2);  
            [OperationContract]  
            double Subtract(double n1, double n2);  
            [OperationContract]  
            double Multiply(double n1, double n2);  
            [OperationContract]  
            double Divide(double n1, double n2);  
        }  
}  
```  
  
```csharp
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
namespace GettingStartedLib  
{  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            double result = n1 + n2;  
            Console.WriteLine("Received Add({0},{1})", n1, n2);  
            // Code added to write output to the console window.  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Subtract(double n1, double n2)  
        {  
            double result = n1 - n2;  
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Multiply(double n1, double n2)  
        {  
            double result = n1 * n2;  
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Divide(double n1, double n2)  
        {  
            double result = n1 / n2;  
            Console.WriteLine("Received Divide({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
    }  
}  
```  
  
```csharp
//Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
using GettingStartedLib;  
using System.ServiceModel.Description;   
  
namespace GettingStartedHost  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Uri baseAddress = new Uri("http://localhost:8000/ServiceModelSamples/Service");  
  
            // Step 2 of the hosting procedure: Create ServiceHost  
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
  
            try  
            {  
                // Step 3 of the hosting procedure: Add a service endpoint.  
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");  
  
                // Step 4 of the hosting procedure: Enable metadata exchange.  
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
                smb.HttpGetEnabled = true;  
                selfHost.Description.Behaviors.Add(smb);  
  
                // Step 5 of the hosting procedure: Start (and then stop) the service.  
                selfHost.Open();  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
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
'IService1.vb  
Imports System  
Imports System.ServiceModel  
  
Namespace GettingStartedLib  
  
    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _  
    Public Interface ICalculator  
  
        <OperationContract()> _  
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()> _  
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()> _  
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()> _  
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
    End Interface  
End Namespace  
```  
  
```vb
'Service1.vb  
Imports System  
Imports System.ServiceModel  
  
Namespace GettingStartedLib  
  
    Public Class CalculatorService  
        Implements ICalculator  
  
        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add  
            Dim result As Double = n1 + n2  
            ' Code added to write output to the console window.  
            Console.WriteLine("Received Add({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
        End Function  
  
        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract  
            Dim result As Double = n1 - n2  
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
  
        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply  
            Dim result As Double = n1 * n2  
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
  
        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide  
            Dim result As Double = n1 / n2  
            Console.WriteLine("Received Divide({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
    End Class  
End Namespace  
```  
  
```vb
'Module1.vb  
Imports System  
Imports System.ServiceModel  
Imports System.ServiceModel.Description  
Imports GettingStartedLibVB.GettingStartedLib  
  
Module Service  
  
    Class Program  
        Shared Sub Main()  
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
            ' Step 2 of the hosting procedure: Create ServiceHost  
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)  
            Try  
  
                ' Step 3 of the hosting procedure: Add a service endpoint.  
                ' Add a service endpoint  
                selfHost.AddServiceEndpoint( _  
                    GetType(ICalculator), _  
                    New WSHttpBinding(), _  
                    "CalculatorService")  
  
                ' Step 4 of the hosting procedure: Enable metadata exchange.  
                ' Enable metadata exchange  
                Dim smb As New ServiceMetadataBehavior()  
                smb.HttpGetEnabled = True  
                selfHost.Description.Behaviors.Add(smb)  
  
                ' Step 5 of the hosting procedure: Start (and then stop) the service.  
                selfHost.Open()  
                Console.WriteLine("The service is ready.")  
                Console.WriteLine("Press <ENTER> to terminate service.")  
                Console.WriteLine()  
                Console.ReadLine()  
  
                ' Close the ServiceHostBase to shutdown the service.  
                selfHost.Close()  
            Catch ce As CommunicationException  
                Console.WriteLine("An exception occurred: {0}", ce.Message)  
                selfHost.Abort()  
            End Try  
        End Sub  
    End Class  
  
End Module  
```  
  
> [!NOTE]
>  Dienste wie dieser müssen dazu berechtigt sein, HTTP-Adressen auf dem Computer zum Überwachen zu registrieren. Administratorkonten verfügen über diese Berechtigung, anderen Konten muss jedoch die Berechtigung für HTTP-Namespaces erteilt werden. [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Konfigurieren von Namespacereservierungen finden Sie unter [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md). Bei Ausführung in Visual Studio muss die service.exe mit Administratorrechten ausgeführt werden.  
  
 Der Dienst wird nun ausgeführt. Fahren Sie mit [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Informationen zur Problembehandlung finden Sie unter [Problembehandlung für das Lernprogramm für erste Schritte](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)
