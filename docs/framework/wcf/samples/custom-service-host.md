---
title: "Benutzerdefinierter Diensthost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Benutzerdefinierter Diensthost
In diesem Beispiel wird veranschaulicht, wie mit einer benutzerdefinierten Ableitung der <xref:System.ServiceModel.ServiceHost>\-Klasse das Laufzeitverhalten eines Diensts geändert wird.  Dieser Ansatz stellt eine wiederverwendbare Alternative zum Konfigurieren einer großen Anzahl von Diensten auf die übliche Weise war.  Außerdem zeigt das Beispiel, wie mithilfe der <xref:System.ServiceModel.Activation.ServiceHostFactory>\-Klasse ein benutzerdefinierter ServiceHost in der IIS\-\(Internet Information Services, Internetinformationsdienste\-\) oder WAS\-\(Windows Process Activation Service\-\)Hostumgebung verwendet wird.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## Informationen über das Szenario  
 Um ein unbeabsichtigtes Veröffentlichen von möglicherweise vertraulichen Dienstmetadaten zu vermeiden, wird mit der Standardkonfiguration für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste die Metadatenveröffentlichung deaktiviert.  Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten \(wie Svcutil.exe\) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist.  
  
 Wenn die Metadatenveröffentlichung für eine große Anzahl von Diensten aktiviert wird, werden jedem einzelnen Dienst die gleichen Konfigurationselemente hinzugefügt. Dies führt zu einer großen Anzahl von Konfigurationsinformationen, die weitgehend identisch sind.  Anstatt jeden Dienst einzeln zu konfigurieren, ist es möglich, imperativen Code zu schreiben, der eine einmalige Veröffentlichung der Metadaten ermöglicht. Anschließend kann dieser Code für mehrere unterschiedliche Dienste verwendet werden.  Zu diesem Zweck wird eine neue Klasse erstellt, die von <xref:System.ServiceModel.ServiceHost> abgeleitet wird und die `ApplyConfiguration`\(\)\-Methode überschreibt, um das Metadatenveröffentlichungsverhalten imperativ hinzuzufügen.  
  
> [!IMPORTANT]
>  Beachten Sie, dass in diesem Beispiel die Erstellung eines ungesicherten Metadaten\-Veröffentlichungsendpunkts veranschaulicht wird.  Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt.  
  
## Implementieren eines benutzerdefinierten Diensthosts  
 Die <xref:System.ServiceModel.ServiceHost>\-Klasse macht mehrere hilfreiche virtuelle Methoden verfügbar, die von Erben überschrieben werden können, um das Laufzeitverhalten eines Diensts zu ändern.  Beispielsweise liest die `ApplyConfiguration`\(\)\-Methode die Dienstkonfigurationsinformationen aus dem Konfigurationsspeicher und ändert die <xref:System.ServiceModel.Description.ServiceDescription> des Diensts entsprechend.  Die Standardimplementierung liest die Konfiguration aus der Konfigurationsdatei der Anwendung.  Die benutzerdefinierte Implementierung kann `ApplyConfiguration`\(\) überschreiben, um die <xref:System.ServiceModel.Description.ServiceDescription> mithilfe von imperativem Code zu ändern oder den Standardkonfigurationsspeicher vollständig zu ersetzen,  z. B. um die Endpunktkonfiguration eines Diensts aus einer Datenbank zu lesen, anstatt aus der Konfigurationsdatei der Anwendung.  
  
 In diesem Beispiel soll ein benutzerdefinierter Diensthost erstellt werden, der das ServiceMetadataBehavior hinzufügt \(das die Veröffentlichung von Metadaten ermöglicht\), selbst wenn dieses Verhalten in der Konfigurationsdatei des Diensts nicht ausdrücklich hinzugefügt wurde.  Zu diesem Zweck erstellen wir eine neue Klasse, die von <xref:System.ServiceModel.ServiceHost> erbt und `ApplyConfiguration`\(\) überschreibt.  
  
