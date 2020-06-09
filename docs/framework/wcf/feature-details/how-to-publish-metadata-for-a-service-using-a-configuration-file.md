---
title: 'Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei'
ms.date: 03/30/2017
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
ms.openlocfilehash: 976e1e0bb2c6479f7599165a1c6fe83bae4e17c1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596980"
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a><span data-ttu-id="e43da-102">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e43da-102">How to: Publish Metadata for a Service Using a Configuration File</span></span>
<span data-ttu-id="e43da-103">Dies ist eines von zwei Vorgehensweisen, in denen das Veröffentlichen von Metadaten für einen Windows Communication Foundation (WCF)-Dienst veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="e43da-103">This is one of two how-to topics that demonstrate publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="e43da-104">Es gibt zwei Möglichkeiten, wie ein Dienst Metadaten veröffentlichen kann: mit einer Konfigurationsdatei und mit Code.</span><span class="sxs-lookup"><span data-stu-id="e43da-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="e43da-105">In diesem Thema wird das Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e43da-105">This topic shows how to publish metadata for a service using a configuration file.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="e43da-106">In diesem Thema wird das Veröffentlichen von Metadaten auf unsichere Weise dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e43da-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="e43da-107">Jeder Client kann Metadaten vom Dienst abrufen.</span><span class="sxs-lookup"><span data-stu-id="e43da-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="e43da-108">Wenn Sie möchten, dass Ihr Dienst Metadaten auf sichere Weise veröffentlicht, finden Sie weitere Informationen unter [Benutzerdefinierter sicherer Metadatenendpunkt](../samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="e43da-108">If you require your service to publish metadata in a secure manner, see [Custom Secure Metadata Endpoint](../samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="e43da-109">Weitere Informationen zum Veröffentlichen von Metadaten im Code finden Sie unter Gewusst [wie: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code](how-to-publish-metadata-for-a-service-using-code.md).</span><span class="sxs-lookup"><span data-stu-id="e43da-109">For more information about publishing metadata in code, see [How to: Publish Metadata for a Service Using Code](how-to-publish-metadata-for-a-service-using-code.md).</span></span> <span data-ttu-id="e43da-110">Die Veröffentlichung von Metadaten ermöglicht Clients, Metadaten über eine WS-Transfer-GET-Anforderung oder eine HTTP/GET-Anforderung mithilfe einer `?wsdl`-Abfragezeichenfolge abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e43da-110">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="e43da-111">Um sicherzustellen, dass der Code funktioniert, erstellen Sie einen einfachen WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="e43da-111">To be sure that the code is working, create a basic WCF service.</span></span> <span data-ttu-id="e43da-112">Der Einfachheit halber wird im folgenden Code ein grundlegender, selbst gehosteter Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e43da-112">For simplicity, a basic self-hosted service is provided in the following code.</span></span>  
  
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
  
 <span data-ttu-id="e43da-113">Dieser Dienst ist ein selbst gehosteter Dienst, der mit einer Konfigurationsdatei konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="e43da-113">This service is a self-hosted service, which is configured using a configuration file.</span></span> <span data-ttu-id="e43da-114">Die folgende Konfigurationsdatei dient als Ausgangspunkt.</span><span class="sxs-lookup"><span data-stu-id="e43da-114">The following configuration file serves as a starting point.</span></span>  
  
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
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a><span data-ttu-id="e43da-115">So veröffentlichen Sie Metadaten für einen WCF-Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e43da-115">To publish metadata for a WCF service using an application configuration file</span></span>  
  
1. <span data-ttu-id="e43da-116">Erstellen Sie in der App.config-Datei, nachdem Sie das `</services>`-Element geschlossen haben, ein `<behaviors>`-Element.</span><span class="sxs-lookup"><span data-stu-id="e43da-116">Within the App.config file, after the closing `</services>` element, create a `<behaviors>` element.</span></span>  

2. <span data-ttu-id="e43da-117">Fügen Sie im `<behaviors>`-Element ein `<serviceBehaviors>`-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="e43da-117">Within the `<behaviors>` element, add a `<serviceBehaviors>` element.</span></span>  

