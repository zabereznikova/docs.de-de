---
title: WMI-Anbieter
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: dd24a6d270a0bd9012bbda2a53913167c9697bc5
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424512"
---
# <a name="wmi-provider"></a>WMI-Anbieter
In diesem Beispiel wird veranschaulicht, wie Daten aus Windows Communication Foundation (WCF)-Diensten zur Laufzeit mithilfe des in WCF integrierten Windows-Verwaltungsinstrumentation (WMI)-Anbieters gesammelt werden. Außerdem wird in diesem Beispiel gezeigt, wie einem Dienst ein benutzerdefiniertes WMI-Objekt hinzugefügt wird. Im Beispiel [wird der WMI-Anbieter](../../../../docs/framework/wcf/samples/getting-started-sample.md) für die ersten Schritte aktiviert, und es wird veranschaulicht, wie Daten aus dem `ICalculator`-Dienst zur Laufzeit erfasst werden.  
  
 Bei WMI handelt es sich um die Implementierung des Web-Based Enterprise Management (WBEM)-Standards von Microsoft. Weitere Informationen zum WMI-SDK finden Sie unter [Windows-Verwaltungsinstrumentation](/windows/desktop/WmiSdk/wmi-start-page). Bei WBEM handelt es sich um einen Industriestandard für das Verhalten von Anwendungen beim Verfügbarmachen der Verwaltungsinstrumentation für externe Verwaltungstools.  
  
 WCF implementiert einen WMI-Anbieter, eine Komponente, die die Instrumentation zur Laufzeit über eine WBEM-kompatible Schnittstelle verfügbar macht. Über die Schnittstelle können Verwaltungstools zur Laufzeit Verbindungen mit den Diensten herstellen. WCF macht Attribute von Diensten verfügbar, z. b. Adressen, Bindungen, Verhaltensweisen und Listener.  
  
 Der integrierte WMI-Anbieter wird in der Konfigurationsdatei der Anwendung aktiviert. Dies erfolgt über das `wmiProviderEnabled`-Attribut der [\<Diagnose >](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) im Abschnitt [\<System. Service Model >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , wie in der folgenden Beispielkonfiguration gezeigt:  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 Mit diesem Konfigurationseintrag wird eine WMI-Schnittstelle verfügbar gemacht. Über diese Schnittstelle kann nun von Verwaltungsanwendungen eine Verbindung hergestellt und auf die Verwaltungsinstrumentierung der Anwendung zugegriffen werden.  
  
## <a name="custom-wmi-object"></a>Benutzerdefiniertes WMI-Objekt  
 Wenn einem Dienst WMI-Objekte hinzugefügt werden, können zusammen mit den Informationen des integrierten WMI-Anbieters auch benutzerdefinierte Informationen preisgegeben werden. Dies wird durchgeführt, indem das Schema des Diensts mithilfe der Anwendung "Installutil.exe" in WMI veröffentlicht wird. Eine Anleitung dazu und ausführlichere Informationen finden Sie in den Anweisungen zum Einrichten am Ende dieses Themas.  
  
## <a name="accessing-wmi-information"></a>Zugreifen auf WMI-Informationen  
 Auf WMI-Daten kann auf mehreren Wegen zugegriffen werden. Microsoft stellt WMI-APIs für Skripts, Visual Basic C++ Anwendungen, Anwendungen und die .NET Framework (https://docs.microsoft.com/windows/desktop/wmisdk/using-wmi) bereit.  
  
 In diesem Beispiel werden zwei Javaskripts verwendet: das eine zum Auflisten der auf dem Computer ausgeführten Dienste mit einigen ihrer Eigenschaften und das andere zum Anzeigen benutzerdefinierter WMI-Daten. Das Skript öffnet eine Verbindung zum WMI-Anbieter, analysiert Daten und zeigt die erfassten Daten an.  
  
 Starten Sie das Beispiel, um eine laufende Instanz eines WCF-Dienstanbieter zu erstellen. Führen Sie mit dem folgenden Befehl jedes Javaskript in der Eingabeaufforderung aus, während der Dienst ausgeführt wird:  
  
```console  
cscript EnumerateServices.js  
```  
  
 Das Skript greift auf die im Dienst enthaltene Instrumentation zu und erzeugt die folgende Ausgabe:  
  
```console  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 Führen Sie danach das zweite Javaskript zum Anzeigen der benutzerdefinierten WMI-Daten aus:  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 Das Skript greift auf die in den Diensten enthaltene benutzerdefinierte Instrumentation zu und erzeugt die folgende Ausgabe:  
  
```console 
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 Die Ausgabe zeigt an, dass auf dem Computer ein einziger Dienst ausgeführt wird. Der Dienst macht einen Endpunkt verfügbar, der den `ICalculator`-Vertrag implementiert. Die Einstellungen des vom Endpunkt implementierten Verhaltens und der implementierten Bindung werden als Summe einzelner Elemente des Messagingstapels aufgeführt.  
  
 WMI ist nicht darauf beschränkt, die Verwaltungs Instrumentation der WCF-Infrastruktur verfügbar zu machen. Die Anwendung kann mithilfe desselben Mechanismus ihre eigenen domänenspezifischen Datenelemente verfügbar machen. WMI ist ein einheitlicher Mechanismus zur Kontrolle und Steuerung eines Webdiensts.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Veröffentlichen Sie das Dienstschema in WMI, indem Sie die Datei InstallUtil.exe (die sich standardmäßig unter "%WINDIR%\Microsoft.NET\Framework\v4.0.30319" befindet) für die Datei service.dll im Hostingverzeichnis ausführen. Dieser Schritt muss nur dann ausgeführt werden, wenn an der Datei service.dll Änderungen vorgenommen wurden.
  
4. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Wenn Sie WCF nach der Installation von ASP.NET installiert haben, müssen Sie möglicherweise "% windir% \" ausführen. Microsoft. NET\Framework\v3.0\Windows Communication foundation\servicemodelreg.exe "-r-x, um dem ASPNET-Konto die Berechtigung zum Veröffentlichen von WMI-Objekten zu erteilen.  
  
5. Die über WMI verfügbar gemachten Daten aus dem Beispiel zeigen Sie mit den folgenden Befehlen an: `cscript EnumerateServices.js` oder `cscript EnumerateCustomObjects.js`.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a>Siehe auch

- [AppFabric-Überwachungs Beispiele](https://go.microsoft.com/fwlink/?LinkId=193959)
