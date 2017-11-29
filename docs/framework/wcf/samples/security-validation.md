---
title: Sicherheitsvalidierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
caps.latest.revision: "35"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 4e8e8ff9a99c362fb5e2a6f5ef1161f48df86ceb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="security-validation"></a>Sicherheitsvalidierung
Dieses Beispiel veranschaulicht die Verwendung eines benutzerdefinierten Verhaltens, mit dem Dienste auf einem Computer überprüft werden, um sicherzustellen, dass sie bestimmte Kriterien erfüllen. In diesem Beispiel werden Dienste vom benutzerdefinierten Verhalten überprüft, indem jeder Endpunkt im Dienst gescannt und dahingehend überprüft wird, ob er sichere Bindungselemente enthält. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## <a name="endpoint-validation-custom-behavior"></a>Benutzerdefiniertes Verhalten zur Endpunktvalidierung  
 Durch Hinzufügen von Benutzercode zur `Validate`-Methode aus der <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle kann einem Dienst oder einem Endpunkt benutzerdefiniertes Verhalten zugewiesen werden, um benutzerdefinierte Aktionen auszuführen. Mit dem folgenden Code wird jeder in einem Dienst enthaltene Endpunkt durchlaufen und deren Bindungsauflistungen nach sicheren Bindungen durchsucht.  
  
```  
public void Validate(ServiceDescription serviceDescription,   
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually gathering their    
       binding elements.  
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
>  Beim Hinzufügen von Verhalten zu allen Diensten wird empfohlen, vorher die Datei Machine.config zu sichern.  
  
 Führen Sie nun den Client aus dem Verzeichnis client\bin dieses Beispiels aus. Eine Ausnahme mit der folgenden Nachricht tritt auf: "Der angeforderte Dienst, 'http://localhost/servicemodelsamples/service.svc', konnte nicht aktiviert werden." Dies ist zu erwarten, da das Endpunktvalidierungsverhalten einen Endpunkt als unsicher betrachtet und verhindert, dass der Dienst startet. Außerdem löst das Verhalten eine interne Ausnahme aus, die beschreibt, welcher Endpunkt unsicher ist, und schreibt eine Nachricht für die Ereignisanzeige unter der Quelle "System.ServiceModel 4.0.0.0" und der Kategorie "WebHost". Es ist auch möglich, für den Dienst aus diesem Beispiel die Ablaufverfolgung einzuschalten. Dadurch wird dem Benutzer ermöglicht, die vom Endpunktvalidierungsverhalten ausgelösten Ausnahmen anzuzeigen, indem er die resultierenden Dienstablaufverfolgungen mit dem Service Trace Viewer öffnet.  
  
#### <a name="to-view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a>So zeigen Sie Ausnahmemeldungen von fehlgeschlagenen Endpunktvalidierungen in der Ereignisanzeige an  
  
1.  Klicken Sie auf die **starten** Menü **ausführen...** .  
  
2.  Typ `eventvwr` , und klicken Sie auf **OK**.  
  
3.  Klicken Sie im Fenster-Ereignisanzeige auf **Anwendung**.  
  
4.  Doppelklicken Sie auf das Ereignis "System.ServiceModel 4.0.0.0" kürzlich hinzugefügte unter der Kategorie "WebHost" in der **Anwendung** Fenster aus, um Nachrichten von unsicheren Endpunkten anzuzeigen.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a>Siehe auch  
 [Überwachen der AppFabric-Beispiele](http://go.microsoft.com/fwlink/?LinkId=193959)
