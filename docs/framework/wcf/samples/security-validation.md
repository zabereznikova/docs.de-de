---
title: Sicherheitsvalidierung
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
ms.openlocfilehash: 70408976469b1cbcf9c4679bd91d81872ec74ae1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599970"
---
# <a name="security-validation"></a>Sicherheitsüberprüfung
Dieses Beispiel veranschaulicht die Verwendung eines benutzerdefinierten Verhaltens, mit dem Dienste auf einem Computer überprüft werden, um sicherzustellen, dass sie bestimmte Kriterien erfüllen. In diesem Beispiel werden Dienste vom benutzerdefinierten Verhalten überprüft, indem jeder Endpunkt im Dienst gescannt und dahingehend überprüft wird, ob er sichere Bindungselemente enthält. Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## <a name="endpoint-validation-custom-behavior"></a>Benutzerdefiniertes Verhalten zur Endpunktvalidierung  
 Durch Hinzufügen von Benutzercode zur `Validate`-Methode aus der <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle kann einem Dienst oder einem Endpunkt benutzerdefiniertes Verhalten zugewiesen werden, um benutzerdefinierte Aktionen auszuführen. Mit dem folgenden Code wird jeder in einem Dienst enthaltene Endpunkt durchlaufen und deren Bindungsauflistungen nach sicheren Bindungen durchsucht.  
  
```csharp
public void Validate(ServiceDescription serviceDescription,
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually, gathering their
    // binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any
        // secure binding elements. Transport, Asymmetric, and Symmetric
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 Durch Hinzufügen des folgenden Codes zu der Datei "Web.config" wird die `serviceValidate`-Verhaltenserweiterung für den zu erkennenden Dienst hinzugefügt.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>
    ...
</system.serviceModel>
```  
  
 Nach dem Hinzufügen der Verhaltenserweiterung zum Dienst kann nun das `endpointValidate`-Verhalten zur Liste der Verhaltensweisen in der Datei "Web.config" (und damit zum Dienst) hinzugefügt werden.  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 Wenn Verhalten und deren Erweiterungen der Datei Web.config hinzugefügt werden, wird das Verhalten auf einzelne Dienste angewendet. Werden Sie aber der Datei Machine.config hinzugefügt, gilt das Verhalten für alle aktiven Dienste auf dem Computer.  
  
> [!NOTE]
> Beim Hinzufügen von Verhalten zu allen Diensten wird empfohlen, vorher die Datei Machine.config zu sichern.  
  
 Führen Sie nun den Client aus dem Verzeichnis client\bin dieses Beispiels aus. Eine Ausnahme wird mit der folgenden Meldung ausgelöst: "der angeforderte Dienst, ' http://localhost/servicemodelsamples/service.svc ' konnte nicht aktiviert werden." Dies ist zu erwarten, da das Endpunktvalidierungsverhalten einen Endpunkt als unsicher betrachtet und verhindert, dass der Dienst startet. Außerdem löst das Verhalten eine interne Ausnahme aus, die beschreibt, welcher Endpunkt unsicher ist, und schreibt eine Nachricht für die Ereignisanzeige unter der Quelle "System.ServiceModel 4.0.0.0" und der Kategorie "WebHost". Es ist auch möglich, für den Dienst aus diesem Beispiel die Ablaufverfolgung einzuschalten. Dadurch wird dem Benutzer ermöglicht, die vom Endpunktvalidierungsverhalten ausgelösten Ausnahmen anzuzeigen, indem er die resultierenden Dienstablaufverfolgungen mit dem Service Trace Viewer öffnet.  
  
### <a name="view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a>Anzeigen fehlerhafter Endpunkt Validierungs Ausnahme Meldungen im Ereignisanzeige  
  
1. Klicken Sie **auf das** Startmenü, und wählen Sie **ausführen...** aus.  
  
2. Geben Sie `eventvwr` ein und klicken Sie dann auf **OK**.  
  
3. Klicken Sie im Fenster Ereignisanzeige auf **Anwendung**.  
  
4. Doppelklicken Sie auf das kürzlich hinzugefügte Ereignis "System. Service Model 4.0.0.0" unter der Kategorie "Webhost" im **Anwendungs** Fenster, um unsichere Endpunkt Nachrichten anzuzeigen.  
  
## <a name="set-up-build-and-run-the-sample"></a>Einrichten, erstellen und Ausführen des Beispiels  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a>Weitere Informationen

- [AppFabric-Überwachungsbeispiele](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
