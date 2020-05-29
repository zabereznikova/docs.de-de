---
title: Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung
ms.date: 03/30/2017
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
ms.openlocfilehash: c5a2145a6d7b631a666df94eb0c1fc53cbc3c55f
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202265"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a>Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung

Windows Communication Foundation (WCF) verfügt über eine Option für den ASP.NET-Kompatibilitätsmodus, mit der WCF-Anwendungen wie ASP.NET-Webdienste programmiert und konfiguriert werden können und deren Verhalten imitiert wird. In den folgenden Abschnitten werden ASP.NET-Webdienste und WCF basierend auf dem, was zum Entwickeln von Anwendungen mit beiden Technologien erforderlich ist, verglichen.

## <a name="data-representation"></a>Datendarstellung

Die Entwicklung eines Webdiensts mit ASP.NET beginnt normalerweise mit der Definition aller komplexen Datentypen, die vom Dienst verwendet werden sollen. ASP.NET verwendet <xref:System.Xml.Serialization.XmlSerializer>, um Daten, die von .NET Framework-Typen dargestellt werden, zur Übertragung an oder von einem Dienst in XML zu übersetzen und als XML empfangene Daten in .NET Framework-Objekte zu übersetzen. Die Definition der komplexen Datentypen, die ein ASP.NET-Dienst verwenden soll, erfordert die Definition von .NET Framework-Klassen, die <xref:System.Xml.Serialization.XmlSerializer> in und aus XML serialisieren kann. Derartige Klassen können manuell geschrieben oder aus Definitionen der Typen in XML-Schema generiert werden. Dies geschieht mithilfe von xsd.exe, dem Befehlszeilen-Unterstützungsprogramm für XML-Schemas/-Datentypen.

Nachfolgend finden Sie eine Auflistung wesentlicher Probleme, die beim Definieren von .NET Framework-Klassen auftreten können, die <xref:System.Xml.Serialization.XmlSerializer> in und aus XML serialisieren kann:

- Nur die öffentlichen Felder und Eigenschaften von .NET Framework-Objekten werden in XML übersetzt.

- Instanzen der Auflistungsklassen können nur in XML serialisiert werden, wenn die Klassen entweder die <xref:System.Collections.IEnumerable>-Schnittstelle oder die <xref:System.Collections.ICollection>-Schnittstelle implementieren.

- Klassen, die die <xref:System.Collections.IDictionary>-Schnittstelle, zum Beispiel <xref:System.Collections.Hashtable>, implementieren, können nicht in XML serialisiert werden.

- Die zahlreichen Attributtypen im <xref:System.Xml.Serialization>-Namespace können einer .NET Framework-Klasse und deren Membern hinzugefügt werden, um die Darstellung der Klasseninstanzen in XML zu steuern.

Die Entwicklung von WCF-Anwendungen beginnt in der Regel auch mit der Definition komplexer Typen. WCF kann verwendet werden, um dieselben .NET Framework Typen wie ASP.NET-Webdienste zu verwenden.

Die WCF <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> können .NET Framework Typen hinzugefügt werden, um anzugeben, dass Instanzen des Typs in XML serialisiert werden sollen und welche speziellen Felder oder Eigenschaften des Typs serialisiert werden sollen, wie im folgenden Beispielcode gezeigt.

```csharp
//Example One:
[DataContract]
public class LineItem
{
    [DataMember]
    public string ItemNumber;
    [DataMember]
    public decimal Quantity;
    [DataMember]
    public decimal UnitPrice;
}

//Example Two:
public class LineItem
{
    [DataMember]
    private string itemNumber;
    [DataMember]
    private decimal quantity;
    [DataMember]
    private decimal unitPrice;

    public string ItemNumber
    {
      get
      {
          return this.itemNumber;
      }

      set
      {
          this.itemNumber = value;
      }
    }

    public decimal Quantity
    {
        get
        {
            return this.quantity;
        }

        set
        {
            this.quantity = value;
        }
    }

    public decimal UnitPrice
    {
      get
      {
          return this.unitPrice;
      }

      set
      {
          this.unitPrice = value;
      }
    }
}

//Example Three:
public class LineItem
{
     private string itemNumber;
     private decimal quantity;
     private decimal unitPrice;

     [DataMember]
     public string ItemNumber
     {
       get
       {
          return this.itemNumber;
       }

       set
       {
           this.itemNumber = value;
       }
     }

     [DataMember]
     public decimal Quantity
     {
          get
          {
              return this.quantity;
          }

          set
          {
             this.quantity = value;
          }
     }

     [DataMember]
     public decimal UnitPrice
     {
          get
          {
              return this.unitPrice;
          }

          set
          {
              this.unitPrice = value;
          }
     }
}
```

<xref:System.Runtime.Serialization.DataContractAttribute> gibt an, dass null oder mehr Felder oder Eigenschaften eines Typs serialisiert werden sollen. <xref:System.Runtime.Serialization.DataMemberAttribute> gibt dagegen an, dass ein bestimmtes Feld oder eine Eigenschaft serialisiert werden soll. <xref:System.Runtime.Serialization.DataContractAttribute> kann für eine Klasse oder Struktur übernommen werden. <xref:System.Runtime.Serialization.DataMemberAttribute> kann auf ein Feld oder eine Eigenschaft angewendet werden, und die Felder und Eigenschaften, für die das Attribut übernommen wird, können entweder öffentlich oder privat sein. Instanzen von Typen, auf die <xref:System.Runtime.Serialization.DataContractAttribute> angewendet wird, werden in WCF als Datenverträge bezeichnet. Sie werden mit <xref:System.Runtime.Serialization.DataContractSerializer> in XML serialisiert.

Nachfolgend finden Sie eine Liste der wichtigen Unterschiede zwischen der Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> und der Verwendung von <xref:System.Xml.Serialization.XmlSerializer> sowie der verschiedenen Attribute des <xref:System.Xml.Serialization>-Namespace.

