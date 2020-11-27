---
title: 'Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration'
description: Erfahren Sie, wie Endpunkte für einen WCF-Dienst mithilfe einer Konfigurationsdatei hinzugefügt werden, die sowohl relative als auch absolute Adressen enthält.
ms.date: 06/16/2016
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
ms.openlocfilehash: aa8dce18a39b44c2c56d072a81699d1bc1e7d7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286421"
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a>Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration

Endpunkte ermöglichen Clients den Zugriff auf die Funktionalität, die ein Windows Communication Foundation (WCF)-Dienst bietet. Sie können einen oder mehrere Endpunkte mit einer Kombination relativer und absoluter Endpunktadressen für den Dienst definieren. Wenn Sie keine Dienstendpunkte definieren, stellt die Runtime standardmäßig einige Endpunkte bereit. In diesem Thema wird beschrieben, wie Endpunkte, die sowohl relative als auch absolute Adressen enthalten, mit einer Konfigurationsdatei hinzugefügt werden.  
  
## <a name="example"></a>Beispiel  

 Die folgende Dienstkonfiguration gibt eine Basisadresse und fünf Endpunkte an.  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced in .NET Framework 4. -->  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService">  
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
  
## <a name="example"></a>Beispiel  

 Die Basisadresse wird mit dem `add`-Element unter "Dienst/Host/baseAddresses" angegeben, wie im folgenden Beispiel dargestellt.  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a>Beispiel  

 Die erste Endpunktdefinition, die im folgenden Beispiel gezeigt wird, gibt eine relative Adresse an. Dies bedeutet, dass die Endpunktadresse eine Kombination aus der Basisadresse und der relativen Adresse nach den Regelen der Uniform Resource Identifier (URI)-Zusammensetzung ist. Die relative Adresse ist leer (""), folglich ist die Endpunktadresse gleich der Basisadresse. Die tatsächliche Endpunkt Adresse ist `http://localhost:8000/servicemodelsamples/service` .  
  
```xml  
<endpoint address=""
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>Beispiel  

 Die zweite Endpunktdefinition gibt ebenfalls eine relative Adresse an, wie in der folgenden Beispielkonfiguration dargestellt. Die relative Adresse "test" ist an die Basisadresse angefügt. Die tatsächliche Endpunkt Adresse ist `http://localhost:8000/servicemodelsamples/service/test` .  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>Beispiel  

 Die dritte Endpunktdefinition gibt eine absolute Adresse an, wie in der folgenden Beispielkonfiguration dargestellt. Die Basisadresse spielt bei der Adresse keine Rolle. Die tatsächliche Endpunkt Adresse ist `http://localhost:8001/hello/servicemodelsamples` .  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>Beispiel  

 Die vierte Endpunktadresse gibt eine absolute Adresse und einen anderen Transport an, nämlich TCP. Die Basisadresse spielt bei der Adresse keine Rolle. Die tatsächliche Endpunktadresse lautet net.tcp://localhost:9000/servicemodelsamples/service.  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>Beispiel  

 Um die von der Runtime bereitgestellten Standardendpunkte zu verwenden, geben Sie weder im Code noch in der Konfigurationsdatei Dienstendpunkte an. In diesem Beispiel erstellt die Laufzeit die Standardendpunkte, wenn der Dienst geöffnet wird. Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](../simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](../samples/simplified-configuration-for-wcf-services.md).  
  
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
