---
title: Übersicht über die Endpunkterstellung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- endpoints [WCF], overview
ms.assetid: f4dce0fb-6f54-47e6-8054-86d7f574b91c
ms.openlocfilehash: 0b0c22737e9407ebe2cb56c15fb7ff75d16b50a4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040306"
---
# <a name="endpoint-creation-overview"></a>Übersicht über die Endpunkterstellung

Die gesamte Kommunikation mit einem Windows Communication Foundation (WCF)-Dienst erfolgt über die *Endpunkte* des Dienstanbieter. Endpunkte ermöglichen Clients den Zugriff auf die Funktionen, die von einem WCF-Dienst angeboten werden. In diesem Abschnitt wird die Struktur eines Endpunkts beschrieben und dargestellt, wie ein Endpunkt in einer Konfiguration oder im Code definiert wird.

## <a name="the-structure-of-an-endpoint"></a>Die Struktur eines Endpunkts

Jeder Endpunkt beinhaltet eine Adresse, die angibt, wo sich der Endpunkt befindet, eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann und einen Vertrag angibt, der die verfügbaren Methoden identifiziert.

- **Adresse**. Die Adresse gewährleistet eine eindeutige Identifizierung des Endpunkts und teilt potenziellen Consumern den Standort des Diensts mit. Er wird im WCF-Objektmodell durch die <xref:System.ServiceModel.EndpointAddress> Adresse dargestellt, die eine Uniform Resource Identifier (URI) und Adress Eigenschaften enthält, die eine Identität, einige Web Services Description Language (WSDL)-Elemente und eine Auflistung Optionaler Elemente enthalten. Kopf. Die optionalen Header stellen zusätzliche ausführliche Adressinformationen bereit, um den Endpunkt zu identifizieren oder damit zu interagieren. Weitere Informationen finden Sie unter [Angeben einer Endpunkt Adresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md).

- **Bindung**. Die Bindung gibt an, wie eine Kommunikation mit dem Endpunkt stattfindet. Die Bindung gibt an, wie der Endpunkt mit der Außenwelt kommuniziert (einschließlich des zu verwendenden Transportprotokolls, beispielsweise TCP oder HTTP), welche Codierung für die Nachrichten zu verwenden ist (beispielsweise Text- oder Binärcodierung) und welche Sicherheitsanforderungen erforderlich sind (beispielsweise Secure Sockets Layer [SSL] oder SOAP-Nachrichtensicherheit). Weitere Informationen finden Sie unter [Verwenden von Bindungen zum Konfigurieren von Diensten und Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).

- **Dienstvertrag**. Der Dienstvertrag zeigt, welche Funktionen der Endpunkt dem Client zur Verfügung stellt. In einem Vertrag wird Folgendes angegeben: die Vorgänge, die ein Client aufrufen kann, die Form der Nachricht und der Typ der Eingabeparameter oder die Daten, die zum Aufrufen des Vorgangs erforderlich sind, sowie die Art der Verarbeitung oder die Antwortnachricht, die der Client erwarten kann. Drei grundlegende Vertragstypen entsprechen grundlegenden Nachrichtenaustauschmustern: Datagramm (unidirektional), Anforderung/Antwort und Duplex (bidirektional). Für den Dienstvertrag können zudem Daten- und Nachrichtenverträge verwendet werden, um beim Zugriff bestimmte Datentypen und Nachrichtenformate zu fordern. Weitere Informationen zum Definieren eines Dienstvertrags finden Sie unter Entwerfen von [Dienstverträgen](../../../docs/framework/wcf/designing-service-contracts.md). Ein Client kann ggf. auch dazu aufgefordert werden, einen vom Dienst definierten Vertrag zu implementieren (wird als Rückrufvertrag bezeichnet), um vom Dienst in einem Duplexnachrichten-Austauschmuster Nachrichten zu empfangen. Weitere Informationen finden Sie unter [Duplex Dienste](../../../docs/framework/wcf/feature-details/duplex-services.md).

Der Endpunkt für einen Dienst kann entweder verbindlich durch Verwenden von Code oder deklarativ durch Konfiguration angegeben werden. Wenn keine Endpunkte angegeben sind, stellt die Runtime Standardendpunkte bereit, indem ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag, der vom Dienst implementiert wird, hinzugefügt wird. Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden. Im Allgemeinen ist es praktischer, Dienstendpunkte nicht mit Code, sondern mit Konfiguration zu definieren. Werden die Bindung und die Adressinformationen nicht in den Code integriert, ist eine Änderung ohne Neukompilierung und erneute Bereitstellung der Anwendung möglich.

