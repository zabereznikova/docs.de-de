---
title: "Zugreifen auf Dienste mithilfe eines WCF-Clients | Microsoft Docs"
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
  - "Clients [WCF], Verarbeiten von Diensten"
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Zugreifen auf Dienste mithilfe eines WCF-Clients
Nach dem Erstellen eines Diensts ist der nächste Schritt das Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientproxys.  Eine Clientanwendung verwendet den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientproxy, um mit dem Dienst zu kommunizieren.  Clientanwendungen importieren normalerweise Metadaten eines Dienstes zum Generieren von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientcode, mit dem der Dienst aufgerufen werden kann.  
  
 Nachfolgend werden die grundlegenden Schritte zum Erstellen eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients aufgeführt:  
  
1.  Kompilieren Sie den Dienstcode.  
  
2.  Generieren Sie den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientproxy.  
  
3.  Instanziieren Sie den WCF\-Clientproxy.  
  
 Der WCF\-Clientproxy kann manuell generiert werden, indem Sie das Service Model Metadata Utility\-Tool \(**SvcUtil.exe**\) ausführen. Weitere Informationen finden Sie unter [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  Der WCF\-Clientproxy kann auch mithilfe der Funktion **Dienstverweis hinzufügen** in Visual Studio generiert werden.  Um den WCF\-Clientproxy mithilfe einer dieser Methoden zu generieren, muss der Dienst ausgeführt werden.  Wenn es sich um einen selbst gehosteten Dienst handelt, müssen Sie den Host ausführen.  Wenn der Dienst in IIS\/WAS gehostet wird, ist kein weiterer Schritt erforderlich.  
  
## ServiceModel Metadata Utility Tool  
 Das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) ist ein Befehlszeilentool zum Generieren von Code aus Metadaten.  Die folgende Verwendung ist ein Beispiel für einen grundlegenden Svcutil.exe\-Befehl.  
  
```  
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
```  
  
 Alternativ können Sie Svcutil.exe mit WSDL \(Web Services Description Language\) und XSD \(XML Schema Definition Language\)\-Dateien im Dateisystem verwenden.  
  
```  
Svcutil.exe <list of WSDL and XSD files on file system>  
```  
  
 Das Ergebnis ist ein Code, der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientcode enthält, mit dem die Clientanwendung den Dienst aufrufen kann.  
  
 Sie können das Tool auch zum Generieren von Konfigurationsdateien verwenden.  
  
```  
Svcutil.exe <file1 [,file2]>  
```  
  
 Wenn nur ein Dateiname angegeben wird, ist das der Name der Ausgabedatei.  Wenn zwei Dateinamen angegeben werden, ist die erste Datei eine Eingabekonfigurationsdatei, deren Inhalt mit der generierten Konfiguration zusammengeführt und in die zweite Datei geschrieben wird.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] zur Konfiguration finden Sie unter [Konfigurieren von Bindungen für Dienste](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).  
  
> [!IMPORTANT]
>  Nicht gesicherte Metadatenanforderungen stellen genau wie nicht gesicherte Netzwerkanforderungen ein gewisses Risiko dar: Wenn Sie sich nicht sicher sind, ob der Endpunkt, mit dem Sie kommunizieren, der vorgegebenen Identität entspricht, stammen die abgerufenen Informationen unter Umständen von einem bösartigen Dienst.  
  
## "Dienstverweis hinzufügen" in Visual Studio  
 Klicken Sie, während der Dienst ausgeführt wird, mit der rechten Maustaste auf das Projekt, in dem der WCF\-Clientproxy enthalten ist, und wählen Sie **Dienstverweis hinzufügen** aus.  Geben Sie im Dialogfeld **Dienstverweis hinzufügen** die URL des Diensts ein, den Sie aufrufen möchten, und klicken Sie auf die Schaltfläche **Gehe zu**.  Das Dialogfeld zeigt eine Liste der Dienste an, die unter der Adresse verfügbar sind.  Doppelklicken Sie auf den Dienst, um die verfügbaren Verträge und Vorgänge anzuzeigen, geben Sie einen Namespace für den generierten Code an, und klicken Sie auf die Schaltfläche **OK**.  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein für einen Dienst erstellter Dienstvertrag gezeigt.  
  
```csharp  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    // Other methods are not shown here.  
}  
```  
  
