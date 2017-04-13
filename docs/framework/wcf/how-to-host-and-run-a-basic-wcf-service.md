---
title: "Gewusst wie: Hosten und Ausf&#252;hren eines grundlegenden Windows Communication Foundation-Diensts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "WCF-Dienste [WCF]"
  - "WCF-Dienste [WCF], Ausführen"
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
caps.latest.revision: 58
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 58
---
# Gewusst wie: Hosten und Ausf&#252;hren eines grundlegenden Windows Communication Foundation-Diensts
Dies ist die dritte von sechs Aufgaben, die zum Erstellen einer grundlegenden [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendung erforderlich sind.Eine Übersicht über alle sechs Aufgaben finden Sie im Thema [Lernprogramm 'Erste Schritte'](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 In diesem Thema wird beschrieben, wie ein [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienst in einer Konsolenanwendung gehostet wird.Dieses Verfahren umfasst die folgenden Schritte:  
  
-   Erstellen Sie ein Konsolenanwendungsprojekt, um den Dienst zu hosten.  
  
-   Erstellen eines Diensthosts für den Dienst  
  
-   Aktivieren des Metadatenaustauschs  
  
-   Öffnen des Diensthosts  
  
 Eine vollständige Liste des für diese Aufgabe geschriebenen Codes wird in einem Beispiel im Anschluss an das Verfahren bereitgestellt.  
  
### So erstellen Sie eine neue Konsolenanwendung, um den Dienst zu hosten  
  
1.  Erstellen Sie ein neues Konsolenanwendungsprojekt, indem Sie mit der rechten Maustaste auf die Projektmappe "Erste Schritte" klicken und dann **Hinzufügen** und **Neues Projekt** auswählen.Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** auf der linken Seite des Dialogfelds **Windows** unter **C\#** oder **VB** aus.Wählen Sie im mittleren Abschnitt des Dialogfelds **Konsolenanwendung** aus.Nennen Sie das Projekt "GettingStartedHost".  
  
2.  Legen Sie das Zielframework des GettingStartedHost\-Projekts auf .NET Framework 4.5 fest, indem Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **GettingStartedHost** klicken und **Eigenschaften** auswählen.Wählen Sie im Dropdownfeld **Zielframework** den Eintrag **.NET Framework 4.5** aus.Das Festlegen des Zielframeworks für ein VB\-Projekt weicht etwas davon ab. Klicken Sie im Eigenschaftendialogfelds des GettingStartedHost\-Projekts links im Bildschirm auf die Registerkarte **Kompilieren**, und klicken Sie dann unten links im Dialogfeld auf die Schaltfläche **Erweiterte Kompilierungsoptionen**.Wählen Sie im Dropdownfeld **Zielframework**den Eintrag **.NET Framework 4.5** aus.  
  
     Das Festlegen des Zielframeworks führt dazu, dass die Projektmappe von [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] neu geladen wird. Klicken Sie auf **OK**, wenn Sie dazu aufgefordert werden.  
  
3.  Fügen Sie dem GettingStartedHost\-Projekt einen Verweis auf das GettingStartedLib\-Projekt hinzu, indem Sie im Projektmappen\-Explorer auf den Ordner **Verweise** unterhalb des GettingStartedHost\-Projekt klicken, und wählen Sie **Verweis hinzufügen** aus.Wählen Sie im Dialogfeld **Verweis hinzufügen** links im Dialogfeld **Projektmappe hinzufügen** und im mittleren Abschnitt des Dialogfelds "GettingStartedLib" aus, und klicken Sie auf **Hinzufügen**.Dadurch werden die in GettingStartedLib definierten Typen für das GettingStartedHost\-Projekt verfügbar.  
  
4.  Fügen Sie dem GettingStartedHost\-Projekt einen Verweis auf System.ServiceModel hinzu, indem Sie im Projektmappen\-Explorer mit der rechten Maustaste auf den Ordner **Verweis** unter dem GettingStartedHost\-Projekt klicken, und wählen Sie **Verweis hinzufügen** aus.Wählen Sie im Dialogfeld **Verweis hinzufügen** links im Dialogfeld **Framework** aus.Geben Sie im Textfeld **Assemblys suchen**`System.ServiceModel` ein.Wählen Sie im mittleren Abschnitt des Dialogfelds **System.ServiceModel** aus, und klicken Sie auf die Schaltfläche **Hinzufügen** und auf die Schaltfläche **Schließen**.Speichern Sie die Projektmappe, indem Sie unterhalb des Hauptmenüs auf die Schaltfläche **Alle speichern** klicken.  
  
### So hosten Sie den Dienst  
  
-   Öffnen Sie die Datei Program.cs oder Module.vb, und geben Sie den folgenden Code ein:  
  
    ```  
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
  
    ```  
    ‘Module1.vb  
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
  
    1.  Schritt 1: Erstellt eine Instanz der URI\-Klasse, die die Basisadresse des Diensts enthält.Dienste werden über eine URL identifiziert, die eine Basisadresse und einen optionalen URI enthält.Die Basisadresse wird wie folgt formatiert: transport\]:\/\/\[machine\-name oder domain\]\[:optional port \#\]\/\[optional URI segment\]Die Basisadresse für den Rechnerdienst verwendet den HTTP\-Transport, localhost, Port 8000 und das URI\-Segment “GettingStarted”  
  
    2.  Schritt 2: Erstellt eine Instanz der <xref:System.ServiceModel.ServicHost>\-Klasse zum Hosten des Diensts.Der Konstruktor akzeptiert zwei Parameter, den Typ der Klasse, die den Dienstvertrag implementiert, und die Basisadresse des Diensts.  
  
    3.  Schritt 3: Erstellt eine neue <xref:System.ServiceModel.ServiceEndpoint>\-Instanz.Ein Dienstendpunkt setzt sich aus einer Adresse, einer Bindung und einem Dienstvertrag zusammen.Der <xref:System.ServiceModel.ServiceEndpoint>\-Konstruktor akzeptiert daher den Schnittstellentyp des Dienstvertrags, eine Bindung und eine Adresse.Der Dienstvertrag ist `ICalculator`, den Sie im Diensttyp definiert und implementiert haben.Die in diesem Beispiel verwendete Bindung ist <xref:System.ServiceModel.WSHttpBinding>. Dies ist eine integrierte Bindung, die für die Verbindung mit Endpunkten verwendet wird, die den WS\-\*\-Spezifikationen entsprechen.Weitere Informationen zu WCF\-Bindungen finden Sie unter [WCF\-Bindungsübersicht](../../../docs/framework/wcf/bindings-overview.md).Die Adresse wird an die Basisadresse angefügt, um den Endpunkt zu identifizieren.Die Adresse, die in diesem Code angegeben wird, ist "Calculator". Daher ist die vollqualifizierte Adresse für den Endpunkt `“http://localhost:8000/GettingStartedService/Calculator”`.  
  
        > [!IMPORTANT]
        >  Das Hinzufügen eines Dienstendpunkts ist optional, wenn .NET Framework 4 oder höher verwendet wird.Wenn im Code oder in der Konfiguration keine Endpunkte hinzugefügt wurden, fügt WCF in diesen Versionen einen Standardendpunkt für jede Kombination aus Basisadresse und Vertrag hinzu, die vom Dienst implementiert wurden.Weitere Informationen zu Standardendpunkten finden Sie unter [Angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
    4.  Schritt 4: Aktiviert den Metadatenaustausch.Clients verwenden den Metadatenaustausch, um Proxys zu generieren, die zum Aufrufen von Dienstvorgänge verwendet werden.Zum Aktivieren von Metadatenaustausch erstellen Sie eine <xref:System.ServiceModel.Description.ServiceMetadataBehavior>\-Instanz, legen Sie deren Eigenschaft auf <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> ist `true` fest und fügen das Verhalten der <xref:System.ServiceModel.ServiceHost.Behaviors%2A>\-Auflistung der <xref:System.ServiceModel.ServiceHost> \-Instanz hinzu.  
  
    5.  Schritt 5: Öffnet den <xref:System.ServiceModel.ServiceHost>, um auf eingehende Nachrichten zu lauschen.Der Code wartet darauf, dass der Benutzer die EINGABETASTE drückt.Wenn dies nicht erfolgt, wird die App sofort geschlossen und der Dienst heruntergefahren. Beachten Sie auch, dass ein try\/catch\-Block verwendet wird.Nachdem <xref:System.ServiceModel.ServiceHost> instanziiert wurde, wird der gesamte Code in einen try\/catch\-Block platziert.Weitere Informationen zum sicheren Abfangen von Ausnahmen, die von <xref:System.ServiceModel.ServiceHost> ausgelöst werden, finden Sie unter [Vermeiden von Problemen mit der Using\-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)  
  
### So überprüfen Sie, ob der Dienst funktioniert  
  
1.  Führen Sie die GettingStartedHost\-Konsolenanwendung aus [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] heraus aus.Beim Ausführen unter [!INCLUDE[wv](../../../includes/wv-md.md)] und höher muss der Dienst mit Administratorrechten ausgeführt werden.Da [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] mit Administratorrechten ausgeführt wurde, wird auch GettingStartedHost mit Administratorrechten ausgeführt.Sie können auch eine neue Eingabeaufforderung mit Administratorrechten starten und "service.exe" damit ausführen.  
  
2.  Öffnen Sie Internet Explorer, und navigieren Sie unter `http://localhost:8000/GettingStarted/CalculatorService` zur Debuggingseite des Diensts.  
  
## Beispiel  
 Das folgende Beispiel enthält den Dienstvertrag und die Implementierung aus den vorangegangenen Schritten im Lernprogramm und hostet den Dienst in einer Konsolenanwendung.  
  
 Zur Kompilierung mit einem Befehlszeilencompiler kompilieren Sie IService1.cs und Service2.cs in eine Klassenbibliothek, die auf `System.ServiceModel.dll` verweist.Und kompilieren Sie Program.cs in eine Konsolenanwendung.  
  
```  
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
  
```  
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
  
```  
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
  
```  
‘IService1.vb  
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
  
```  
‘Service1.vb  
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
  
```  
‘Module1.vb  
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
>  Dienste wie dieser müssen dazu berechtigt sein, zu belauschende HTTP\-Adressen auf dem Computer zu registrieren.Administratorkonten verfügen über diese Berechtigung, anderen Konten muss diese Berechtigung für HTTP\-Namespaces gewährt werden.[!INCLUDE[crabout](../../../includes/crabout-md.md)] dazu, wie Namespacereservierungen konfiguriert werden, finden Sie unter [Konfigurieren von HTTP und HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).Wird der Dienst unter [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] ausgeführt, muss "service.exe" über Administratorrechte verfügen.  
  
 Der Dienst wird nun ausgeführt.Fahren Sie mit [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md) fort.Informationen zur Problembehandlung finden Sie unter [Problembehandlung für das Lernprogramm "Erste Schritte"](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).  
  
## Siehe auch  
 [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)