> [!NOTE]
> Beim Hinzufügen eines Dienstendpunkts, der einen Identitätswechsel ausführt, muss entweder eine der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methoden oder die <xref:System.ServiceModel.Description.ContractDescription.GetContract%28System.Type%2CSystem.Type%29>-Methode verwendet werden, um den Vertrag ordnungsgemäß in ein neues <xref:System.ServiceModel.Description.ServiceDescription>-Objekt zu laden.

## <a name="defining-endpoints-in-code"></a>Definieren von Endpunkten in Code

Im folgenden Beispiel wird die Angabe eines Endpunkts in Code veranschaulicht:

- Definieren Sie einen Vertrag für `IEcho` einen Diensttyp, der den Namen einer Person akzeptiert und die Antwort "Hello \<Name >!" erhält.

- Implementieren Sie einen `Echo`-Dienst des Typs, der durch den `IEcho`-Vertrag definiert wird.

- Geben Sie eine Endpunkt Adresse `http://localhost:8000/Echo` von für den Dienst an.

- Konfigurieren Sie den `Echo`-Dienst mithilfe einer <xref:System.ServiceModel.WSHttpBinding>-Bindung.

```csharp
namespace Echo
{
   // Define the contract for the IEcho service
   [ServiceContract]
   public interface IEcho
   {
       [OperationContract]
       String Hello(string name)
   }

   // Create an Echo service that implements IEcho contract
   class Echo : IEcho
   {
      public string Hello(string name)
      {
         return "Hello" + name + "!";
      }
      public static void Main ()
      {
          //Specify the base address for Echo service.
          Uri echoUri = new Uri("http://localhost:8000/");

          //Create a ServiceHost for the Echo service.
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);

          // Use a predefined WSHttpBinding to configure the service.
          WSHttpBinding binding = new WSHttpBinding();

          // Add the endpoint for this service to the service host.
          serviceHost.AddServiceEndpoint(
             typeof(IEcho),
             binding,
             echoUri
           );

          // Open the service host to run it.
          serviceHost.Open();
     }
  }
}
```

```vb
' Define the contract for the IEcho service
    <ServiceContract()> _
    Public Interface IEcho
        <OperationContract()> _
        Function Hello(ByVal name As String) As String
    End Interface

' Create an Echo service that implements IEcho contract
    Public Class Echo
        Implements IEcho
        Public Function Hello(ByVal name As String) As String _
 Implements ICalculator.Hello
            Dim result As String = "Hello" + name + "!"
            Return result
        End Function

' Specify the base address for Echo service.
Dim echoUri As Uri = New Uri("http://localhost:8000/")

' Create a ServiceHost for the Echo service.
Dim svcHost As ServiceHost = New ServiceHost(GetType(HelloWorld), echoUri)

' Use a predefined WSHttpBinding to configure the service.
Dim binding As New WSHttpBinding()

' Add the endpoint for this service to the service host.
serviceHost.AddServiceEndpoint(GetType(IEcho), binding, echoUri)

' Open the service host to run it.
serviceHost.Open()
```

> [!NOTE]
> Der Diensthost wird mit einer Basisadresse erstellt. Anschließend wird der Rest der Adresse relativ zur Basisadresse als Teil eines Endpunkts angegeben. Diese Partitionierung der Adresse ermöglicht die einfachere Definition von mehreren Endpunkten für Dienste an einem Host.

