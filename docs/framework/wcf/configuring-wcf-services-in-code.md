---
title: Konfigurieren von WCF-Diensten in Code
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 2046ee00bef0f3e84a61151474c777d64005a30c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-wcf-services-in-code"></a>Konfigurieren von WCF-Diensten in Code
Windows Communication Foundation (WCF) können Entwickler Dienste mithilfe von Konfigurationsdateien oder Code konfigurieren.  Konfigurationsdateien sind nützlich, wenn ein Dienst konfiguriert werden muss, nachdem er bereitgestellt wurde. Bei der Verwendung von Konfigurationsdateien muss ein IT-Experte nur die Konfigurationsdatei aktualisieren, es ist keine Neukompilierung erforderlich. Konfigurationsdateien können jedoch komplex und schwierig zu pflegen sein. Das Debuggen von Konfigurationsdateien wird nicht unterstützt. Auf Konfigurationselemente wird über den Namen verwiesen, was die Erstellung von Konfigurationsdateien fehleranfällig und schwierig macht. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ermöglicht auch das Konfigurieren von Diensten im Code. In früheren Versionen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (4.0 und früher) war das Konfigurieren von Diensten im Code in selbstgehosteten Szenarien einfach, weil die <xref:System.ServiceModel.ServiceHost>-Klasse die Möglichkeit bot, Endpunkte und Verhaltensweisen vor dem Aufrufen von ServiceHost.Open zu konfigurieren. In webgehosteten Szenarien haben Sie jedoch keinen direkten Zugriff auf die <xref:System.ServiceModel.ServiceHost>-Klasse. Um einen webgehosteten Dienst zu konfigurieren, mussten Sie eine `System.ServiceModel.ServiceHostFactory` erstellen, durch die ein <xref:System.ServiceModel.Activation.ServiceHostFactory> erstellt und alle erforderlichen Konfigurationsschritte ausgeführt wurden. Ab .NET 4.5 bietet [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] eine einfachere Möglichkeit, selbstgehostete und webgehostete Dienste im Code zu konfigurieren.  
  
## <a name="the-configure-method"></a>Die Configure-Methode  
 Definieren Sie einfach in der Dienstimplementierungsklasse die öffentliche statische Methode `Configure` mit der folgenden Signatur:  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Die Configure-Methode akzeptiert eine <xref:System.ServiceModel.ServiceConfiguration>-Instanz, die es den Entwicklern ermöglicht, Endpunkte und Verhalten hinzuzufügen. Diese Methode wird von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aufgerufen, bevor der Diensthost geöffnet wird. Sofern definiert, werden alle Dienstkonfigurationseinstellungen in der Datei app.config oder web.config ignoriert.  
  
 Der folgende Codeausschnitt zeigt, wie die `Configure`-Methode definiert wird und ein Dienstendpunkt, ein Endpunktverhalten und Dienstverhalten hinzugefügt werden:  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return string.Format("You entered: {0}", value);  
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 Um ein Protokoll, z. B. HTTPS, für einen Dienst zu aktivieren, können Sie entweder explizit einen Endpunkt hinzufügen, der das Protokoll verwendet, oder Sie können automatisch Endpunkte durch Aufrufen von ServiceConfiguration.EnableProtocol(Binding) hinzufügen. Dabei wird ein Endpunkt für jede Basisadresse, die mit dem Protokoll kompatibel ist, und für jeden definierten Dienstvertrag hinzugefügt. Der folgende Code veranschaulicht die Verwendung der ServiceConfiguration.EnableProtocol-Methode:  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 Die Einstellungen in der <`protocolMappings`> Abschnitt werden nur verwendet, wenn keine Endpunkte hinzugefügt werden die <xref:System.ServiceModel.ServiceConfiguration> programmgesteuert. Sie können optional die Dienstkonfiguration aus der Standard-Anwendungskonfigurationsdatei laden, durch den Aufruf <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> und klicken Sie dann die Einstellungen zu ändern. Sie können auch mit der <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration>-Klasse die Konfiguration aus einer zentralen Konfiguration laden. Im folgenden Code wird veranschaulicht, wie dies implementiert wird:  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
>  Beachten Sie, dass <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignoriert <`host`> Einstellungen in der <`service`>-Tag <`system.serviceModel`>. Im Prinzip <`host`> geht es um Hostkonfiguration nicht Dienstkonfiguration, und er ruft geladen, bevor die Configure-Methode ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren von Diensten mit Konfigurationsdateien](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [Konfigurieren von Clientverhalten](../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md)  
 [Konfigurationsbasierte Aktivierung](../../../docs/framework/wcf/samples/configuration-based-activation.md)  
 [Konfiguration](../../../docs/framework/wcf/samples/configuration-sample.md)  
 [Konfigurationsbasierte Aktivierung unter IIS und WAS](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 [Konfiguration und Metadatenunterstützung](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)  
 [Konfiguration](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)  
 [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