3. <span data-ttu-id="e43da-118">Fügen Sie ein `<behavior>`-Element zum `<serviceBehaviors>`-Element hinzu, und geben Sie einen Wert für das `name`-Attribut des `<behavior>`-Elements an.</span><span class="sxs-lookup"><span data-stu-id="e43da-118">Add a `<behavior>` element to the `<serviceBehaviors>` element and specify a value for the `name` attribute of the `<behavior>` element.</span></span>  

4. <span data-ttu-id="e43da-119">Fügen Sie dem `<serviceMetadata>`-Element ein `<behavior>`-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="e43da-119">Add a `<serviceMetadata>` element to the `<behavior>` element.</span></span> <span data-ttu-id="e43da-120">Legen Sie das `httpGetEnabled`-Attribut auf `true` und das `policyVersion`-Attribut auf Policy15 fest.</span><span class="sxs-lookup"><span data-stu-id="e43da-120">Set the `httpGetEnabled` attribute to `true` and the `policyVersion` attribute to Policy15.</span></span> <span data-ttu-id="e43da-121">`httpGetEnabled` ermöglicht es dem Dienst, auf die Metadatenanforderungen einer HTTP GET-Anforderung zu antworten.</span><span class="sxs-lookup"><span data-stu-id="e43da-121">`httpGetEnabled` allows the service to respond to metadata requests made by an HTTP GET request.</span></span> <span data-ttu-id="e43da-122">`policyVersion` teilt dem Dienst mit, bei der Erstellung von Metadaten der WS-Richtlinie 1.5 zu folgen.</span><span class="sxs-lookup"><span data-stu-id="e43da-122">`policyVersion` tells the service to conform to WS-Policy 1.5 when generating metadata.</span></span>  

5. <span data-ttu-id="e43da-123">Fügen Sie dem `behaviorConfiguration`-Element ein `<service>`-Attribut hinzu, und geben Sie das `name`-Attribut des in Schritt&#160;1 hinzugefügten `<behavior>`-Elements an, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e43da-123">Add a `behaviorConfiguration` attribute to the `<service>` element and specify the `name` attribute of the `<behavior>` element added in step 1, as shown in the following code example.</span></span>  
  
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
  
6. <span data-ttu-id="e43da-124">Fügen Sie ein oder mehrere `<endpoint>`-Elemente hinzu, wobei der Vertrag auf `IMetadataExchange` festgelegt ist, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e43da-124">Add one or more `<endpoint>` elements with the contract set to `IMetadataExchange`, as shown in the following code example.</span></span>  
  
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
  
7. <span data-ttu-id="e43da-125">Legen Sie für die im vorherigen Schritt hinzugefügten Metadatenendpunkte das `binding`-Attribut auf einen der folgenden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="e43da-125">For the metadata endpoints added in the previous step, set the `binding` attribute to one of the following:</span></span>  
  
    - <span data-ttu-id="e43da-126">`mexHttpBinding` für HTTP-Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="e43da-126">`mexHttpBinding` for HTTP publication.</span></span>  
  
    - <span data-ttu-id="e43da-127">`mexHttpsBinding` für HTTPS-Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="e43da-127">`mexHttpsBinding` for HTTPS publication.</span></span>  
  
    - <span data-ttu-id="e43da-128">`mexNamedPipeBinding` für benannte Pipeveröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="e43da-128">`mexNamedPipeBinding` for named pipe publication.</span></span>  
  
    - <span data-ttu-id="e43da-129">`mexTcpBinding` für TCP-Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="e43da-129">`mexTcpBinding` for TCP publication.</span></span>  
  
8. <span data-ttu-id="e43da-130">Legen Sie die Adressen für die in einem vorherigen Schritt hinzugefügten Metadatenendpunkte auf Folgendes fest:</span><span class="sxs-lookup"><span data-stu-id="e43da-130">For the metadata endpoints added in a previous step, set the address equal to:</span></span>  
  
    - <span data-ttu-id="e43da-131">Eine leere Zeichenfolge, um die Basisadresse der Hostanwendung als Veröffentlichungspunkt zu verwenden, wenn die Basisadresse gleich der Metadatenbindung ist.</span><span class="sxs-lookup"><span data-stu-id="e43da-131">An empty string to use the host application's base address as the publication point if the base address is the same as the metadata binding.</span></span>  
  
    - <span data-ttu-id="e43da-132">Eine relative Adresse, wenn die Hostanwendung über eine Basisadresse verfügt.</span><span class="sxs-lookup"><span data-stu-id="e43da-132">A relative address if the host application has a base address.</span></span>  
  
    - <span data-ttu-id="e43da-133">Eine absolute Adresse.</span><span class="sxs-lookup"><span data-stu-id="e43da-133">An absolute address.</span></span>  
  