> [!NOTE]
> Eigenschaften von <xref:System.ServiceModel.Description.ServiceDescription> in der Dienstanwendung dürfen nicht im Anschluss an die <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A>-Methode auf <xref:System.ServiceModel.ServiceHostBase> geändert werden. Einige Member, wie die <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft und die `AddServiceEndpoint`-Methoden auf <xref:System.ServiceModel.ServiceHostBase> und <xref:System.ServiceModel.ServiceHost>, lösen eine Ausnahme aus, wenn eine Änderung über diesen Punkt hinaus stattfindet. Andere Member können geändert werden, wobei das Ergebnis jedoch nicht definiert ist.
>
> Ähnlich verhält es sich mit den <xref:System.ServiceModel.Description.ServiceEndpoint>-Werten, die auf dem Client nach dem Aufruf von <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> auf <xref:System.ServiceModel.ChannelFactory> nicht geändert werden dürfen. Die <xref:System.ServiceModel.ChannelFactory.Credentials%2A>-Eigenschaft löst eine Ausnahme aus, wenn sie über diesen Punkt hinaus geändert wird. Die anderen Clientbeschreibungswerte können ohne Fehler geändert werden, aber das Ergebnis ist nicht definiert.
>
> Sowohl für den Dienst als auch den Client wird empfohlen, die Beschreibung vor dem Aufruf von <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> zu ändern.

## <a name="defining-endpoints-in-configuration"></a>Definieren von Endpunkten in der Konfiguration

Beim Erstellen einer Anwendung sollen dem Administrator, der die Anwendung bereitstellt, Entscheidungen häufig verzögert mitgeteilt werden. Beispielsweise weiß man häufig nicht, welche Dienstadresse (URI) verwendet wird. Anstatt eine Adresse fest zu programmieren, sollte diese Aufgabe einem Administrator nach dem Erstellen eines Diensts übergeben werden. Diese Flexibilität wird durch Konfiguration ermöglicht. Weitere Informationen finden Sie unter [Konfigurieren von Diensten](../../../docs/framework/wcf/configuring-services.md).

> [!NOTE]
> Verwenden Sie [das Service Model Metadata Utility-Tool (Svcutil. exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit der `/config:`Option *Dateiname*`[,`Dateiname `]` , um schnell Konfigurationsdateien zu erstellen.

## <a name="using-default-endpoints"></a>Verwenden von Standardendpunkten

Wenn im Code oder in der Konfiguration keine Endpunkte angegeben sind, stellt die Runtime Standardendpunkte bereit, indem ein Standardendpunkt für alle Basisadressen in jedem Dienstvertrag, der vom Dienst implementiert wird, hinzugefügt wird. Die Basisadresse kann im Code oder in der Konfiguration angegeben werden, und die Standardendpunkte werden hinzugefügt, wenn <xref:System.ServiceModel.ICommunicationObject.Open> auf dem <xref:System.ServiceModel.ServiceHost> aufgerufen wird. Dieses Beispiel entspricht dem Beispiel aus dem vorherigen Abschnitt. Da aber keine Endpunkte angegeben sind, werden die Standardendpunkte hinzugefügt.

```csharp
namespace Echo
{
   // Define the contract for the IEcho service
   [ServiceContract]
   public interface IEcho
   {
       [OperationContract]
       String Hello(string name)
   }

   // Create an Echo service that implements IEcho contract
   public class Echo : IEcho
   {
      public string Hello(string name)
      {
         return "Hello" + name + "!";
      }
      public static void Main ()
      {
          //Specify the base address for Echo service.
          Uri echoUri = new Uri("http://localhost:8000/");

          //Create a ServiceHost for the Echo service.
          ServiceHost serviceHost = new ServiceHost(typeof(Echo),echoUri);

          // Open the service host to run it. Default endpoints
          // are added when the service is opened.
          serviceHost.Open();
     }
  }
}
```

```vb
' Define the contract for the IEcho service
    <ServiceContract()> _
    Public Interface IEcho
        <OperationContract()> _
        Function Hello(ByVal name As String) As String
    End Interface

' Create an Echo service that implements IEcho contract
    Public Class Echo
        Implements IEcho
        Public Function Hello(ByVal name As String) As String _
 Implements ICalculator.Hello
            Dim result As String = "Hello" + name + "!"
            Return result
        End Function

' Specify the base address for Echo service.
Dim echoUri As Uri = New Uri("http://localhost:8000/")

' Open the service host to run it. Default endpoints
' are added when the service is opened.
serviceHost.Open()
```

 Wenn Endpunkte explizit bereitgestellt werden, können die Standardpunkte dennoch hinzugefügt werden, indem <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints%2A> auf dem <xref:System.ServiceModel.ServiceHost> aufgerufen wird, bevor <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> aufgerufen wird. Weitere Informationen zu Standard Endpunkten finden Sie unter [vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).

## <a name="see-also"></a>Siehe auch

- [Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md)
