---
title: Vereinfachte Konfiguration für WCF-Dienste
description: Erfahren Sie, wie Sie einen typischen Dienst und Client mithilfe von WCF implementieren und konfigurieren. Der-Dienst kommuniziert über einen Endpunkt, der in einer Konfigurationsdatei angegeben ist.
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: 087618d603ea1c7df75ab5383f6c95b781dca847
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96290022"
---
# <a name="simplified-configuration-for-wcf-services"></a>Vereinfachte Konfiguration für WCF-Dienste

In diesem Beispiel wird veranschaulicht, wie ein typischer Dienst und Client mit Windows Communication Foundation (WCF) implementiert und konfiguriert wird. Es dient als Grundlage für alle anderen grundlegenden Technologiebeispiele.  
  
 Dieser Dienst, der einen Endpunkt für die Kommunikation mit dem Dienst verfügbar macht, verwendet die vereinfachte Konfiguration in .NET Framework 4. Vor .NET Framework 4 wird der Endpunkt in der Regel in einer Konfigurationsdatei (Web.config) definiert, wie im folgenden Beispiel Konfigurations Code gezeigt.  
  
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
  
 In .NET Framework 4 ist das- `<service>` Element optional. Wenn ein Dienst keine Endpunkte definiert, wird ein Endpunkt für jede Basisadresse und jeden implementierten Vertrag zum Dienst hinzugefügt. Die Basisadresse wird an den Vertragsnamen angefügt, um den Endpunkt zu bestimmen, und die Bindung wird vom Adressschema bestimmt. Im folgenden Codebeispiel wird eine vereinfachte Konfigurationsdatei veranschaulicht. Wie konfiguriert, kann `http://localhost/servicemodelsamples/service.svc` von einem Client auf dem gleichen Computer auf den Dienst zugegriffen werden. Bei Clients auf Remotecomputern muss für den Dienstzugriff anstelle von localhost ein vollqualifizierter Domänenname angegeben werden. Standardmäßig macht der Dienst keine Metadaten verfügbar. Damit aktiviert der Dienst das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Verhalten.  
  
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
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.  
  
3. Führen Sie das Beispiel aus, indem Sie folgende Schritte ausführen:  
  
    1. Klicken Sie mit der rechten Maustaste auf das **Dienst** Projekt, und wählen Sie **als Startprojekt festlegen**. Drücken Sie dann **STRG + F5**  
  
    2. Warten Sie auf die Ausgabe der Konsole, die bestätigt, dass der Dienst gestartet ist und ausgeführt wird.  
  
    3. Klicken Sie mit der rechten Maustaste auf das **Client** Projekt, und wählen Sie **als Startprojekt festlegen**. Drücken Sie dann **STRG + F5**  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Verwaltungsbeispiele](/previous-versions/appfabric/ff383405(v=azure.10))
- [Vereinfachte Konfiguration](../simplified-configuration.md)
