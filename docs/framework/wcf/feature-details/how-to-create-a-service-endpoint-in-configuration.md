---
title: 'Gewusst wie: Erstellen eines Dienstendpunkts in einer Konfiguration'
ms.date: 06/16/2016
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
ms.openlocfilehash: 63a40576b805952197cec5af2f89a5dc4b5d3545
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266272"
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a><span data-ttu-id="8f1aa-102">Gewusst wie: Erstellen eines Dienstendpunkts in einer Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f1aa-102">How to: Create a Service Endpoint in Configuration</span></span>
<span data-ttu-id="8f1aa-103">Endpunkte ermöglichen Clients den Zugriff auf die Funktionalität, die ein Windows Communication Foundation (WCF)-Dienst bietet.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-103">Endpoints provide clients with access to the functionality a Windows Communication Foundation (WCF) service offers.</span></span> <span data-ttu-id="8f1aa-104">Sie können einen oder mehrere Endpunkte mit einer Kombination relativer und absoluter Endpunktadressen für den Dienst definieren. Wenn Sie keine Dienstendpunkte definieren, stellt die Runtime standardmäßig einige Endpunkte bereit.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-104">You can define one or more endpoints for a service by using a combination of relative and absolute endpoint addresses, or if you do not define any service endpoints, the runtime provides some by default for you.</span></span> <span data-ttu-id="8f1aa-105">In diesem Thema wird beschrieben, wie Endpunkte, die sowohl relative als auch absolute Adressen enthalten, mit einer Konfigurationsdatei hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-105">This topic shows how to add endpoints using a configuration file that contain both relative and absolute addresses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f1aa-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f1aa-106">Example</span></span>  
 <span data-ttu-id="8f1aa-107">Die folgende Dienstkonfiguration gibt eine Basisadresse und fünf Endpunkte an.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-107">The following service configuration specifies a base address and five endpoints.</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced  
         in .NET Framework 4. -->  
      <service  
          name="Microsoft.ServiceModel.Samples.CalculatorService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="/test"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="http://localhost:8001/hello/servicemodelsamples"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
                  binding="netTcpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is another relative address exposed at   
             http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="8f1aa-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f1aa-108">Example</span></span>  
 <span data-ttu-id="8f1aa-109">Die Basisadresse wird mit dem `add`-Element unter "Dienst/Host/baseAddresses" angegeben, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-109">The base address is specified using the `add` element, under service/host/baseAddresses, as shown in the following sample.</span></span>  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a><span data-ttu-id="8f1aa-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f1aa-110">Example</span></span>  
 <span data-ttu-id="8f1aa-111">Die erste Endpunktdefinition, die im folgenden Beispiel gezeigt wird, gibt eine relative Adresse an. Dies bedeutet, dass die Endpunktadresse eine Kombination aus der Basisadresse und der relativen Adresse nach den Regelen der Uniform Resource Identifier (URI)-Zusammensetzung ist.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-111">The first endpoint definition shown in the following sample specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of Uniform Resource Identifier (URI) composition.</span></span> <span data-ttu-id="8f1aa-112">Die relative Adresse ist leer (""), folglich ist die Endpunktadresse gleich der Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-112">The relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="8f1aa-113">Die tatsächliche Endpunktadresse lautet `http://localhost:8000/servicemodelsamples/service`.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-113">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>  
  
```xml  
<endpoint address=""   
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="8f1aa-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f1aa-114">Example</span></span>  
 <span data-ttu-id="8f1aa-115">Die zweite Endpunktdefinition gibt ebenfalls eine relative Adresse an, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-115">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span> <span data-ttu-id="8f1aa-116">Die relative Adresse "test" ist an die Basisadresse angefügt.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-116">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="8f1aa-117">Die tatsächliche Endpunktadresse lautet `http://localhost:8000/servicemodelsamples/service/test`.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-117">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="8f1aa-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f1aa-118">Example</span></span>  
 <span data-ttu-id="8f1aa-119">Die dritte Endpunktdefinition gibt eine absolute Adresse an, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-119">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span> <span data-ttu-id="8f1aa-120">Die Basisadresse spielt bei der Adresse keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-120">The base address plays no role in the address.</span></span> <span data-ttu-id="8f1aa-121">Die tatsächliche Endpunktadresse lautet `http://localhost:8001/hello/servicemodelsamples`.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-121">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="8f1aa-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f1aa-122">Example</span></span>  
 <span data-ttu-id="8f1aa-123">Die vierte Endpunktadresse gibt eine absolute Adresse und einen anderen Transport an, nämlich TCP.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-123">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="8f1aa-124">Die Basisadresse spielt bei der Adresse keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-124">The base address plays no role in the address.</span></span> <span data-ttu-id="8f1aa-125">Die tatsächliche Endpunktadresse lautet net.tcp://localhost:9000/servicemodelsamples/service.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-125">The actual endpoint address is net.tcp://localhost:9000/servicemodelsamples/service.</span></span>  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="8f1aa-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f1aa-126">Example</span></span>  
 <span data-ttu-id="8f1aa-127">Um die von der Runtime bereitgestellten Standardendpunkte zu verwenden, geben Sie weder im Code noch in der Konfigurationsdatei Dienstendpunkte an.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-127">To use the default endpoints provided by the runtime, do not specify any service endpoints in either the code or the configuration file.</span></span> <span data-ttu-id="8f1aa-128">In diesem Beispiel erstellt die Laufzeit die Standardendpunkte, wenn der Dienst geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="8f1aa-128">In this example, the runtime creates the default endpoints when the service is opened.</span></span> <span data-ttu-id="8f1aa-129">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="8f1aa-129">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```
