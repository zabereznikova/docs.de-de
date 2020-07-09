---
title: Benutzerdefinierter Diensthost
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 8302c3c829883da954d200526ca641eb4c169f98
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052025"
---
# <a name="custom-service-host"></a>Benutzerdefinierter Diensthost
In diesem Beispiel wird veranschaulicht, wie mit einer benutzerdefinierten Ableitung der <xref:System.ServiceModel.ServiceHost>-Klasse das Laufzeitverhalten eines Diensts geändert wird. Dieser Ansatz stellt eine wiederverwendbare Alternative zum Konfigurieren einer großen Anzahl von Diensten auf die übliche Weise war. Außerdem zeigt das Beispiel, wie mithilfe der <xref:System.ServiceModel.Activation.ServiceHostFactory>-Klasse ein benutzerdefinierter ServiceHost in der IIS-(Internet Information Services, Internetinformationsdienste-) oder WAS-(Windows Process Activation Service-)Hostumgebung verwendet wird.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a>Informationen über das Szenario
 Um eine unbeabsichtigte Offenlegung von potenziell sensiblen Dienst Metadaten zu verhindern, wird die Metadatenveröffentlichung durch die Standardkonfiguration für Windows Communication Foundation (WCF)-Dienste deaktiviert. Dieses Verhalten ist standardmäßig sicher, bedeutet aber auch, dass Sie kein metadatenimportierungstool (z. b. Svcutil.exe) verwenden können, um den Client Code zu generieren, der zum Abrufen des Dienstanbieter erforderlich ist, es sei denn, das Metadatenveröffentlichungs Verhalten des dienstan  
  
 Wenn die Metadatenveröffentlichung für eine große Anzahl von Diensten aktiviert wird, werden jedem einzelnen Dienst die gleichen Konfigurationselemente hinzugefügt. Dies führt zu einer großen Anzahl von Konfigurationsinformationen, die weitgehend identisch sind. Anstatt jeden Dienst einzeln zu konfigurieren, ist es möglich, imperativen Code zu schreiben, der eine einmalige Veröffentlichung der Metadaten ermöglicht. Anschließend kann dieser Code für mehrere unterschiedliche Dienste verwendet werden. Zu diesem Zweck wird eine neue Klasse erstellt, die von <xref:System.ServiceModel.ServiceHost> abgeleitet wird und die `ApplyConfiguration`()-Methode überschreibt, um das Metadatenveröffentlichungsverhalten imperativ hinzuzufügen.  
  
> [!IMPORTANT]
> Beachten Sie, dass in diesem Beispiel die Erstellung eines ungesicherten Metadaten-Veröffentlichungsendpunkts veranschaulicht wird. Solche Endpunkte können für anonyme, nicht authentifizierte Consumer potenziell verfügbar sein, und vor der Bereitstellung solcher Endpunkte muss darauf geachtet werden, dass die öffentliche Offenlegung der Metadaten eines Diensts angemessen ist.  
  
