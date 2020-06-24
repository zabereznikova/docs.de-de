---
title: 'Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei'
description: Erfahren Sie, wie Sie Metadaten für einen WCF-Dienst mithilfe einer Konfigurationsdatei veröffentlichen. Durch die Veröffentlichung können Clients diese Metadaten mithilfe einer Get-oder HTTP/GET-Anforderung erhalten.
ms.date: 03/30/2017
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
ms.openlocfilehash: d5d425be7f02a204476c4f6e81441aca9ea39fcc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246817"
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a>Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei
Dies ist eines von zwei Vorgehensweisen, in denen das Veröffentlichen von Metadaten für einen Windows Communication Foundation (WCF)-Dienst veranschaulicht wird. Es gibt zwei Möglichkeiten, wie ein Dienst Metadaten veröffentlichen kann: mit einer Konfigurationsdatei und mit Code. In diesem Thema wird das Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei dargestellt.  
  
> [!CAUTION]
> In diesem Thema wird das Veröffentlichen von Metadaten auf unsichere Weise dargestellt. Jeder Client kann Metadaten vom Dienst abrufen. Wenn Sie möchten, dass Ihr Dienst Metadaten auf sichere Weise veröffentlicht, finden Sie weitere Informationen unter [Benutzerdefinierter sicherer Metadatenendpunkt](../samples/custom-secure-metadata-endpoint.md).  
  
 Weitere Informationen zum Veröffentlichen von Metadaten im Code finden Sie unter Gewusst [wie: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code](how-to-publish-metadata-for-a-service-using-code.md). Die Veröffentlichung von Metadaten ermöglicht Clients, Metadaten über eine WS-Transfer-GET-Anforderung oder eine HTTP/GET-Anforderung mithilfe einer `?wsdl`-Abfragezeichenfolge abzurufen. Um sicherzustellen, dass der Code funktioniert, erstellen Sie einen einfachen WCF-Dienst. Der Einfachheit halber wird im folgenden Code ein grundlegender, selbst gehosteter Dienst bereitgestellt.  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
 Dieser Dienst ist ein selbst gehosteter Dienst, der mit einer Konfigurationsdatei konfiguriert wird. Die folgende Konfigurationsdatei dient als Ausgangspunkt.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Metadata.Example.SimpleService">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
      </service>  
    </services>  
    <behaviors>  
  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a>So veröffentlichen Sie Metadaten für einen WCF-Dienst mithilfe einer Konfigurationsdatei  
  
1. Erstellen Sie in der App.config-Datei, nachdem Sie das `</services>`-Element geschlossen haben, ein `<behaviors>`-Element.  

2. Fügen Sie im `<behaviors>`-Element ein `<serviceBehaviors>`-Element hinzu.  

3. Fügen Sie ein `<behavior>`-Element zum `<serviceBehaviors>`-Element hinzu, und geben Sie einen Wert für das `name`-Attribut des `<behavior>`-Elements an.  

4. Fügen Sie dem `<serviceMetadata>`-Element ein `<behavior>`-Element hinzu. Legen Sie das `httpGetEnabled`-Attribut auf `true` und das `policyVersion`-Attribut auf Policy15 fest. `httpGetEnabled` ermöglicht es dem Dienst, auf die Metadatenanforderungen einer HTTP GET-Anforderung zu antworten. `policyVersion` teilt dem Dienst mit, bei der Erstellung von Metadaten der WS-Richtlinie 1.5 zu folgen.  

5. Fügen Sie dem `behaviorConfiguration`-Element ein `<service>`-Attribut hinzu, und geben Sie das `name`-Attribut des in Schritt&#160;1 hinzugefügten `<behavior>`-Elements an, wie im folgenden Codebeispiel gezeigt.  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
        ...  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy15" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
6. Fügen Sie ein oder mehrere `<endpoint>`-Elemente hinzu, wobei der Vertrag auf `IMetadataExchange` festgelegt ist, wie im folgenden Codebeispiel gezeigt.  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    ```  
  
7. Legen Sie für die im vorherigen Schritt hinzugefügten Metadatenendpunkte das `binding`-Attribut auf einen der folgenden Werte fest:  
  
    - `mexHttpBinding` für HTTP-Veröffentlichung.  
  
    - `mexHttpsBinding` für HTTPS-Veröffentlichung.  
  
    - `mexNamedPipeBinding` für benannte Pipeveröffentlichung.  
  
    - `mexTcpBinding` für TCP-Veröffentlichung.  
  
8. Legen Sie die Adressen für die in einem vorherigen Schritt hinzugefügten Metadatenendpunkte auf Folgendes fest:  
  
    - Eine leere Zeichenfolge, um die Basisadresse der Hostanwendung als Veröffentlichungspunkt zu verwenden, wenn die Basisadresse gleich der Metadatenbindung ist.  
  
    - Eine relative Adresse, wenn die Hostanwendung über eine Basisadresse verfügt.  
  
    - Eine absolute Adresse.  
  
9. Erstellen Sie die Konsolenanwendung, und führen Sie sie aus.  
  
10. Navigieren Sie mit Internet Explorer zur Basisadresse des Dienstanbieter ( `http://localhost:8001/MetadataSample` in diesem Beispiel), und vergewissern Sie sich, dass die Metadatenveröffentlichung aktiviert ist. Wenn nicht, wird oben auf der Ergebnisseite folgende Meldung angezeigt: "Das Veröffentlichen von Metadaten für diesen Dienst ist derzeit deaktiviert."  
  
### <a name="to-use-default-endpoints"></a>So verwenden Sie Standardendpunkte  
  
1. Um Metadaten für einen Dienst zu konfigurieren, der Standardendpunkte verwendet, geben Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in der Konfigurationsdatei fest, so wie im vorherigen Beispiel. Legen Sie jedoch keine Endpunkte fest. Die Konfigurationsdatei sieht dann wie folgt aus.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="SimpleServiceBehavior">  
              <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     Da für den Dienst das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> mit `httpGetEnabled` auf `true` festgelegt wurde, ist für den Dienst die Veröffentlichung von Metadaten aktiviert. Und da keine Endpunkte explizit hinzugefügt wurden, fügt die Runtime die Standardendpunkte hinzu. Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Implementierung eines einfachen WCF-Dienstanbieter und der Konfigurationsdatei veranschaulicht, die Metadaten für den Dienst veröffentlicht.  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../how-to-host-a-wcf-service-in-a-managed-application.md)
- [Selbst gehostete Dienste](../samples/self-host.md)
- [Übersicht über die Metadatenarchitektur](metadata-architecture-overview.md)
- [Verwenden von Metadaten](using-metadata.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code](how-to-publish-metadata-for-a-service-using-code.md)
