---
title: "WMI-Anbieter | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
caps.latest.revision: 35
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 35
---
# WMI-Anbieter
Dieses Beispiel veranschaulicht, wie Daten aus [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Diensten mithilfe des in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] integrierten WMI\-Anbieters \(Windows Management Instrumentation, Windows\-Verwaltungsinstrumentation\) zur Laufzeit erfasst werden.  Außerdem wird in diesem Beispiel gezeigt, wie einem Dienst ein benutzerdefiniertes WMI\-Objekt hinzugefügt wird.  Im Beispiel wird der WMI\-Anbieter für das [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md) aktiviert und gezeigt, wie Daten aus dem `ICalculator`\-Dienst zur Laufzeit erfasst werden.  
  
 Bei WMI handelt es sich um die Implementierung des Web\-Based Enterprise Management \(WBEM\)\-Standards von Microsoft.  Weitere Informationen zum WMI\-SDK finden Sie in der MSDN Library.  \(http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/wmisdk\/wmi\/wmi\_start\_page.asp\).  Bei WBEM handelt es sich um einen Industriestandard für das Verhalten von Anwendungen beim Verfügbarmachen der Verwaltungsinstrumentation für externe Verwaltungstools.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert einen WMI\-Anbieter, eine Komponente, die die Instrumentation zur Laufzeit über eine WBEM\-kompatible Schnittstelle verfügbar macht.  Über die Schnittstelle können Verwaltungstools zur Laufzeit Verbindungen mit den Diensten herstellen.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] macht Attribute von Diensten \(wie Adressen, Bindungen, Verhaltensweisen und Listener\) verfügbar.  
  
 Der integrierte WMI\-Anbieter wird in der Konfigurationsdatei der Anwendung aktiviert.  Dies erfolgt über das `wmiProviderEnabled`\-Attribut des [\<Diagnose\>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)s im Abschnitt des [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)\-Elements Abschnitt, wie in der folgenden Beispielkonfiguration gezeigt:  
  
```  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
  
```  
  
 Mit diesem Konfigurationseintrag wird eine WMI\-Schnittstelle verfügbar gemacht.  Über diese Schnittstelle kann nun von Verwaltungsanwendungen eine Verbindung hergestellt und auf die Verwaltungsinstrumentation der Anwendung zugegriffen werden.  
  
## Benutzerdefiniertes WMI\-Objekt  
 Wenn einem Dienst WMI\-Objekte hinzugefügt werden, können zusammen mit den Informationen des integrierten WMI\-Anbieters auch benutzerdefinierte Informationen preisgegeben werden.  Dies wird durchgeführt, indem das Schema des Diensts mithilfe der Anwendung "Installutil.exe" in WMI veröffentlicht wird.  Eine Anleitung dazu und ausführlichere Informationen finden Sie in den Anweisungen zum Einrichten am Ende dieses Themas.  
  
## Zugreifen auf WMI\-Informationen  
 Auf WMI\-Daten kann auf mehreren Wegen zugegriffen werden.  Microsoft stellt WMI\-APIs für Skripts, [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\-Anwendungen, C\+\+\-Anwendungen und die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] \(http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/wmisdk\/wmi\/using\_wmi.asp\) bereit.  
  
 In diesem Beispiel werden zwei Javaskripts verwendet: das eine zum Auflisten der auf dem Computer ausgeführten Dienste mit einigen ihrer Eigenschaften und das andere zum Anzeigen benutzerdefinierter WMI\-Daten.  Das Skript öffnet eine Verbindung zum WMI\-Anbieter, analysiert Daten und zeigt die erfassten Daten an.  
  
 Starten Sie das Beispiel, um eine laufende Instanz eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts zu erstellen.  Führen Sie mit dem folgenden Befehl jedes Javaskript in der Eingabeaufforderung aus, während der Dienst ausgeführt wird:  
  
```  
cscript EnumerateServices.js  
  
```  
  
 Das Skript greift auf die im Dienst enthaltene Instrumentation zu und erzeugt die folgende Ausgabe:  
  
```  
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
  
 Führen Sie danach das zweite Javaskript zum Anzeigen der benutzerdefinierten WMI\-Daten aus:  
  
```  
cscript EnumerateCustomObjects.js  
```  
  
 Das Skript greift auf die in den Diensten enthaltene benutzerdefinierte Instrumentation zu und erzeugt die folgende Ausgabe:  
  
```  
  
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
  
```  
  
 Die Ausgabe zeigt an, dass auf dem Computer ein einziger Dienst ausgeführt wird.  Der Dienst macht einen Endpunkt verfügbar, der den `ICalculator`\-Vertrag implementiert.  Die Einstellungen des vom Endpunkt implementierten Verhaltens und der implementierten Bindung werden als Summe einzelner Elemente des Messagingstapels aufgeführt.  
  
 WMI beschränkt sich nicht darauf, die Verwaltungsinstrumentation der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Infrastruktur verfügbar zu machen.  Die Anwendung kann mithilfe desselben Mechanismus ihre eigenen domänenspezifischen Datenelemente verfügbar machen.  WMI ist ein einheitlicher Mechanismus zur Kontrolle und Steuerung eines Webdiensts.  
  
#### So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Befolgen Sie zum Erstellen der C\#\- oder Visual Basic .NET\-Variante der Lösung die Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Veröffentlichen Sie das Dienstschema in WMI, indem Sie die Datei InstallUtil.exe \(die sich standardmäßig unter "%WINDIR%\\Microsoft.NET\\Framework\\v4.0.30319" befindet\) für die Datei service.dll im Hostingverzeichnis ausführen.  Dieser Schritt muss nur dann ausgeführt werden, wenn an der Datei service.dll Änderungen vorgenommen wurden.  Weitere Informationen finden Sie unter "Bereitstellen von Verwaltungsinformationen durch Instrumentieren von Anwendungen" unter "http:\/\/msdn2.microsoft.com\/library\/ms186147.aspx" im Abschnitt "Vorgehensweise: Veröffentlichen des Schemas für eine instrumentierte Anwendung in WMI".  
  
4.  Wenn Sie das Beispiel in einer Einzelcomputer\- oder einer computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    >  Wenn Sie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nach der Installation von ASP.NET installiert haben, müssen Sie u. U. "%WINDIR%\\Microsoft.Net\\Framework\\v3.0\\Windows Communication Foundation\\servicemodelreg.exe \-r –x" ausführen, um dem ASPNET\-Konto die Berechtigung zum Veröffentlichen von WMI\-Objekten zu erteilen.  
  
5.  Die über WMI verfügbar gemachten Daten aus dem Beispiel zeigen Sie mit den folgenden Befehlen an: `cscript EnumerateServices.js` oder `cscript EnumerateCustomObjects.js`.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## Siehe auch  
 [AppFabric\-Überwachungsbeispiele](http://go.microsoft.com/fwlink/?LinkId=193959)