## <a name="implementing-a-custom-servicehost"></a>Implementieren eines benutzerdefinierten Diensthosts
 Die <xref:System.ServiceModel.ServiceHost>-Klasse macht mehrere hilfreiche virtuelle Methoden verfügbar, die von Erben überschrieben werden können, um das Laufzeitverhalten eines Diensts zu ändern. Beispielsweise liest die `ApplyConfiguration`()-Methode die Dienstkonfigurationsinformationen aus dem Konfigurationsspeicher und ändert die <xref:System.ServiceModel.Description.ServiceDescription> des Diensts entsprechend. Die Standard Implementierung liest die Konfiguration aus der Konfigurationsdatei der Anwendung. Die benutzerdefinierte Implementierung kann `ApplyConfiguration`() überschreiben, um die <xref:System.ServiceModel.Description.ServiceDescription> mithilfe von imperativem Code zu ändern oder den Standardkonfigurationsspeicher vollständig zu ersetzen, So können Sie z. b. die Endpunkt Konfiguration eines dienstanaus einer Datenbank anstelle der Konfigurationsdatei der Anwendung lesen.  
  
 In diesem Beispiel möchten wir einen benutzerdefinierten Service Host erstellen, der das ServiceMetadataBehavior (das die Metadatenveröffentlichung ermöglicht) hinzufügt, auch wenn dieses Verhalten nicht explizit in der Konfigurationsdatei des Diensts hinzugefügt wird. Um dies zu erreichen, erstellen Sie eine neue Klasse, die von erbt <xref:System.ServiceModel.ServiceHost> und `ApplyConfiguration` () überschreibt.  
  
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
  
 Da keine Konfiguration ignoriert werden soll, die in der Konfigurationsdatei der Anwendung bereitgestellt wurde, wird als erstes bei der außer Kraft Setzung von `ApplyConfiguration` () die Basis Implementierung aufgerufen. Nach der Fertigstellung dieser Methode kann das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> der Beschreibung imperativ mithilfe des folgenden imperativen Codes hinzugefügt werden.  
  
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
  
 Die letzte Aufgabe, die beim Überschreiben von `ApplyConfiguration`() ausgeführt werden muss, ist das Hinzufügen des Standardmetadatenendpunkts. Gemäß der Konvention wird für jeden URI in der baseadressen-Auflistung des Dienst Hosts ein Metadatenendpunkt erstellt.  
  
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
  
 Der benutzerdefinierte Host liest weiterhin die Endpunkt Konfiguration des Diensts aus der Konfigurationsdatei der Anwendung, so als ob wir die Standard <xref:System.ServiceModel.ServiceHost> Klasse zum Hosten des Diensts verwendet hätten. Da jedoch in dem benutzerdefinierten Host die Logik für die Aktivierung der Metadatenveröffentlichung hinzugefügt wurde, muss das Metadatenveröffentlichungsverhalten nicht mehr explizit in der Konfiguration aktiviert werden. Dieser Ansatz bietet vor allem dann Vorteile, wenn Sie eine Anwendung erstellen, die mehrere Dienste enthält, und Sie die Metadatenveröffentlichung auf allen diesen Diensten aktivieren möchten, ohne jedes Mal die gleichen Konfigurationselemente schreiben zu müssen.  
  
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
  
 Wie Sie sehen können, ist die Implementierung einer benutzerdefinierten ServiceHostFactory unkompliziert. Die gesamte benutzerdefinierte Logik befindet sich in der Implementierung des Diensthosts, und die Factory gibt eine Instanz der abgeleiteten Klasse zurück.  
  
 Damit eine benutzerdefinierte Factory mit einer Dienst Implementierung verwendet werden kann, müssen der SVC-Datei des dienstanteils zusätzliche Metadaten hinzugefügt werden.  
  
```aspx-csharp
<% @ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"
               language=c# Debug="true" %>
```
  
 Hier haben wir ein zusätzliches `Factory` Attribut zur `@ServiceHost` -Direktive hinzugefügt und den CLR-Typnamen der benutzerdefinierten Factory als Attribut Wert weitergegeben. Wenn IIS oder was eine Nachricht für diesen Dienst empfängt, erstellt die WCF-Hostinginfrastruktur zunächst eine Instanz von ServiceHostFactory und instanziiert dann den Dienst Host selbst durch Aufrufen von `ServiceHostFactory.CreateServiceHost()` .  
  
## <a name="running-the-sample"></a>Ausführen des Beispiels  
 Obwohl dieses Beispiel eine voll funktionsfähige Client-und Dienst Implementierung bereitstellt, besteht der Punkt des Beispiels darin, zu veranschaulichen, wie das Laufzeitverhalten eines Diensts mithilfe eines benutzerdefinierten Hosts geändert werden kann. führen Sie die folgenden Schritte aus:  
  
### <a name="observe-the-effect-of-the-custom-host"></a>Beobachten der Auswirkung des benutzerdefinierten Hosts
  
1. Öffnen Sie die Web.config Datei des dienstanders, und beachten Sie, dass keine Konfiguration explizit die Metadaten für den Dienst aktiviert.  
  
2. Öffnen Sie die SVC-Datei des dienstanders, und beobachten Sie, dass die- @ServiceHost Direktive ein Factory-Attribut enthält, das den Namen einer benutzerdefinierten ServiceHostFactory angibt.  
  
### <a name="set-up-build-and-run-the-sample"></a>Einrichten, erstellen und Ausführen des Beispiels
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.

3. Nachdem die Projekt Mappe erstellt wurde, führen Sie Setup.bat aus, um die Service Model Samples-Anwendung in IIS 7,0 einzurichten. Das Verzeichnis Service Model Samples sollte jetzt als IIS 7,0-Anwendung angezeigt werden.

4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

5. Führen Sie *Cleanup.bat*aus, um die IIS 7,0-Anwendung zu entfernen.

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Hosten eines WCF-Diensts in IIS](../feature-details/how-to-host-a-wcf-service-in-iis.md)