```vb  
' Define a service contract.  
<ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")> _  
Public Interface ICalculator  
    <OperationContract()>  _  
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double   
    ' Other methods are not shown here.  
End Interface   
```  
  
 Das ServiceModel Metadata Utility\-Tool und **Dienstverweis hinzufügen** in Visual Studio generieren die folgende [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientklasse.  Die Klasse erbt von der generischen <xref:System.ServiceModel.ClientBase%601>\-Klasse und implementiert die `ICalculator`\-Schnittstelle.  Das Tool generiert auch die `ICalculator`\-Schnittstelle \(wird hier nicht gezeigt\).  
  
```csharp  
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator  
{  
    public CalculatorClient(){}  
  
    public CalculatorClient(string configurationName) :   
            base(configurationName)  
    {}  
  
    public CalculatorClient(System.ServiceModel.Binding binding) :   
            base(binding)  
    {}  
  
    public CalculatorClient(System.ServiceModel.EndpointAddress address,  
    System.ServiceModel.Binding binding) :   
            base(address, binding)  
    {}  
  
    public double Add(double n1, double n2)  
    {  
        return base.InnerChannel.Add(n1, n2);  
    }  
}  
  
```  
  
```vb  
Partial Public Class CalculatorClient  
    Inherits System.ServiceModel.ClientBase(Of ICalculator)  
    Implements ICalculator  
  
    Public Sub New()  
        MyBase.New  
    End Sub  
  
    Public Sub New(ByVal configurationName As String)  
        MyBase.New(configurationName)  
    End Sub  
  
    Public Sub New(ByVal binding As System.ServiceModel.Binding)  
        MyBase.New(binding)  
    End Sub  
  
    Public Sub New(ByVal address As _  
    System.ServiceModel.EndpointAddress, _  
    ByVal binding As System.ServiceModel.Binding)  
        MyBase.New(address, binding)  
    End Sub  
  
    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As _  
    Double Implements ICalculator.Add  
        Return MyBase.InnerChannel.Add(n1, n2)  
    End Function   
End Class  
  
```  
  
## Verwenden des WCF\-Clients  
 Erstellen Sie zum Verwenden des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients eine Instanz des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients, und rufen Sie dann seine Methoden auf, wie im folgenden Code gezeigt.  
  
```csharp  
// Create a client object with the given client endpoint configuration.  
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = calcClient.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
```  
  
```vb  
' Create a client object with the given client endpoint configuration.  
Dim calcClient As CalculatorClient = _  
New CalculatorClient("CalculatorEndpoint")  
  
' Call the Add service operation.  
Dim value1 As Double = 100.00D  
Dim value2 As Double = 15.99D  
Dim result As Double = calcClient.Add(value1, value2)  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)  
  
```  
  
## Debuggen der von einem Client ausgelösten Ausnahmen  
 Viele von einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client ausgelöste Ausnahmen werden von einer Ausnahme des Diensts verursacht.  Im Folgenden finden Sie einige Beispiele:  
  
-   <xref:System.Net.Sockets.SocketException>: Vom Remotehost wurde die Schließung einer bestehenden Verbindung erzwungen.  
  
-   <xref:System.ServiceModel.CommunicationException>: Die zugrunde liegende Verbindung wurde unerwartet geschlossen.  
  
-   <xref:System.ServiceModel.CommunicationObjectAbortedException>: Die Socketverbindung wurde abgebrochen.  Mögliche Ursache: Ein Fehler beim Verarbeiten der Nachricht, eine Zeitüberschreitung durch den Remotehost beim Empfang oder ein Problem mit einer zugrunde liegenden Netzwerkressource.  
  
 Tritt eine Ausnahme dieses Typs auf, aktivieren Sie die Ablaufverfolgung auf der Dienstseite, und ermitteln Sie die dort aufgetretene Ausnahme.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] zur Ablaufverfolgung finden Sie unter [Ablaufverfolgung](../../../docs/framework/wcf/diagnostics/tracing/index.md) sowie unter [Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern](../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).  
  
## Siehe auch  
 [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)   
 [Vorgehensweise: Asynchrones Aufrufen von Dienstvorgängen](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)   
 [Vorgehensweise: Zugreifen auf Dienste mit unidirektionalen und Anforderung\-Antwort\-Verträgen](../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)   
 [Vorgehensweise: Zugriff auf einen WSE3.0\-Dienst](../../../docs/framework/wcf/feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)   
 [Grundlagen des generierten Clientcodes](../../../docs/framework/wcf/feature-details/understanding-generated-client-code.md)   
 [Vorgehensweise: Verbessern der Startzeit von WCF\-Clientanwendungen mit dem XmlSerializer](../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)   
 [Angeben des Clientlaufzeitverhaltens](../../../docs/framework/wcf/specifying-client-run-time-behavior.md)   
 [Konfigurieren von Clientverhalten](../../../docs/framework/wcf/configuring-client-behaviors.md)