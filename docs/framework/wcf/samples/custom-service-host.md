---
title: Benutzerdefinierter Diensthost
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 6470249c557d571dfee165d57ce518d475340093
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140935"
---
# <a name="custom-service-host"></a>Benutzerdefinierter Diensthost
In diesem Beispiel wird veranschaulicht, wie mit einer benutzerdefinierten Ableitung der <xref:System.ServiceModel.ServiceHost>-Klasse das Laufzeitverhalten eines Diensts geändert wird. Dieser Ansatz stellt eine wiederverwendbare Alternative zum Konfigurieren einer großen Anzahl von Diensten auf die übliche Weise war. Außerdem zeigt das Beispiel, wie mithilfe der <xref:System.ServiceModel.Activation.ServiceHostFactory>-Klasse ein benutzerdefinierter ServiceHost in der IIS-(Internet Information Services, Internetinformationsdienste-) oder WAS-(Windows Process Activation Service-)Hostumgebung verwendet wird.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a>Informationen über das Szenario
 Um eine unbeabsichtigte Offenlegung von potenziell sensiblen Dienst Metadaten zu verhindern, wird die Metadatenveröffentlichung durch die Standardkonfiguration für Windows Communication Foundation (WCF)-Dienste deaktiviert. Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist.  
  
 Wenn die Metadatenveröffentlichung für eine große Anzahl von Diensten aktiviert wird, werden jedem einzelnen Dienst die gleichen Konfigurationselemente hinzugefügt. Dies führt zu einer großen Anzahl von Konfigurationsinformationen, die weitgehend identisch sind. Anstatt jeden Dienst einzeln zu konfigurieren, ist es möglich, imperativen Code zu schreiben, der eine einmalige Veröffentlichung der Metadaten ermöglicht. Anschließend kann dieser Code für mehrere unterschiedliche Dienste verwendet werden. Zu diesem Zweck wird eine neue Klasse erstellt, die von <xref:System.ServiceModel.ServiceHost> abgeleitet wird und die `ApplyConfiguration`()-Methode überschreibt, um das Metadatenveröffentlichungsverhalten imperativ hinzuzufügen.  
  
> [!IMPORTANT]
> Beachten Sie, dass in diesem Beispiel die Erstellung eines ungesicherten Metadaten-Veröffentlichungsendpunkts veranschaulicht wird. Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt.  
  
## <a name="implementing-a-custom-servicehost"></a>Implementieren eines benutzerdefinierten Diensthosts
 Die <xref:System.ServiceModel.ServiceHost>-Klasse macht mehrere hilfreiche virtuelle Methoden verfügbar, die von Erben überschrieben werden können, um das Laufzeitverhalten eines Diensts zu ändern. Beispielsweise liest die `ApplyConfiguration`()-Methode die Dienstkonfigurationsinformationen aus dem Konfigurationsspeicher und ändert die <xref:System.ServiceModel.Description.ServiceDescription> des Diensts entsprechend. Die Standardimplementierung liest die Konfiguration aus der Konfigurationsdatei der Anwendung. Die benutzerdefinierte Implementierung kann `ApplyConfiguration`() überschreiben, um die <xref:System.ServiceModel.Description.ServiceDescription> mithilfe von imperativem Code zu ändern oder den Standardkonfigurationsspeicher vollständig zu ersetzen, z.&#160;B. um die Endpunktkonfiguration eines Diensts aus einer Datenbank zu lesen, anstatt aus der Konfigurationsdatei der Anwendung.  
  
 In diesem Beispiel soll ein benutzerdefinierter Diensthost erstellt werden, der das ServiceMetadataBehavior hinzufügt (das die Veröffentlichung von Metadaten ermöglicht), selbst wenn dieses Verhalten in der Konfigurationsdatei des Diensts nicht ausdrücklich hinzugefügt wurde. Zu diesem Zweck erstellen wir eine neue Klasse, die von <xref:System.ServiceModel.ServiceHost> erbt und `ApplyConfiguration`() überschreibt.  
  
```csharp
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
  
 Da die Konfigurationen in der Konfigurationsdatei der Anwendung nicht ignoriert werden sollen, wird beim Überschreiben von `ApplyConfiguration`() zuerst die Basisimplementierung aufgerufen. Nach der Fertigstellung dieser Methode kann das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> der Beschreibung imperativ mithilfe des folgenden imperativen Codes hinzugefügt werden.  
  
```csharp
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
  
 Die letzte Aufgabe, die beim Überschreiben von `ApplyConfiguration`() ausgeführt werden muss, ist das Hinzufügen des Standardmetadatenendpunkts. Entsprechend der Konvention wird für jeden URI in der BaseAddresses-Auflistung des Diensthosts ein Metadatenendpunkt erstellt.  
  