```  
class SelfDescribingServiceHost : ServiceHost  
{  
    public SelfDescribingServiceHost(Type serviceType, params Uri[] baseAddresses)  
        : base(serviceType, baseAddresses) { }  
  
    //Overriding ApplyConfiguration() allows us to   
    //alter the ServiceDescription prior to opening  
    //the service host.   
    protected override void ApplyConfiguration()  
    {  
        //First, we call base.ApplyConfiguration()  
        //to read any configuration that was provided for  
        //the service we're hosting. After this call,  
        //this.Description describes the service  
        //as it was configured.  
        base.ApplyConfiguration();       
  
        //(rest of implementation elided for clarity)  
    }  
}  
```  
  
 Da die Konfigurationen in der Konfigurationsdatei der Anwendung nicht ignoriert werden sollen, wird beim Überschreiben von `ApplyConfiguration`\(\) zuerst die Basisimplementierung aufgerufen.  Nach der Fertigstellung dieser Methode kann das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> der Beschreibung imperativ mithilfe des folgenden imperativen Codes hinzugefügt werden.  
  
```  
ServiceMetadataBehavior mexBehavior = this.Description.Behaviors.Find<ServiceMetadataBehavior>();  
if (mexBehavior == null)  
{  
    mexBehavior = new ServiceMetadataBehavior();  
    this.Description.Behaviors.Add(mexBehavior);  
}  
else  
{  
    //Metadata behavior has already been configured,   
    //so we do not have any work to do.  
    return;  
}  
```  
  
 Die letzte Aufgabe, die beim Überschreiben von `ApplyConfiguration`\(\) ausgeführt werden muss, ist das Hinzufügen des Standardmetadatenendpunkts.  Entsprechend der Konvention wird für jeden URI in der BaseAddresses\-Auflistung des Diensthosts ein Metadatenendpunkt erstellt.  
  
```  
//Add a metadata endpoint at each base address  
//using the "/mex" addressing convention  
foreach (Uri baseAddress in this.BaseAddresses)  
{  
    if (baseAddress.Scheme == Uri.UriSchemeHttp)  
    {  
        mexBehavior.HttpGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeHttps)  
    {  
        mexBehavior.HttpsGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpsBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetPipe)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexNamedPipeBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetTcp)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexTcpBinding(),  
                                "mex");  
    }  
}  
  
```  
  
## Verwenden eines benutzerdefinierten Diensthosts bei Selbsthost  
 Nachdem wir nun die Implementierung des benutzerdefinierten Diensthosts fertig gestellt haben, können wird diese verwenden, um einem beliebigen Dienst Metadatenveröffentlichungsverhalten hinzuzufügen, indem dieser Dienst innerhalb einer Instanz von `SelfDescribingServiceHost` gehostet wird.  Im folgenden Code wird gezeigt, wie diese im Selbsthostszenario verwendet wird.  
  