- <xref:System.Xml.Serialization.XmlSerializer> und die Attribute des <xref:System.Xml.Serialization>-Namespace ermöglichen das Zuordnen von .NET Framework-Typen zu jedem gültigen Typ, der in XML-Schema definiert ist. Dadurch ermöglichen sie eine außerordentlich genaue Steuerung der Darstellung eines Typs in XML. <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> bieten nur sehr wenige Möglichkeiten zur Steuerung der Darstellung eines Typs in XML. Angegeben werden können nur die Namespaces und Namen, die zum Darstellen des Typs und der Felder oder Eigenschaften in XML verwendet werden, sowie die Reihenfolge, in der die Felder und Eigenschaften in XML angezeigt werden:

  ```csharp
  [DataContract(
  Namespace="urn:Contoso:2006:January:29",
  Name="LineItem")]
  public class LineItem
  {
        [DataMember(Name="ItemNumber",IsRequired=true,Order=0)]
        public string itemNumber;
        [DataMember(Name="Quantity",IsRequired=false,Order = 1)]
        public decimal quantity;
        [DataMember(Name="Price",IsRequired=false,Order = 2)]
        public decimal unitPrice;
  }
  ```

  Alle anderen Aspekte der Struktur von XML, mit der der .NET-Typ dargestellt wird, werden von <xref:System.Runtime.Serialization.DataContractSerializer> bestimmt.

- Dadurch, dass keine umfassenden Möglichkeiten zur Steuerung der Darstellung eines Typs in XML gewährt werden, wird der Serialisierungsprozess für <xref:System.Runtime.Serialization.DataContractSerializer> leicht vorhersehbar und die Optimierung dadurch vereinfacht. Ein praktischer Vorteil des Entwurfs von <xref:System.Runtime.Serialization.DataContractSerializer> ist eine um etwa zehn Prozent höhere Leistung.

- Die Attribute für die Verwendung mit <xref:System.Xml.Serialization.XmlSerializer> geben nicht an, welche Felder oder Eigenschaften des Typs in XML serialisiert werden, wohingegen <xref:System.Runtime.Serialization.DataMemberAttribute> für die Verwendung mit <xref:System.Runtime.Serialization.DataContractSerializer> explizit die zu serialisierenden Felder oder Eigenschaften anzeigt. Daher handelt es sich bei den Datenverträgen um explizite Verträge über die Struktur der Daten, die von einer Anwendung gesendet und empfangen werden.

- <xref:System.Xml.Serialization.XmlSerializer> kann nur die öffentlichen Member eines .NET-Objekts in XML übersetzen, und <xref:System.Runtime.Serialization.DataContractSerializer> kann die Member eines Objekts unabhängig von den Zugriffsmodifizierern dieser Member in XML übersetzen.

- Da die nicht öffentlichen Member der Typen in XML serialisiert werden können, gelten für <xref:System.Runtime.Serialization.DataContractSerializer> weniger Einschränkungen bezüglich der Vielfalt der .NET-Typen, die in XML serialisiert werden können. Insbesondere ist eine Übersetzung in XML-Typen wie <xref:System.Collections.Hashtable> möglich, mit denen die <xref:System.Collections.IDictionary>-Schnittstelle implementiert wird. <xref:System.Runtime.Serialization.DataContractSerializer> ist mit einer weitaus höheren Wahrscheinlichkeit in der Lage, die Instanzen eines beliebigen zuvor vorhandenen .NET-Typs in XML zu serialisieren, ohne entweder die Definition des Typs ändern oder einen Wrapper dafür entwickeln zu müssen.

- Da <xref:System.Runtime.Serialization.DataContractSerializer> auf die nicht öffentlichen Member eines Typs zugreifen kann, ist im Gegensatz zu <xref:System.Xml.Serialization.XmlSerializer> zudem volle Vertrauenswürdigkeit erforderlich. Die voll vertrauenswürdige Code Zugriffsberechtigung bietet vollständigen Zugriff auf alle Ressourcen auf einem Computer, auf den über die Anmelde Informationen zugegriffen werden kann, unter denen der Code ausgeführt wird. Diese Option sollte mit Bedacht verwendet werden, da vollständig vertrauenswürdiger Code auf alle Ressourcen auf Ihrem Computer zugreift.

- <xref:System.Runtime.Serialization.DataContractSerializer> bietet einige Unterstützung für Versionsverwaltung:

  - <xref:System.Runtime.Serialization.DataMemberAttribute> verfügt über eine <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>-Eigenschaft, der der Wert false für Member zugewiesen werden kann, die neuen Versionen eines Datenvertrags hinzugefügt werden, die in früheren Versionen noch nicht vorhanden waren. Dadurch wird Anwendungen mit der neueren Version des Vertrags das Verarbeiten früherer Versionen ermöglicht.

  - Wenn mit einem Datenvertrag die <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle implementiert wird, kann <xref:System.Runtime.Serialization.DataContractSerializer> das Übergeben von Membern gestattet werden, die in neueren Versionen eines Datenvertrags durch Anwendungen mit älteren Versionen des Vertrags definiert sind.

Ungeachtet aller Unterschiede ist das XML, in das <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, semantisch identisch mit dem XML, in das <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, dass der Namespace für das XML explizit definiert ist. Die folgende Klasse, die über Attribute für die Verwendung mit beiden serialisierungssoren verfügt, wird von und von in semantisch identisches XML übersetzt <xref:System.Xml.Serialization.XmlSerializer> <xref:System.Runtime.Serialization.DataContractAttribute> :

```csharp
[Serializable]
[XmlRoot(Namespace="urn:Contoso:2006:January:29")]
[DataContract(Namespace="urn:Contoso:2006:January:29")]
public class LineItem
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}
```

