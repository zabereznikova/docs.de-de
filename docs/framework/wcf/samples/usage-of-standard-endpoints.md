---
title: "Verwendung von Standardendpunkten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Verwendung von Standardendpunkten
In diesem Beispiel wird veranschaulicht, wie Standardendpunkte in Dienstkonfigurationsdateien verwendet werden.  Ein Standardendpunkt ermöglicht es dem Benutzer, einfacher Endpunktdefinitionen anzugeben, indem mit einer einzigen Eigenschaft eine Kombination aus Adresse, Bindung und Vertrag beschrieben und diesen Elementen zusätzliche Eigenschaften zugeordnet werden.  In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Standardendpunkt definiert und implementiert wird und wie bestimmte Eigenschaften im Endpunkt definiert werden.  
  
## Beispieldetails  
 Dienstendpunkte können mit der Bereitstellung von drei Parametern angegeben werden: Adresse, Bindung und Vertrag.  Andere Parameter, die angegeben werden können, sind etwa Verhaltenskonfiguration, Header, Überwachungs\-URI usw.  In einigen Fällen verfügen einige oder alle der Adressen, Bindungen und Verträge über Werte, die nicht veränderlich sind.  Aus diesem Grund können Standardendpunkte verwendet werden.  Einige Beispiele für solche Endpunkte enthalten Metadatenaustausch\-Endpunkte und Suchendpunkte.  Standardendpunkte erhöhen außerdem die Benutzerfreundlichkeit, da sie die Konfiguration von Dienstendpunkten ermöglichen, ohne dass bestimmte Informationen bereitgestellt oder eigene Standardendpunkte erstellt werden müssen, etwa zur Verbesserung der Nutzbarkeit durch die Angabe eines entsprechenden Satzes von Standardwerten, um die Komplexität der Konfigurationsdateien zu reduzieren.  
  
 Dieses Beispiel besteht aus zwei Projekten: dem Dienst, der zwei Standardendpunkte definiert, und dem Client, der mit dem Dienst kommuniziert.  Die Methode zur Definition der Standardendpunkte für den Dienst in der Konfigurationsdatei wird im folgenden Beispiel erläutert.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <endpointExtensions>  
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">  
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />  
        <endpoint kind="mexEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <standardEndpoints>  
      <customEndpoint>  
        <standardEndpoint property="True" />  
      </customEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
</configuration>  
  
```  
  
 Der erste für den Dienst definierte Endpunkt ist ein `customEndpoint`, dessen Definition im Abschnitt `<standardEndpoints>` angezeigt wird. Dabei enthält die `property`\-Eigenschaft den Wert `true`.  Hierbei handelt es sich um einen Endpunkt, der mit einer neuen Eigenschaft angepasst wird.  Der zweite Endpunkt entspricht einem Metadatenendpunkt, in dem die Werte für die Adresse, die Bindung und den Vertrag fest angegeben sind.  
  
 Für die Definition des Standardendpunkt\-Elements muss eine Klasse, die sich von `StandardEndpointElement` ableitet, erstellt werden.  Im Fall dieses Beispiels wurde die `CustomEndpointElement`\-Klasse wie im folgenden Beispiel dargestellt definiert.  
  
```csharp  
public class CustomEndpointElement : StandardEndpointElement  
{  
    public bool Property  
    {  
        get { return (bool)base["property"]; }  
        set { base["property"] = value; }  
    }  
  
    protected override ConfigurationPropertyCollection Properties  
    {  
        get  
        {  
            ConfigurationPropertyCollection properties = base.Properties;  
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));  
            return properties;  
        }  
    }  
  
    protected override Type EndpointType  
    {  
        get { return typeof(CustomEndpoint); }  
    }  
  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)  
    {  
        return new CustomEndpoint();  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
}  
  
```  
  
 Es wird ein `CustomEndpoint`\-Objekt in der `CreateServiceEndpoint`\-Funktion erstellt.  Die entsprechende Definition wird im folgenden Beispiel dargestellt.  
  
```  
public class CustomEndpoint : ServiceEndpoint  
    {  
        public CustomEndpoint()  
            : this(string.Empty)  
        {  
        }  
  
        public CustomEndpoint(string address)  
            : this(address, ContractDescription.GetContract(typeof(ICalculator)))  
        {  
        }  
  
        public CustomEndpoint(string address, ContractDescription contract)  
            : base(contract)  
        {  
            this.Binding = new BasicHttpBinding();  
            this.IsSystemEndpoint = false;  
        }  
  
        public bool Property  
        {  
            get;  
            set;  
        }  
    }  
  
```  
  
 Für die Kommunikation zwischen Dienst und Client wird im Client ein Dienstverweis zum Dienst erstellt.  Wenn das Beispiel erstellt und ausgeführt wurde, wird der Dienst ausgeführt, und der Client kommuniziert damit.  Beachten Sie, dass der Dienstverweis stets aktualisiert werden muss, wenn es eine Änderung im Dienst gibt.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die Datei StandardEndpoints.sln.  
  
2.  Aktivieren Sie mehrere Projekte, um zu starten.  
  
    1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Projektmappe Standardendpunkte, und wählen Sie dann die Option **Eigenschaften** aus.  
  
    2.  Wählen Sie unter **Allgemeine Eigenschaften** die Option **Startprojekt** aus, und klicken Sie dann auf **Mehrere Startprojekte**.  
  
    3.  Verschieben Sie das Dienstprojekt an den Anfang der Liste, wobei als **Aktion** die Option **Start** angegeben ist.  
  
    4.  Verschieben Sie das Clientprojekt an die Stelle nach dem Dienstprojekt, wobei auch hier für **Aktion** die Option **Start** angegeben ist.  
  
         Dadurch wird angegeben, dass das Clientprojekt nach dem Dienstprojekt ausgeführt werden soll.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!NOTE]
>  Wenn diese Schritte nicht funktionieren, stellen Sie mithilfe der folgenden Schritte sicher, dass die Umgebung ordnungsgemäß eingerichtet wurde.  
>   
>  1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
> 2.  Befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Projektmappe zu erstellen.  
> 3.  Wenn Sie das Beispiel in einer Konfiguration mit einem Computer oder mehreren Computern ausführen möchten, folgen Sie den unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`  
  
## Siehe auch