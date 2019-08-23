---
title: 'Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
ms.openlocfilehash: d3224b1d732fb82ffe68e8ce0bd410850004cb95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967157"
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a><span data-ttu-id="90a63-102">Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="90a63-102">How to: Specify a Service Binding in Configuration</span></span>
<span data-ttu-id="90a63-103">In diesem Beispiel wird ein `ICalculator`-Vertrag für einen grundlegenden Rechnerdienst definiert. Der Dienst wird in die `CalculatorService`-Klasse implementiert. Anschließend wird der Endpunkt in der Datei "Web.config" konfiguriert, in der angegeben wird, dass der Dienst die <xref:System.ServiceModel.BasicHttpBinding> verwendet.</span><span class="sxs-lookup"><span data-stu-id="90a63-103">In this example, an `ICalculator` contract is defined for a basic calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is configured in the Web.config file, where it is specified that the service uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="90a63-104">Eine Beschreibung, wie dieser Dienst mithilfe von Code anstelle einer Konfiguration konfiguriert wird, finden [Sie unter Gewusst wie: Geben Sie eine Dienst Bindung im](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)Code an.</span><span class="sxs-lookup"><span data-stu-id="90a63-104">For a description of how to configure this service using code instead of a configuration, see [How to: Specify a Service Binding in Code](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md).</span></span>  
  
 <span data-ttu-id="90a63-105">Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code.</span><span class="sxs-lookup"><span data-stu-id="90a63-105">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="90a63-106">Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90a63-106">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="90a63-107">Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="90a63-107">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="90a63-108">Alle der folgenden Konfigurationsschritte können mit dem-Konfigurations- [Editor-Tool (SvcConfigEditor. exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="90a63-108">All of the following configuration steps can be undertaken using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="90a63-109">Die Quell Kopie dieses Beispiels finden Sie unter [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md).</span><span class="sxs-lookup"><span data-stu-id="90a63-109">For the source copy of this example, see [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md).</span></span>  
  
### <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a><span data-ttu-id="90a63-110">So geben Sie die BasicHttpBinding zur Konfiguration des Dienstes an</span><span class="sxs-lookup"><span data-stu-id="90a63-110">To specify the BasicHttpBinding to use to configure the service</span></span>  
  
1. <span data-ttu-id="90a63-111">Definieren Sie einen Dienstvertrag für den Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="90a63-111">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="90a63-112">Implementieren Sie den Dienstvertrag in einer Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="90a63-112">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    > <span data-ttu-id="90a63-113">Die Adresse oder die Bindungsinformationen werden nicht in der Implementierung des Dienstes angegeben.</span><span class="sxs-lookup"><span data-stu-id="90a63-113">Address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="90a63-114">Ebenso wenig muss Code geschrieben werden, um diese Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="90a63-114">Also, code does not have to be written to fetch that information from the configuration file.</span></span>  
  
3. <span data-ttu-id="90a63-115">Erstellen Sie eine Web.config-Datei, um einen Endpunkt für den `CalculatorService` zu konfigurieren, der die <xref:System.ServiceModel.WSHttpBinding> verwendet.</span><span class="sxs-lookup"><span data-stu-id="90a63-115">Create a Web.config file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  
            <endpoint   
            <!-- Leave the address blank to be populated by default -->  
            <!-- from the hosting environment,in this case IIS, so -->  
            <!-- the address will just be that of the IIS Virtual -->  
            <!-- Directory. -->  
                address=""   
            <!-- Specify the binding type -->  
                binding="wsHttpBinding"  
            <!-- Specify the binding configuration name for that -->  
            <!-- binding type. This is optional but useful if you -->  
            <!-- want to modify the properties of the binding. -->  
            <!-- The bindingConfiguration name Binding1 is defined -->  
            <!-- below in the bindings element. -->  
                bindingConfiguration="Binding1"  
                contract="ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <wsHttpBinding>  
            <binding name="Binding1">  
              <!-- Binding property values can be modified here. -->  
              <!-- See the next procedure. -->  
            </binding>  
          </wsHttpBinding>  
       </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. <span data-ttu-id="90a63-116">Erstellen Sie eine Service.svc-Datei, die die folgende Zeile enthält, und platzieren Sie sie im virtuellen IIS-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="90a63-116">Create a Service.svc file that contains the following line and place it in your Internet Information Services (IIS) virtual directory.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="90a63-117">So ändern Sie die Standardwerte für die Bindungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="90a63-117">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="90a63-118">Um einen der Standardeigenschaftswerte von <xref:System.ServiceModel.WSHttpBinding>zu ändern, erstellen Sie im [ \<WSHttpBinding-](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) `<binding name="Binding1">` > Element einen neuen Bindungs Konfigurations Namen, und legen Sie die neuen Werte für die Attribute der Bindung in dieser Bindung fest. gewisses.</span><span class="sxs-lookup"><span data-stu-id="90a63-118">To modify one of the default property values of the <xref:System.ServiceModel.WSHttpBinding>, create a new binding configuration name - `<binding name="Binding1">` - within the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element and set the new values for the attributes of the binding in this binding element.</span></span> <span data-ttu-id="90a63-119">Wenn Sie beispielsweise die standardmäßigen Timeoutwerte für das Öffnen und Schließen von 1 Minute in 2 Minuten ändern möchten, fügen Sie Folgendes der Konfigurationsdatei hinzu:</span><span class="sxs-lookup"><span data-stu-id="90a63-119">For example, to change the default open and close timeout values of 1 minute to 2 minutes, add the following to the configuration file.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="90a63-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90a63-120">See also</span></span>

- [<span data-ttu-id="90a63-121">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="90a63-121">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="90a63-122">Angeben einer Endpunktadresse</span><span class="sxs-lookup"><span data-stu-id="90a63-122">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)