9. <span data-ttu-id="e43da-134">Erstellen Sie die Konsolenanwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="e43da-134">Build and run the console application.</span></span>  
  
10. <span data-ttu-id="e43da-135">Navigieren Sie mit Internet Explorer zur Basisadresse des Dienstanbieter ( `http://localhost:8001/MetadataSample` in diesem Beispiel), und vergewissern Sie sich, dass die Metadatenveröffentlichung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e43da-135">Use Internet Explorer to browse to the base address of the service (`http://localhost:8001/MetadataSample` in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="e43da-136">Wenn nicht, wird oben auf der Ergebnisseite folgende Meldung angezeigt: "Das Veröffentlichen von Metadaten für diesen Dienst ist derzeit deaktiviert."</span><span class="sxs-lookup"><span data-stu-id="e43da-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
### <a name="to-use-default-endpoints"></a><span data-ttu-id="e43da-137">So verwenden Sie Standardendpunkte</span><span class="sxs-lookup"><span data-stu-id="e43da-137">To use default endpoints</span></span>  
  
1. <span data-ttu-id="e43da-138">Um Metadaten für einen Dienst zu konfigurieren, der Standardendpunkte verwendet, geben Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in der Konfigurationsdatei fest, so wie im vorherigen Beispiel. Legen Sie jedoch keine Endpunkte fest.</span><span class="sxs-lookup"><span data-stu-id="e43da-138">To configure metadata on a service that uses default endpoints, specify the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> in the configuration file as in the previous example, but do not specify any endpoints.</span></span> <span data-ttu-id="e43da-139">Die Konfigurationsdatei sieht dann wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="e43da-139">The configuration file would then look like this.</span></span>  
  
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
  
     <span data-ttu-id="e43da-140">Da für den Dienst das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> mit `httpGetEnabled` auf `true` festgelegt wurde, ist für den Dienst die Veröffentlichung von Metadaten aktiviert. Und da keine Endpunkte explizit hinzugefügt wurden, fügt die Runtime die Standardendpunkte hinzu.</span><span class="sxs-lookup"><span data-stu-id="e43da-140">Because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> with the `httpGetEnabled` set to `true`, the service has publishing metadata enabled, and because no endpoints were explicitly added, the runtime adds the default endpoints.</span></span> <span data-ttu-id="e43da-141">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e43da-141">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e43da-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e43da-142">Example</span></span>  
 <span data-ttu-id="e43da-143">Im folgenden Codebeispiel wird die Implementierung eines einfachen WCF-Dienstanbieter und der Konfigurationsdatei veranschaulicht, die Metadaten für den Dienst veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e43da-143">The following code example shows the implementation of a basic WCF service and the configuration file that publishes metadata for the service.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e43da-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e43da-144">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="e43da-145">Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung</span><span class="sxs-lookup"><span data-stu-id="e43da-145">How to: Host a WCF Service in a Managed Application</span></span>](../how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="e43da-146">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="e43da-146">Self-Host</span></span>](../samples/self-host.md)
- [<span data-ttu-id="e43da-147">Übersicht über die Metadatenarchitektur</span><span class="sxs-lookup"><span data-stu-id="e43da-147">Metadata Architecture Overview</span></span>](metadata-architecture-overview.md)
- [<span data-ttu-id="e43da-148">Verwenden von Metadaten</span><span class="sxs-lookup"><span data-stu-id="e43da-148">Using Metadata</span></span>](using-metadata.md)
- [<span data-ttu-id="e43da-149">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code</span><span class="sxs-lookup"><span data-stu-id="e43da-149">How to: Publish Metadata for a Service Using Code</span></span>](how-to-publish-metadata-for-a-service-using-code.md)