Das Windows Software Development Kit (SDK) umfasst ein Befehlszeilen Tool namens [Service Model Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Wie das Tool XSD. exe, das mit ASP.NET-Webdiensten verwendet wird, kann Svcutil. exe Definitionen von .NET-Datentypen aus dem XML-Schema generieren. Bei den Typen handelt es sich um Datenverträge, sofern <xref:System.Runtime.Serialization.DataContractSerializer> XML in dem vom XML-Schema definierten Format ausgeben kann; andernfalls sind sie für die Serialisierung mithilfe von <xref:System.Xml.Serialization.XmlSerializer> vorgesehen. Svcutil. exe kann auch ein XML-Schema aus Daten Verträgen mithilfe seines `dataContractOnly` Schalters generieren.

> [!NOTE]
> Obwohl die ASP.NET-Webdienste den verwenden <xref:System.Xml.Serialization.XmlSerializer> , und der WCF ASP.NET-Kompatibilitätsmodus bewirkt, dass WCF-Dienste das Verhalten von ASP.NET-Webdiensten imitieren, schränkt die ASP.net-Kompatibilitäts Option nicht auf die Verwendung von ein <xref:System.Xml.Serialization.XmlSerializer> . <xref:System.Runtime.Serialization.DataContractSerializer> kann nach wie vor verwendet werden, während die Dienste im ASP.NET-Kompatibilitätsmodus ausgeführt werden.

## <a name="service-development"></a>Dienstentwicklung

Soll ein Dienst mithilfe von ASP.NET entwickelt werden, wird einer Klasse üblicherweise das <xref:System.Web.Services.WebService>-Attribut hinzugefügt, und <xref:System.Web.Services.WebMethodAttribute> wird einer beliebigen Methode dieser Klasse, bei denen es sich um Vorgänge des Diensts handeln soll, hinzugefügt:

```csharp
[WebService]
public class Service : T:System.Web.Services.WebService
{
    [WebMethod]
    public string Echo(string input)
    {
       return input;
    }
}
```

Seit ASP.NET 2.0 steht eine Option zur Verfügung, mit der der <xref:System.Web.Services.WebService> und das <xref:System.Web.Services.WebMethodAttribute> des Attributs einer Schnittstelle und nicht einer Klasse hinzugefügt werden und eine Klasse zum Implementieren der Schnittstelle geschrieben wird:

```csharp
[WebService]
public interface IEcho
{
    [WebMethod]
    string Echo(string input);
}

public class Service : IEcho
{

   public string Echo(string input)
   {
        return input;
    }
}
```

Die Verwendung dieser Option wird empfohlen, da die Schnittstelle mit dem <xref:System.Web.Services.WebService>-Attribut einen Vertrag für die vom Dienst ausgeführten Vorgänge darstellt. Dieser Vertrag kann erneut mit verschiedenen Klassen verwendet werden, die denselben Vertrag möglicherweise auf unterschiedliche Art und Weise implementieren.

Ein WCF-Dienst wird bereitgestellt, indem ein oder mehrere WCF-Endpunkte definiert werden. Ein Endpunkt wird durch eine Adresse, eine Bindung und einen Dienstvertrag definiert. Die Adresse wird am Standort des Diensts definiert. Die Bindung gibt an, wie eine Kommunikation mit dem Dienst stattfindet. Mit dem Dienstvertrag werden die Vorgänge, die der Dienst ausführen kann, definiert.

Der Dienstvertrag wird normalerweise zuerst definiert, indem einer Schnittstelle <xref:System.ServiceModel.ServiceContractAttribute> und <xref:System.ServiceModel.OperationContractAttribute> hinzugefügt werden:

```csharp
[ServiceContract]
public interface IEcho
{
     [OperationContract]
     string Echo(string input);
}
```

Der <xref:System.ServiceModel.ServiceContractAttribute> gibt an, dass die-Schnittstelle einen WCF-Dienstvertrag definiert, und <xref:System.ServiceModel.OperationContractAttribute> gibt an, welche, sofern vorhanden, der Methoden der-Schnittstelle Vorgänge des Dienstvertrags definieren.

Nach der Definition eines Dienstvertrags wird dieser in einer Klasse implementiert, indem die Klasse die Schnittstelle implementiert, nach der der Dienstvertrag definiert ist:

```csharp
public class Service : IEcho
{
    public string Echo(string input)
    {
       return input;
    }
}
```

Eine Klasse, die einen Dienstvertrag implementiert, wird in WCF als Diensttyp bezeichnet.

Der nächste Schritt besteht in der Zuordnung einer Adresse und einer Bindung zu einem Diensttyp. Dies erfolgt in der Regel in einer Konfigurationsdatei, entweder durch direktes Bearbeiten der Datei oder durch Verwendung eines mit WCF bereitgestellten Konfigurations-Editors. Hier sehen Sie ein Beispiel einer Konfigurationsdatei.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
     <system.serviceModel>
      <services>
      <service name="Service ">
       <endpoint
        address="EchoService"
        binding="basicHttpBinding"
        contract="IEchoService "/>
      </service>
      </services>
     </system.serviceModel>
</configuration>
```

Die Bindung gibt den Satz der Protokolle für die Kommunikation mit der Anwendung an. In der folgenden Tabelle sind die vom System bereitgestellten Bindungen, die allgemeine Optionen darstellen, aufgeführt.

|Name|Zweck|
|----------|-------------|
|BasicHttpBinding|Interoperabilität mit Webdiensten und Clients, die WS-BasicProfile 1.1 und Basic Security Profile 1.0 unterstützen.|
|WSHttpBinding|Interoperabilität mit Webdiensten und Clients, die die Protokolle vom Typ WS-* über HTTP unterstützen.|
|WSDualHttpBinding|Duplex-HTTP-Kommunikation, bei der der Empfänger einer ursprünglichen Nachricht nicht direkt dem ursprünglichen Absender antwortet, jedoch eine beliebige Anzahl von Antworten über einen bestimmten Zeitraum übertragen kann, indem er HTTP in Übereinstimmung mit WS-*-Protokollen verwendet.|
|WSFederationBinding|HTTP-Kommunikation, in der der Zugriff auf Ressourcen eines Diensts auf Basis der Anmeldeinformationen gesteuert wird, die von einem explizit identifizierten Anmeldeinformationsanbieter ausgestellt werden.|
|NetTcpBinding|Sichere, zuverlässige, leistungsstarke Kommunikation zwischen WCF-Software Entitäten in einem Netzwerk.|
|NetNamedPipeBinding|Sichere, zuverlässige und leistungsstarke Kommunikation zwischen WCF-Software Entitäten auf dem gleichen Computer.|
|NetMsmqBinding|Kommunikation zwischen WCF-Software Entitäten mithilfe von MSMQ.|
|MsmqIntegrationBinding|Kommunikation zwischen einer WCF-Software Entität und einer anderen Software Entität unter Verwendung von MSMQ.|
|NetPeerTcpBinding|Kommunikation zwischen WCF-Software Entitäten mithilfe von Windows-Peer-zu-Peer-Netzwerken.|

Mit der vom System bereitgestellten Bindung, <xref:System.ServiceModel.BasicHttpBinding>, wird der Satz der von ASP.NET-Webdiensten unterstützten Protokolle integriert.

Benutzerdefinierte Bindungen für WCF-Anwendungen können problemlos als Auflistungen der Bindungs Element Klassen definiert werden, die von WCF zum Implementieren einzelner Protokolle verwendet werden. Neue Bindungselemente können zur Darstellung zusätzlicher Protokolle geschrieben werden.

Das interne Verhalten der Diensttypen kann mithilfe der Eigenschaften einer Klassenfamilie mit der Bezeichnung Verhaltensweisen angepasst werden. Hier wird mit der <xref:System.ServiceModel.ServiceBehaviorAttribute>-Klasse angegeben, dass der Diensttyp Multithread sein soll.

```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple)]
public class DerivativesCalculatorServiceType: IDerivativesCalculator
```

Einige Verhaltensweisen wie zum Beispiel <xref:System.ServiceModel.ServiceBehaviorAttribute> sind Attribute. Andere Verhaltensweisen (diejenigen mit den Eigenschaften, die normalerweise von Administratoren festgelegt werden) können in der Konfiguration einer Anwendung geändert werden.

In Programmierdiensttypen wird häufig die <xref:System.ServiceModel.OperationContext>-Klasse verwendet. Die statische <xref:System.ServiceModel.OperationContext.Current%2A>-Eigenschaft bietet Zugriff auf Informationen zu dem Kontext, in dem ein Vorgang ausgeführt wird. <xref:System.ServiceModel.OperationContext> ist für die Klassen <xref:System.Web.HttpContext> und <xref:System.EnterpriseServices.ContextUtil> ähnlich.

## <a name="hosting"></a>Hosting

ASP.NET-Webdienste werden in eine Klassenbibliothekassembly kompiliert. Eine als Dienstdatei bezeichnete Datei wird bereitgestellt, die die Erweiterung ASMX aufweist und eine `@ WebService`-Anweisung zur Identifizierung der Klasse mit dem Code für den Dienst und die Assembly beinhaltet, in der sich die Klasse befindet.

`<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>`

Die Dienstdatei wird in das Stammverzeichnis einer ASP.NET-Anwendung in Internetinformationsdienste (IIS) und die Assembly in das \bin-Unterverzeichnis dieses Anwendungsstammverzeichnisses kopiert. Die Anwendung ist anschließend durch Angabe der URL (Uniform Resource Locator) der Dienstdatei im Stammverzeichnis der Anwendung verfügbar.

WCF-Dienste können problemlos innerhalb von IIS 5,1 oder 6,0, dem Windows Process Activation Service (was) gehostet werden, der als Teil von IIS 7,0 und innerhalb einer beliebigen .NET-Anwendung bereitgestellt wird. Soll ein Dienst in IIS 5.1 oder 6.0 gehostet werden, muss HTTP als Kommunikationstransportprotokoll verwendet werden.

Soll ein Dienst innerhalb von IIS 5, 6.0 oder WAS gehostet werden, gehen Sie folgendermaßen vor:

1. Kompilieren Sie den Diensttyp in eine Klassenbibliothekassembly.

2. Erstellen Sie eine Dienstdatei mit einer SVC-Erweiterung und einer `@ ServiceHost`-Anweisung zur Identifizierung des Diensttyps:

    `<%@ServiceHost language="c#" Service="MyService" %>`

3. Kopieren Sie die Dienstdatei in ein virtuelles Verzeichnis und die Assembly in das \bin-Unterverzeichnis des virtuellen Verzeichnisses.

4. Kopieren Sie die Konfigurationsdatei in das virtuelle Verzeichnis, und nennen Sie die Datei Web.config.

Die Anwendung ist anschließend durch Angabe der URL der Dienstdatei im Stammverzeichnis der Anwendung verfügbar.

Um einen WCF-Dienst in einer .NET-Anwendung zu hosten, kompilieren Sie den Diensttyp in eine Klassenbibliotheksassembly, auf die von der Anwendung verwiesen wird, und Programmieren Sie die Anwendung, um den Dienst <xref:System.ServiceModel.ServiceHost> mithilfe der Nachfolgend finden Sie ein Beispiel für die erforderliche grundlegende Programmierung:

```csharp
string httpBaseAddress = "http://www.contoso.com:8000/";
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";

