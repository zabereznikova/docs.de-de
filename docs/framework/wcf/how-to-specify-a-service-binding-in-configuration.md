---
title: 'Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration'
description: Erfahren Sie, wie Sie einen Endpunkt für einen WCF-Dienst in einer Konfigurationsdatei konfigurieren. Ein Vertrag wird für einen Dienst definiert und in einer Klasse implementiert.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
ms.openlocfilehash: 06b1cd009d28f854ec73286efa29d42f0f557314
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293688"
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a><span data-ttu-id="4fac0-104">Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4fac0-104">How to: Specify a Service Binding in Configuration</span></span>

<span data-ttu-id="4fac0-105">In diesem Beispiel wird ein `ICalculator`-Vertrag für einen grundlegenden Rechnerdienst definiert. Der Dienst wird in die `CalculatorService`-Klasse implementiert. Anschließend wird der Endpunkt in der Datei "Web.config" konfiguriert, in der angegeben wird, dass der Dienst die <xref:System.ServiceModel.BasicHttpBinding> verwendet.</span><span class="sxs-lookup"><span data-stu-id="4fac0-105">In this example, an `ICalculator` contract is defined for a basic calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is configured in the Web.config file, where it is specified that the service uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="4fac0-106">Eine Beschreibung, wie dieser Dienst mithilfe von Code anstelle einer Konfiguration konfiguriert wird, finden Sie unter Gewusst [wie: Angeben einer Dienst Bindung im Code](how-to-specify-a-service-binding-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="4fac0-106">For a description of how to configure this service using code instead of a configuration, see [How to: Specify a Service Binding in Code](how-to-specify-a-service-binding-in-code.md).</span></span>  
  
 <span data-ttu-id="4fac0-107">Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code.</span><span class="sxs-lookup"><span data-stu-id="4fac0-107">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="4fac0-108">Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4fac0-108">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="4fac0-109">Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="4fac0-109">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="4fac0-110">Alle der folgenden Konfigurationsschritte können mit dem-Konfigurations- [Editor-Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4fac0-110">All of the following configuration steps can be undertaken using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="4fac0-111">Die Quell Kopie dieses Beispiels finden Sie unter [BasicBinding](./samples/basicbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4fac0-111">For the source copy of this example, see [BasicBinding](./samples/basicbinding.md).</span></span>  
  
## <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a><span data-ttu-id="4fac0-112">So geben Sie die BasicHttpBinding zur Konfiguration des Dienstes an</span><span class="sxs-lookup"><span data-stu-id="4fac0-112">To specify the BasicHttpBinding to use to configure the service</span></span>  
  
1. <span data-ttu-id="4fac0-113">Definieren Sie einen Dienstvertrag für den Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="4fac0-113">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="4fac0-114">Implementieren Sie den Dienstvertrag in einer Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="4fac0-114">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    > <span data-ttu-id="4fac0-115">Die Adresse oder die Bindungsinformationen werden nicht in der Implementierung des Dienstes angegeben.</span><span class="sxs-lookup"><span data-stu-id="4fac0-115">Address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="4fac0-116">Ebenso wenig muss Code geschrieben werden, um diese Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4fac0-116">Also, code does not have to be written to fetch that information from the configuration file.</span></span>  
  
3. <span data-ttu-id="4fac0-117">Erstellen Sie eine Web.config-Datei, um einen Endpunkt für den `CalculatorService` zu konfigurieren, der die <xref:System.ServiceModel.WSHttpBinding> verwendet.</span><span class="sxs-lookup"><span data-stu-id="4fac0-117">Create a Web.config file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  

            <!-- Leave the address blank to be populated by default -->
            <!-- from the hosting environment,in this case IIS, so -->
            <!-- the address will just be that of the IIS Virtual -->
            <!-- Directory. -->

            <!-- Specify the binding configuration name for that -->
            <!-- binding type. This is optional but useful if you -->
            <!-- want to modify the properties of the binding. -->
            <!-- The bindingConfiguration name Binding1 is defined -->
            <!-- below in the bindings element. -->
            <endpoint
                address=""
                binding="wsHttpBinding"  
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
  
4. <span data-ttu-id="4fac0-118">Erstellen Sie eine Service.svc-Datei, die die folgende Zeile enthält, und platzieren Sie sie im virtuellen IIS-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4fac0-118">Create a Service.svc file that contains the following line and place it in your Internet Information Services (IIS) virtual directory.</span></span>  
  
    ```aspx-csharp
    <%@ServiceHost language=c# Service="CalculatorService" %>
    ```  
  
## <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="4fac0-119">So ändern Sie die Standardwerte für die Bindungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="4fac0-119">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="4fac0-120">Um einen der Standardeigenschaftswerte von zu ändern <xref:System.ServiceModel.WSHttpBinding> , erstellen Sie im-Element einen neuen Bindungs Konfigurations Namen, `<binding name="Binding1">` [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) und legen Sie die neuen Werte für die Attribute der Bindung in diesem Bindungs Element fest.</span><span class="sxs-lookup"><span data-stu-id="4fac0-120">To modify one of the default property values of the <xref:System.ServiceModel.WSHttpBinding>, create a new binding configuration name - `<binding name="Binding1">` - within the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element and set the new values for the attributes of the binding in this binding element.</span></span> <span data-ttu-id="4fac0-121">Wenn Sie beispielsweise die standardmäßigen Timeoutwerte für das Öffnen und Schließen von 1 Minute in 2 Minuten ändern möchten, fügen Sie Folgendes der Konfigurationsdatei hinzu:</span><span class="sxs-lookup"><span data-stu-id="4fac0-121">For example, to change the default open and close timeout values of 1 minute to 2 minutes, add the following to the configuration file.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4fac0-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fac0-122">See also</span></span>

- [<span data-ttu-id="4fac0-123">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4fac0-123">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4fac0-124">Angeben einer Endpunktadresse</span><span class="sxs-lookup"><span data-stu-id="4fac0-124">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)