```  
SelfDescribingServiceHost host =   
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 Der benutzerdefinierte Host liest die Endpunktkonfiguration des Diensts nach wie vor aus der Konfigurationsdatei der Anwendung, so als wäre die <xref:System.ServiceModel.ServiceHost>\-Standardklasse zum Hosten des Diensts verwendet worden.  Da jedoch in dem benutzerdefinierten Host die Logik für die Aktivierung der Metadatenveröffentlichung hinzugefügt wurde, muss das Metadatenveröffentlichungsverhalten nicht mehr explizit in der Konfiguration aktiviert werden.  Dieser Ansatz bietet vor allem dann Vorteile, wenn Sie eine Anwendung erstellen, die mehrere Dienste enthält, und Sie die Metadatenveröffentlichung auf allen diesen Diensten aktivieren möchten, ohne jedes Mal die gleichen Konfigurationselemente schreiben zu müssen.  
  
## Verwenden eines benutzerdefinierten Diensthosts in IIS oder WAS  
 Die Verwendung eines benutzerdefinierten Diensthosts in einem Selbsthostszenario ist einfach, da ausschließlich Ihr eigener Anwendungscode für die Erstellung und Öffnung der Diensthostinstanz verantwortlich ist.  In der IIS\- oder WAS\-Hostingumgebung instanziiert jedoch die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Infrastruktur dynamisch den Host Ihres Diensts als Antwort auf eingehende Nachrichten.  Es können in dieser Hostingumgebung auch benutzerdefinierte Diensthosts verwendet werden, für diese ist jedoch zusätzlicher Code in Form einer ServiceHostFactory erforderlich.  Im folgenden Code wird eine Ableitung von <xref:System.ServiceModel.Activation.ServiceHostFactory> dargestellt, die Instanzen des benutzerdefinierten `SelfDescribingServiceHost` zurückgibt.  
  
```  
public class SelfDescribingServiceHostFactory : ServiceHostFactory  
{  
    protected override ServiceHost CreateServiceHost(Type serviceType,   
     Uri[] baseAddresses)  
    {  
        //All the custom factory does is return a new instance  
        //of our custom host class. The bulk of the custom logic should  
        //live in the custom host (as opposed to the factory)   
        //for maximum  
        //reuse value outside of the IIS/WAS hosting environment.  
        return new SelfDescribingServiceHost(serviceType,     
                                             baseAddresses);  
    }  
}  
```  
  
 Wie Sie sehen können, ist die Implementierung einer benutzerdefinierten ServiceHostFactory sehr einfach.  Die gesamte benutzerdefinierte Logik befindet sich in der Implementierung des Diensthosts, und die Factory gibt eine Instanz der abgeleiteten Klasse zurück.  
  
 Um eine benutzerdefinierte Factory mit einer Dienstimplementierung zu verwenden, müssen der .svc\-Datei des Diensts einige zusätzlich Metadaten hinzugefügt werden.  
  
```  
<%@ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"  
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"  
               language=c# Debug="true" %>  
```  
  
 Hier wurde der `@ServiceHost`\-Direktive ein zusätzliches `Factory`\-Attribut hinzugefügt, und der CLR\-Typname der benutzerdefinierten Factory wurde als Attributwert übergeben.  Wenn IIS oder WAS eine Nachricht für diesen Dienst empfängt, erstellt die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Hostinginfrastruktur zuerst eine Instanz der ServiceHostFactory und instanziiert anschließend den Diensthost durch den Aufruf von `ServiceHostFactory.CreateServiceHost()` selbst.  
  
## Ausführen des Beispiels  
 Auch wenn dieses Beispiel einen voll funktionsfähigen Client und Dienstimplementierung bereitstellt, ist das Ziel des Beispiels, die Änderung des Laufzeitverhaltens des Diensts mithilfe eines benutzerdefinierten Hosts zu veranschaulichen. Führen Sie die folgenden Schritte aus:  
  
#### So beobachten Sie den Effekt des benutzerdefinierten Hosts  
  
1.  Wenn Sie die Datei "Web.config" des Diensts öffnen, stellen Sie fest, dass keine Konfiguration explizit die Metadaten für den Dienst aktiviert.  
  
2.  Wenn Sie die .svc\-Datei des Diensts öffnen, stellen Sie fest, dass deren @ServiceHost\-Direktive ein Factoryattribut enthält, das den Namen der benutzerdefinierten ServiceHostFactory angibt.  
  
#### So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Projektmappe zu erstellen.  
  
3.  Nachdem die Projektmappe erstellt wurde, führen Sie Setup.bat aus, um die ServiceModelSamples\-Anwendung in [!INCLUDE[iisver](../../../../includes/iisver-md.md)] einzurichten.  Das Verzeichnis ServiceModelSamples sollte jetzt als [!INCLUDE[iisver](../../../../includes/iisver-md.md)]\-Anwendung angezeigt werden.  
  
4.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
5.  Um die Anwendung [!INCLUDE[iisver](../../../../includes/iisver-md.md)] zu entfernen, müssen Sie Cleanup.bat ausführen.  
  
## Siehe auch  
 [Gewusst wie: Hosten eines WCF\-Diensts in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)