Uri httpBaseAddressUri = new Uri(httpBaseAddress);
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);

Uri[] baseAddresses = new Uri[] {
 httpBaseAddressUri,
 tcpBaseAddressUri};

using(ServiceHost host = new ServiceHost(
typeof(Service), //"Service" is the name of the service type baseAddresses))
{
     host.Open();

     […] //Wait to receive messages
     host.Close();
}
```

In diesem Beispiel erfahren Sie, wie Adressen für mindestens ein Transportprotokoll bei der Erstellung von <xref:System.ServiceModel.ServiceHost> angegeben werden. Diese Adressen werden als Basisadressen bezeichnet.

Die Adresse, die für einen beliebigen Endpunkt eines WCF-Diensts bereitgestellt wird, ist eine Adresse relativ zur Basisadresse des Endpunkts des Endpunkts. Der Host kann über eine Basisadresse für jedes Kommunikationstransportprotokoll verfügen. In der Beispielkonfiguration in der vorangegangenen Konfigurationsdatei verwendet die für den Endpunkt gewählte <xref:System.ServiceModel.BasicHttpBinding> HTTP als Transportprotokoll, sodass die Adresse des Endpunkts (`EchoService`) relativ zur HTTP-Basisadresse des Hosts ist. Im Fall des Hosts im vorherigen Beispiel lautet die HTTP-Basisadresse `http://www.contoso.com:8000/` . Für einen in IIS oder WAS gehosteten Dienst ist die Basisadresse die URL der Dienstdatei des Diensts.

Nur in IIS oder was gehostete Dienste, die ausschließlich mit HTTP als Transportprotokoll konfiguriert sind, können zur Verwendung der WCF ASP.NET Compatibility Mode-Option verwendet werden. Das Aktivieren dieser Option erfordert die folgenden Schritte.

1. Der Programmierer muss das <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>-Attribut dem Diensttyp hinzufügen und angeben, dass der ASP.NET-Kompatibilitätsmodus entweder zulässig oder erforderlich ist.

    ```csharp
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(
          RequirementsMode=AspNetCompatibilityRequirementsMode.Require)]
    public class DerivativesCalculatorServiceType: IDerivativesCalculator
    ```

2. Der Administrator muss die Anwendung so konfigurieren, dass der ASP.NET-Kompatibilitätsmodus verwendet wird.

    ```xml
    <configuration>
         <system.serviceModel>
          <services>
          […]
          </services>
          <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
        </system.serviceModel>
    </configuration>
    ```

    WCF-Anwendungen können auch so konfiguriert werden, dass Sie ASMX als Erweiterung für Ihre Dienst Dateien anstelle von SVC verwenden.

    ```xml
    <system.web>
         <compilation>
          <compilation debug="true">
          <buildProviders>
           <remove extension=".asmx"/>
           <add extension=".asmx"
            type="System.ServiceModel.ServiceBuildProvider,
            System.ServiceModel,
            Version=3.0.0.0,
            Culture=neutral,
            PublicKeyToken=b77a5c561934e089" />
          </buildProviders>
          </compilation>
         </compilation>
    </system.web>
    ```

    Diese Option kann Ihnen dabei ersparen, Clients zu ändern, die für die Verwendung der URLs von ASMX-Dienst Dateien konfiguriert sind, wenn Sie einen Dienst für die Verwendung von WCF ändern.

## <a name="client-development"></a>Cliententwicklung

Clients für ASP.NET-Webdienste werden mithilfe des Befehlszeilentools WSDL.exe generiert, das die URL der ASMX-Datei als Eingabe bereitstellt. Das entsprechende von WCF bereitgestellte Tool ist das [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Es generiert ein Codemodul mit der Definition des Dienstvertrags und der Definition einer WCF-Client Klasse. Es generiert auch eine Konfigurationsdatei mit der Adresse und der Bindung des Diensts.

Beim Programmieren eines Clients eines Remotediensts ist es in der Regel empfehlenswert, gemäß einem asynchronen Muster zu programmieren. Der vom Tool WSDL.exe generierte Code beinhaltet standardmäßig sowohl ein synchrones als auch ein asynchrones Muster. Der durch das [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generierte Code kann für beide Muster bereitgestellt werden. Standardmäßig wird das synchrone Muster bereitgestellt. Bei Ausführung des Tools mit `/async` wird durch den generierten Code das asynchrone Muster bereitgestellt.

Es gibt keine Garantie, dass Namen in den von ASP generierten WCF-Client Klassen vorhanden sind. Das Tool "WSDL. exe" von NET entspricht standardmäßig den Namen in WCF-Client Klassen, die vom Tool "Svcutil. exe" generiert wurden. Insbesondere wird den Namen der Eigenschaften von Klassen, die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden müssen, standardmäßig die Suffixeigenschaft im vom Tool Svcutil.exe generierten Code zugewiesen. Beim Tool WSDL.exe ist dies nicht der Fall.

## <a name="message-representation"></a>Nachrichtendarstellung

Die Header der SOAP-Nachrichten, die von ASP.NET-Webdiensten gesendet und empfangen werden, können angepasst werden. Eine Klasse wird von <xref:System.Web.Services.Protocols.SoapHeader> abgeleitet, um die Struktur des Headers zu definieren. Anschließend wird mit <xref:System.Web.Services.Protocols.SoapHeaderAttribute> das Vorhandensein des Headers angezeigt.

```csharp
public class SomeProtocol : SoapHeader
{
     public long CurrentValue;
     public long Total;
}

[WebService]
public interface IEcho
{
     SomeProtocol ProtocolHeader
     {
      get;
     set;
     }

     [WebMethod]
     [SoapHeader("ProtocolHeader")]
     string PlaceOrders(PurchaseOrderType order);
}

public class Service: WebService, IEcho
{
     private SomeProtocol protocolHeader;

     public SomeProtocol ProtocolHeader
     {
         get
         {
              return this.protocolHeader;
         }

         set
         {
              this.protocolHeader = value;
         }
     }

     string PlaceOrders(PurchaseOrderType order)
     {
         long currentValue = this.protocolHeader.CurrentValue;
     }
}
```

Der WCF stellt die Attribute,, und bereit, <xref:System.ServiceModel.MessageContractAttribute> <xref:System.ServiceModel.MessageHeaderAttribute> <xref:System.ServiceModel.MessageBodyMemberAttribute> um die Struktur der SOAP-Nachrichten zu beschreiben, die von einem Dienst gesendet und empfangen werden.

```csharp
[DataContract]
public class SomeProtocol
{
     [DataMember]
     public long CurrentValue;
     [DataMember]
     public long Total;
}

[DataContract]
public class Item
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}

[MessageContract]
public class ItemMessage
{
     [MessageHeader]
     public SomeProtocol ProtocolHeader;
     [MessageBody]
     public Item Content;
}

[ServiceContract]
public interface IItemService
{
     [OperationContract]
     public void DeliverItem(ItemMessage itemMessage);
}
```

Diese Syntax ermöglicht eine explizite Darstellung der Nachrichtenstruktur, wohingegen die Struktur der Nachrichten vom Code eines ASP.NET-Webdiensts impliziert wird. Außerdem werden Nachrichten Header in der ASP.NET-Syntax als Eigenschaften des Dienstanbieter dargestellt, wie z. b. die- `ProtocolHeader` Eigenschaft im vorherigen Beispiel, wohingegen Sie in der WCF-Syntax genauer als Eigenschaften von Nachrichten dargestellt werden. Außerdem ermöglicht WCF, dass Nachrichten Header der Konfiguration von Endpunkten hinzugefügt werden.

```xml
<service name="Service ">
     <endpoint
      address="EchoService"
      binding="basicHttpBinding"
      contract="IEchoService ">
      <headers>
      <dsig:X509Certificate
       xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">
       ...
      </dsig:X509Certificate>
      </headers>
     </endpoint>
</service>
```

Mit dieser Option muss im Code für einen Client oder Dienst kein Verweis auf infrastrukturbezogene Protokollheader angegeben werden: Die Header werden Nachrichten ausgehend von der Konfiguration des Endpunkts hinzugefügt.

## <a name="service-description"></a>Dienstbeschreibung

Bei einer HTTP GET-Anforderung für die ASMX-Datei eines ASP.NET-Webdiensts mit der Abfrage-WSDL generiert ASP.NET zur Beschreibung des Diensts WSDL. Diese WSDL wird als Antwort auf diese Anforderung zurückgegeben.

Mit ASP.NET 2.0 kann überprüft werden, ob ein Dienst mit Basic Profile 1.1 von Web Services-Interoperability Organization (WS-I) kompatibel ist und ein Anspruch, mit dem der Dienst kompatibel ist, in WSDL eingefügt werden. Dies wird mithilfe des `ConformsTo`-Parameters und des `EmitConformanceClaims`-Parameters des <xref:System.Web.Services.WebServiceBindingAttribute>-Attributs durchgeführt.

```csharp
[WebService(Namespace = "http://tempuri.org/")]
[WebServiceBinding(
     ConformsTo = WsiProfiles.BasicProfile1_1,
     EmitConformanceClaims=true)]
public interface IEcho
```

Die WSDL, die ASP.NET für einen Dienst generiert, kann angepasst werden. Anpassungen werden durch Erstellen einer abgeleiteten Klasse von <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> vorgenommen, um der WSDL Elemente hinzuzufügen.

Wenn eine HTTP GET-Anforderung mit der Abfrage-WSDL für die SVC-Datei eines WCF-Dienstanbieter mit einem HTTP-Endpunkt ausgegeben wird, der in IIS 51, 6,0 oder was gehostet wird, antwortet WCF mit WSDL, um den Dienst zu beschreiben. Das Richten einer HTTP GET-Anforderung mit der Abfrage-WSDL an die HTTP-Basisadresse eines in einer .NET-Anwendung gehosteten Diensts hat die gleiche Auswirkung, wenn "httpGetEnabled" auf "true" festgelegt ist.

WCF antwortet jedoch auch auf WS-MetadataExchange-Anforderungen mit WSDL, die es generiert, um einen Dienst zu beschreiben. ASP.NET-Webdienste verfügen über keine integrierte Unterstützung für WS-MetadataExchange-Anforderungen.

Die WSDL, die von WCF generiert wird, kann umfassend angepasst werden. Die <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Klasse bietet einige Funktionen zum Anpassen der WSDL. WCF kann auch so konfiguriert werden, dass keine WSDL generiert wird, sondern stattdessen eine statische WSDL-Datei an einer bestimmten URL verwendet wird.

```xml
<behaviors>
     <behavior name="DescriptionBehavior">
     <metadataPublishing
      enableMetadataExchange="true"
      enableGetWsdl="true"
      enableHelpPage="true"
      metadataLocation=
      "http://localhost/DerivativesCalculatorService/Service.WSDL"/>
     </behavior>
</behaviors>
```

## <a name="exception-handling"></a>Ausnahmebehandlung

In ASP.NET-Webdiensten werden nicht behandelte Ausnahmen den Clients als SOAP-Fehler zurückgegeben. Sie können auch explizit Instanzen der <xref:System.Web.Services.Protocols.SoapException>-Klasse auslösen und eine größere Kontrolle über den Inhalt des SOAP-Fehlers erlangen, der an den Client übertragen wird.

In WCF-Diensten werden nicht behandelte Ausnahmen nicht als SOAP-Fehler an Clients zurückgegeben, um zu verhindern, dass vertrauliche Informationen durch die Ausnahmen versehentlich offengelegt werden. Mit einer Konfigurationseinstellung werden nicht behandelte Ausnahmen zu Debugging-Zwecken an Clients zurückgegeben.

Sollen SOAP-Fehler an Clients zurückgegeben werden, können Instanzen des generischen Typs (<xref:System.ServiceModel.FaultException%601>) unter Verwendung des Datenvertragstyps als generischem Typ ausgelöst werden. Sie können auch <xref:System.ServiceModel.FaultContractAttribute>-Attribute Vorgängen hinzufügen, um die Fehler anzugeben, die sich aus einem Vorgang ergeben können.

```csharp
[DataContract]
public class MathFault
{
     [DataMember]
     public string operation;
     [DataMember]
     public string problemType;
}

[ServiceContract]
public interface ICalculator
{
     [OperationContract]
     [FaultContract(typeof(MathFault))]
     int Divide(int n1, int n2);
}
```

Dies führt dazu, dass mögliche Fehler in der WSDL für den Dienst angekündigt werden und Clientprogrammierer somit vorab wissen, welche Fehler sich aus einem Vorgang ergeben können. Auf Grundlage dieser Ankündigung haben die Programmierer die Möglichkeit, geeignete catch-Anweisungen zu verfassen.

```csharp
try
{
     result = client.Divide(value1, value2);
}
catch (FaultException<MathFault> e)
{
 Console.WriteLine("FaultException<MathFault>: Math fault while doing "
  + e.Detail.operation
  + ". Problem: "
  + e.Detail.problemType);
}
```

## <a name="state-management"></a>Zustandsverwaltung

Die Klasse, mit der ein ASP.NET-Webdienst implementiert wird, wird möglicherweise von <xref:System.Web.Services.WebService> abgeleitet.

```csharp
public class Service : WebService, IEcho
{

 public string Echo(string input)
 {
  return input;
 }
}
```

In diesem Fall kann die Klasse so programmiert werden, dass sie die <xref:System.Web.Services.WebService>-Kontexteigenschaft der Basisklasse für den Zugriff auf ein <xref:System.Web.HttpContext>-Objekt verwendet. Mit dem <xref:System.Web.HttpContext>-Objekt können Anwendungszustandsinformationen durch Verwendung der Anwendungseigenschaft aktualisiert und abgerufen werden. Außerdem können Sitzungszustandsinformationen durch Verwendung der Sitzungseigenschaft aktualisiert und abgerufen werden.

ASP.NET bietet umfassende Funktionen zur Bestimmung des tatsächlichen Speicherorts der Sitzungszustandsinformationen, auf die mithilfe der Sitzungseigenschaft von <xref:System.Web.HttpContext> zugegriffen wird. Die Informationen können in Cookies, einer Datenbank, im Speicher des aktuellen Servers oder im Speicher eines festgelegten Servers gespeichert sein. Die Auswahl wird in der Konfigurationsdatei des Diensts getroffen.

WCF stellt erweiterbare Objekte für die Zustands Verwaltung bereit. Erweiterbare Objekte sind Objekte, mit denen <xref:System.ServiceModel.IExtensibleObject%601> implementiert wird. Die wichtigsten erweiterbaren Objekte sind <xref:System.ServiceModel.ServiceHostBase> und <xref:System.ServiceModel.InstanceContext>. `ServiceHostBase` ermöglicht die Beibehaltung des Zustands, auf den alle Instanzen aller Diensttypen auf demselben Host zugreifen können, während `InstanceContext` das Beibehalten des Zustands ermöglicht, auf den mit jedem Code, der in derselben Instanz eines Diensttyps ausgeführt wird, zugegriffen werden kann.

Hier verfügt der Diensttyp `TradingSystem` über einen, der <xref:System.ServiceModel.ServiceBehaviorAttribute> angibt, dass alle Aufrufe von derselben WCF-Client Instanz an dieselbe Instanz des Dienst Typs weitergeleitet werden.

```csharp
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]
public class TradingSystem: ITradingService
```

Die Klasse (`DealData`) definiert den Zustand, auf den mit jedem Code, der in derselben Instanz eines Diensttyps ausgeführt wird, zugegriffen wird.

```csharp
internal class DealData: IExtension<InstanceContext>
{
 public string DealIdentifier = null;
 public Trade[] Trades = null;
}
```

Im Code des Diensttyps, mit dem einer der Vorgänge des Dienstvertrags implementiert wird, wird ein `DealData`-Statusobjekt dem Zustand der aktuellen Instanz des Diensttyps hinzugefügt.

```csharp
string ITradingService.BeginDeal()
{
 string dealIdentifier = Guid.NewGuid().ToString();
 DealData state = new DealData(dealIdentifier);
 OperationContext.Current.InstanceContext.Extensions.Add(state);
 return dealIdentifier;
}
```

Das Statusobjekt kann anschließend mit dem Code abgerufen und geändert werden, der einen anderen Dienstvertragsvorgang implementiert.

```csharp
void ITradingService.AddTrade(Trade trade)
{
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();
 dealData.AddTrade(trade);
}
```

Während ASP.net die Kontrolle darüber bereitstellt, wo Zustandsinformationen in der <xref:System.Web.HttpContext> Klasse tatsächlich gespeichert werden, bietet WCF, zumindest in seiner ursprünglichen Version, keine Kontrolle darüber, wo erweiterbare Objekte gespeichert werden. Dies ist der beste Grund für die Auswahl des ASP.NET-Kompatibilitätsmodus für einen WCF-Dienst. Sofern eine konfigurierbare Zustandsverwaltung erforderlich ist, können Sie mit dem ASP.NET-Kompatibilitätsmodus die Funktionen der <xref:System.Web.HttpContext>-Klasse genau entsprechend ihrer Verwendung in ASP.NET nutzen und zudem den Speicherort der Zustandsinformationen konfigurieren, die mithilfe der <xref:System.Web.HttpContext>-Klasse verwaltet werden.

## <a name="security"></a>Sicherheit

Die Optionen für das Sichern der ASP.NET-Webdienste stimmen mit den Optionen für das Sichern einer beliebigen IIS-Anwendung überein. Da WCF-Anwendungen nicht nur innerhalb von IIS, sondern auch innerhalb einer ausführbaren .NET-Datei gehostet werden können, müssen die Optionen zum Sichern von WCF-Anwendungen unabhängig von den Funktionen von IIS erstellt werden. Die für ASP.NET-Webdienste bereitgestellten Funktionen sind jedoch auch für WCF-Dienste verfügbar, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden.

### <a name="security-authentication"></a>Sicherheit: Authentifizierung

IIS bietet Funktionen für die Steuerung des Zugriffs auf Anwendungen, mit denen Sie entweder anonymen Zugriff oder eine Reihe von Authentifizierungsmodi auswählen können: Windows-Authentifizierung, Hashwertauthentifizierung, Standardauthentifizierung und .NET Passport-Authentifizierung. Die Option Windows-Authentifizierung kann verwendet werden, um Zugriff auf ASP.NET-Webdienste zu steuern. Wenn WCF-Anwendungen jedoch in IIS gehostet werden, muss IIS so konfiguriert werden, dass der anonyme Zugriff auf die Anwendung zugelassen wird, damit die Authentifizierung von WCF selbst verwaltet werden kann, was die Windows-Authentifizierung unter verschiedenen anderen Optionen unterstützt. Zu den anderen integrierten Optionen zählen Benutzernamentoken, X.509-Zertifikate, SAML-Token und CardSpace-Karten, doch es können auch benutzerdefinierte Authentifizierungsmechanismen definiert werden.

### <a name="security-impersonation"></a>Sicherheit: Identitätswechsel

ASP.NET verfügt über ein Identitätselement, mit dem ein ASP.NET-Webdienst für das Durchführen von Identitätswechseln konfiguriert werden kann, und zwar für einen bestimmten Benutzer oder einen beliebigen Benutzer, für den in der aktuellen Anforderung Anmeldeinformationen angegeben werden. Dieses Element kann zum Konfigurieren des Identitäts Wechsels in WCF-Anwendungen verwendet werden, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden.

Das WCF-Konfigurationssystem stellt ein eigenes Identitätselement zum Festlegen eines bestimmten Benutzers bereit, dessen Identität angenommen werden soll. WCF-Clients und-Dienste können auch unabhängig für den Identitätswechsel konfiguriert werden. Clients können dafür konfiguriert werden, für den aktuellen Benutzer beim Übertragen von Anforderungen einen Identitätswechsel durchzuführen.

```xml
<behaviors>
     <behavior name="DerivativesCalculatorClientBehavior">
      <clientCredentials>
      <windows allowedImpersonationLevel="Impersonation"/>
      </clientCredentials>
     </behavior>
</behaviors>
```

Dienstvorgänge können dafür konfiguriert werden, einen Identitätswechsel für einen beliebigen Benutzer durchzuführen, dessen Anmeldeinformationen in der aktuellen Anforderung angegeben werden.

```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]
public void Receive(Message input)
```

### <a name="security-authorization-using-access-control-lists"></a>Sicherheit: Autorisierung mithilfe von Zugriffssteuerungslisten

Mit Zugriffssteuerungslisten (ACLs) kann der Zugriff auf ASMX-Dateien beschränkt werden. Allerdings werden ACLs in WCF. svc-Dateien ignoriert, außer im ASP.NET-Kompatibilitätsmodus.

### <a name="security-role-based-authorization"></a>Sicherheit: Rollenbasierte Autorisierung

Die Option für Windows-Authentifizierung in IIS kann zusammen mit dem von der ASP.NET-Konfigurationssprache bereitgestellten Autorisierungselement verwendet werden, um rollenbasierte Autorisierung für ASP.NET-Webdienste auf Grundlage der Windows-Gruppen, denen Benutzer zugewiesen sind, zu erleichtern. ASP.NET 2.0 verwendet einen allgemeineren rollenbasierten Autorisierungsmechanismus: Rollenanbieter.

Rollenanbieter sind Klassen, die alle eine Basisschnittstelle für die Abfrage der Rollen, denen ein Benutzer zugewiesen ist, implementieren. Allerdings können diese Informationen mit jedem Rollenanbieter von einer anderen Quelle abgerufen werden. ASP.NET 2.0 verfügt über einen Rollenanbieter zum Abrufen von Rollenzuweisungen von einer Microsoft SQL Server-Datenbank und einen weiteren Rollenanbieter zum Abrufen von Rollenzuweisungen vom Windows Server 2003-Autorisierungs-Manager.

Der Rollen Anbieter Mechanismus kann in einer beliebigen .NET-Anwendung, einschließlich einer WCF-Anwendung, tatsächlich unabhängig von ASP.NET verwendet werden. Die folgende Beispielkonfiguration für eine WCF-Anwendung zeigt, wie die Verwendung eines ASP.NET-Rollen Anbieters eine Option ist, die mithilfe von ausgewählt wird <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .

```xml
<system.serviceModel>
     <services>
         <service name="Service.ResourceAccessServiceType"
             behaviorConfiguration="ServiceBehavior">
             <endpoint
              address="ResourceAccessService"
              binding="wsHttpBinding"
              contract="Service.IResourceAccessContract"/>
         </service>
     </services>
     <behaviors>
       <behavior name="ServiceBehavior">
       <serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
      </behavior>
     </behaviors>
</system.serviceModel>
```

### <a name="security-claims-based-authorization"></a>Sicherheit: Anspruchbasierte Autorisierung

Eine der wichtigsten Innovationen von WCF ist die gründliche Unterstützung für die Autorisierungs des Zugriffs auf geschützte Ressourcen basierend auf Ansprüchen. Ansprüche bestehen beispielsweise aus einem Typ, einem Recht, einem Wert sowie einer Treiberlizenz. Ein Satz von Ansprüchen bezüglich des Trägers wird erstellt. Einer dieser Ansprüche ist das Geburtsdatum des Trägers. Der Typ des Anspruchs ist das Geburtsdatum, wohingegen der Wert des Anspruchs das Geburtsdatum des Treibers ist. Das Recht, das ein Anspruch einem Träger überträgt, gibt an, wozu der Träger den Wert des Anspruchs verwenden kann. Beim Anspruch des Treibergeburtsdatums ist das Recht der Besitz: Der Treiber besitzt dieses Geburtsdatum, kann es jedoch nicht ändern. Anspruchbasierte Autorisierung umfasst rollenbasierte Autorisierung, da Rollen ein Anspruchstyp sind.

Bei der anspruchbasierten Autorisierung wird ein Anspruchsatz mit den Zugriffsanforderungen des Vorgangs verglichen. Dabei wird der Zugriff auf den Vorgang abhängig vom Ergebnis dieses Vergleichs gewährt oder verweigert. In WCF können Sie eine Klasse angeben, die zum Ausführen der Anspruchs basierten Autorisierung verwendet werden soll, indem Sie der-Eigenschaft von einen Wert zuweisen `ServiceAuthorizationManager` <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .

```xml
<behaviors>
     <behavior name='ServiceBehavior'>
     <serviceAuthorization
     serviceAuthorizationManagerType=
                   'Service.AccessChecker, Service' />
     </behavior>
</behaviors>
```

Klassen, die zum Ausführen anspruchsbasierter Autorisierung verwendet werden, müssen von <xref:System.ServiceModel.ServiceAuthorizationManager> abgeleitet werden, der nur eine Methode zum Überschreiben besitzt (`AccessCheck()`). WCF ruft diese Methode immer dann auf, wenn ein Dienst Vorgang aufgerufen wird, und stellt ein- <xref:System.ServiceModel.OperationContext> Objekt bereit, das die Ansprüche für den Benutzer in seiner- `ServiceSecurityContext.AuthorizationContext` Eigenschaft aufweist. WCF führt die Assemblierung von Ansprüchen über den Benutzer von dem Sicherheits Token aus, das der Benutzer für die Authentifizierung bereitgestellt hat. Dadurch wird der von der Aufgabe unterlassen, festzustellen, ob diese Ansprüche für den fraglichen Vorgang ausreichen.

WCF führt die automatische assemblisierung von Ansprüchen aus jeder Art von Sicherheits Token als äußerst bedeutende Innovation aus, da der Code für die Autorisierung basierend auf den Ansprüchen vollständig unabhängig vom Authentifizierungsmechanismus ist. Im Gegensatz dazu ist die Autorisierung mit Zugriffssteuerungslisten oder Rollen in ASP.NET eng an die Windows-Authentifizierung gebunden.

### <a name="security-confidentiality"></a>Sicherheit: Vertraulichkeit

Die Vertraulichkeit von Nachrichten, die mit ASP.NET-Webdiensten ausgetauscht werden, kann auf Transportebene dadurch sichergestellt werden, dass die Anwendung in IIS für die Verwendung von Secure Hypertext Transfer Protocol (HTTPS) konfiguriert wird. Dasselbe gilt für WCF-Anwendungen, die in IIS gehostet werden. WCF-Anwendungen, die außerhalb von IIS gehostet werden, können jedoch auch für die Verwendung eines sicheren Transport Protokolls konfiguriert werden. Wichtiger ist, dass WCF-Anwendungen auch so konfiguriert werden können, dass die Nachrichten vor dem Transport mithilfe des WS-Security-Protokolls gesichert werden. Wird nur der Text einer Nachricht mithilfe von WS-Sicherheit gesichert, ist eine vertrauliche Übertragung über Vermittler möglich, bevor das endgültige Ziel erreicht wird.

## <a name="globalization"></a>Globalisierung

Die ASP.NET-Konfigurationssprache ermöglicht das Angeben der Kultur einzelner Dienste. Diese Konfigurationseinstellung wird von WCF nicht unterstützt, mit Ausnahme des ASP.NET-Kompatibilitätsmodus. Um einen WCF-Dienst zu lokalisieren, der den ASP.NET-Kompatibilitätsmodus nicht verwendet, kompilieren Sie den Diensttyp in kulturspezifische Assemblys, und verwenden Sie für jede kulturspezifische Assembly separate kulturspezifische Endpunkte.

## <a name="see-also"></a>Siehe auch

- [Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