```csharp
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
  
## <a name="using-a-custom-servicehost-in-self-host"></a>Verwenden eines benutzerdefinierten Diensthosts bei Selbsthost  
 Nachdem wir nun die Implementierung des benutzerdefinierten Diensthosts fertig gestellt haben, können wird diese verwenden, um einem beliebigen Dienst Metadatenveröffentlichungsverhalten hinzuzufügen, indem dieser Dienst innerhalb einer Instanz von `SelfDescribingServiceHost` gehostet wird. Im folgenden Code wird gezeigt, wie diese im Selbsthostszenario verwendet wird.  
  
```csharp
SelfDescribingServiceHost host =
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 Der benutzerdefinierte Host liest die Endpunktkonfiguration des Diensts nach wie vor aus der Konfigurationsdatei der Anwendung, so als wäre die <xref:System.ServiceModel.ServiceHost>-Standardklasse zum Hosten des Diensts verwendet worden. Da jedoch in dem benutzerdefinierten Host die Logik für die Aktivierung der Metadatenveröffentlichung hinzugefügt wurde, muss das Metadatenveröffentlichungsverhalten nicht mehr explizit in der Konfiguration aktiviert werden. Dieser Ansatz bietet vor allem dann Vorteile, wenn Sie eine Anwendung erstellen, die mehrere Dienste enthält, und Sie die Metadatenveröffentlichung auf allen diesen Diensten aktivieren möchten, ohne jedes Mal die gleichen Konfigurationselemente schreiben zu müssen.  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a>Verwenden eines benutzerdefinierten Diensthosts in IIS oder WAS  
 Die Verwendung eines benutzerdefinierten Diensthosts in einem Selbsthostszenario ist einfach, da ausschließlich Ihr eigener Anwendungscode für die Erstellung und Öffnung der Diensthostinstanz verantwortlich ist. In der IIS-oder was-Hostingumgebung instanziiert die WCF-Infrastruktur jedoch den Host Ihres Diensts dynamisch als Reaktion auf eingehende Nachrichten. Es können in dieser Hostingumgebung auch benutzerdefinierte Diensthosts verwendet werden, für diese ist jedoch zusätzlicher Code in Form einer ServiceHostFactory erforderlich. Im folgenden Code wird eine Ableitung von <xref:System.ServiceModel.Activation.ServiceHostFactory> dargestellt, die Instanzen des benutzerdefinierten `SelfDescribingServiceHost` zurückgibt.  
  
```csharp
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
  
 Wie Sie sehen können, ist die Implementierung einer benutzerdefinierten ServiceHostFactory sehr einfach. Die gesamte benutzerdefinierte Logik befindet sich in der Implementierung des Diensthosts, und die Factory gibt eine Instanz der abgeleiteten Klasse zurück.  
  
 Um eine benutzerdefinierte Factory mit einer Dienstimplementierung zu verwenden, müssen der .svc-Datei des Diensts einige zusätzlich Metadaten hinzugefügt werden.  
  
```xml
<% @ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"
               language=c# Debug="true" %>
```
  
 Hier wurde der `Factory`-Anweisung ein zusätzliches `@ServiceHost`-Attribut hinzugefügt, und der CLR-Typname der benutzerdefinierten Factory wurde als Attributwert übergeben. Wenn IIS oder was eine Nachricht für diesen Dienst empfängt, erstellt die WCF-Hostinginfrastruktur zunächst eine Instanz von ServiceHostFactory und instanziiert dann den Dienst Host `ServiceHostFactory.CreateServiceHost()`selbst durch Aufrufen von.  
  
## <a name="running-the-sample"></a>Ausführen des Beispiels  
 Auch wenn dieses Beispiel einen voll funktionsfähigen Client und Dienstimplementierung bereitstellt, ist das Ziel des Beispiels, die Änderung des Laufzeitverhaltens des Diensts mithilfe eines benutzerdefinierten Hosts zu veranschaulichen. Führen Sie die folgenden Schritte aus:  
  
### <a name="observe-the-effect-of-the-custom-host"></a>Beobachten der Auswirkung des benutzerdefinierten Hosts
  
1. Öffnen Sie die Datei "Web. config" des Diensts, und beachten Sie, dass keine Konfiguration explizit die Metadaten für den Dienst aktiviert.  
  
2. Öffnen Sie die SVC-Datei des dienstanders, @ServiceHost und beobachten Sie, dass die-Direktive ein Factory-Attribut enthält, das den Namen einer benutzerdefinierten ServiceHostFactory angibt.  
  
### <a name="set-up-build-and-run-the-sample"></a>Einrichten, erstellen und Ausführen des Beispiels
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.

3. Nachdem die Projekt Mappe erstellt wurde, führen Sie Setup. bat aus, um die Service Model Samples-Anwendung in IIS 7,0 einzurichten. Das Verzeichnis Service Model Samples sollte jetzt als IIS 7,0-Anwendung angezeigt werden.

4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

5. Um die IIS 7,0-Anwendung zu entfernen, führen Sie *Cleanup. bat*aus.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Hosten eines WCF-Diensts in IIS](../feature-details/how-to-host-a-wcf-service-in-iis.md)
