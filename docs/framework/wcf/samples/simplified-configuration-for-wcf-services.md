---
title: "Vereinfachte Konfiguration für WCF-Dienste"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c6f0d73ba01ec51fe2fcd00f33bbd3183e382c74
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="simplified-configuration-for-wcf-services"></a>Vereinfachte Konfiguration für WCF-Dienste
Dieses Beispiel zeigt, wie mithilfe von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ein typischer Dienst und ein typischer Client implementiert und konfiguriert werden. Es dient als Grundlage für alle anderen grundlegenden Technologiebeispiele.  
  
 Dieser Dienst, der einen Endpunkt zur Kommunikation mit dem Dienst verfügbar macht, verwendet die vereinfachte Konfiguration in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]. Vor [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] wird der Endpunkt in der Regel in einer Konfigurationsdatei (Web.config) definiert, wie im folgenden Beispielkonfigurationscode gezeigt.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] ist das `<service>`-Element optional. Wenn ein Dienst keine Endpunkte definiert, wird ein Endpunkt für jede Basisadresse und jeden implementierten Vertrag zum Dienst hinzugefügt. Die Basisadresse wird an den Vertragsnamen angefügt, um den Endpunkt zu bestimmen, und die Bindung wird vom Adressschema bestimmt. Im folgenden Codebeispiel wird eine vereinfachte Konfigurationsdatei veranschaulicht. Wie in der Konfiguration angegeben, kann auf den Dienst unter http://localhost/servicemodelsamples/service.svc von einem Client auf demselben Computer zugegriffen werden. Bei Clients auf Remotecomputern muss für den Dienstzugriff anstelle von localhost ein vollqualifizierter Domänenname angegeben werden. Standardmäßig macht der Dienst keine Metadaten verfügbar. Damit aktiviert der Dienst das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Verhalten.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Führen Sie das Beispiel aus, indem Sie folgende Schritte ausführen:  
  
    1.  Klicken Sie mit der rechten Maustaste auf die **Service** Projekt, und wählen Sie **als Startprojekt festlegen**, drücken Sie dann die **STRG + F5**.  
  
    2.  Warten Sie auf die Ausgabe der Konsole, die bestätigt, dass der Dienst gestartet ist und ausgeführt wird.  
  
    3.  Klicken Sie mit der rechten Maustaste auf die **Client** Projekt, und wählen Sie **als Startprojekt festlegen**, drücken Sie dann die **STRG + F5**.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiele für AppFabric-Management](http://go.microsoft.com/fwlink/?LinkId=193960)  
 [Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md)
