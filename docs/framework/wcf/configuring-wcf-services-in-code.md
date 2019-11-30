---
title: Konfigurieren von WCF-Diensten in Code
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 5d05fe5f70f4e2b1490c728cc019430cd94ff925
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569507"
---
# <a name="configuring-wcf-services-in-code"></a>Konfigurieren von WCF-Diensten in Code
Windows Communication Foundation (WCF) ermöglicht es Entwicklern, Dienste mithilfe von Konfigurationsdateien oder Code zu konfigurieren.  Konfigurationsdateien sind nützlich, wenn ein Dienst konfiguriert werden muss, nachdem er bereitgestellt wurde. Bei der Verwendung von Konfigurationsdateien muss ein IT-Experte nur die Konfigurationsdatei aktualisieren, es ist keine Neukompilierung erforderlich. Konfigurationsdateien können jedoch komplex und schwierig zu pflegen sein. Das Debuggen von Konfigurationsdateien wird nicht unterstützt. Auf Konfigurationselemente wird über den Namen verwiesen, was die Erstellung von Konfigurationsdateien fehleranfällig und schwierig macht. WCF ermöglicht Ihnen außerdem das Konfigurieren von Diensten im Code. In früheren Versionen von WCF (4,0 und früher) war das Konfigurieren von Diensten im Code in selbstgeh osteten Szenarien ganz einfach. mit der <xref:System.ServiceModel.ServiceHost>-Klasse haben Sie die Möglichkeit, Endpunkte und Verhaltensweisen vor dem Aufrufen von Service Host. Open zu konfigurieren. In webgehosteten Szenarien haben Sie jedoch keinen direkten Zugriff auf die <xref:System.ServiceModel.ServiceHost>-Klasse. Um einen webgehosteten Dienst zu konfigurieren, mussten Sie eine `System.ServiceModel.ServiceHostFactory` erstellen, durch die ein <xref:System.ServiceModel.Activation.ServiceHostFactory> erstellt und alle erforderlichen Konfigurationsschritte ausgeführt wurden. Ab .NET 4,5 bietet WCF eine einfachere Möglichkeit, selbstgeh ostete und im Internet gehostete Dienste im Code zu konfigurieren.  
  
## <a name="the-configure-method"></a>Die Configure-Methode  
 Definieren Sie einfach in der Dienstimplementierungsklasse die öffentliche statische Methode `Configure` mit der folgenden Signatur:  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Die Configure-Methode akzeptiert eine <xref:System.ServiceModel.ServiceConfiguration>-Instanz, die es den Entwicklern ermöglicht, Endpunkte und Verhalten hinzuzufügen. Diese Methode wird von WCF aufgerufen, bevor der Dienst Host geöffnet wird. Sofern definiert, werden alle Dienstkonfigurationseinstellungen in der Datei app.config oder web.config ignoriert.  
  
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
            return $"You entered: {value}";
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
       config.EnableProtocol(new BasicHttpsBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 Die Einstellungen im Abschnitt <`protocolMappings`> werden nur verwendet, wenn der <xref:System.ServiceModel.ServiceConfiguration> Programm gesteuert keine Anwendungs Endpunkte hinzugefügt werden. Optional können Sie die Dienst Konfiguration aus der Standard Anwendungs Konfigurationsdatei laden, indem Sie <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> aufrufen und dann die Einstellungen ändern. Sie können auch mit der <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration>-Klasse die Konfiguration aus einer zentralen Konfiguration laden. Im folgenden Code wird veranschaulicht, wie dies implementiert wird:  
  
```csharp
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
> Beachten Sie, dass <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> <`host`> Einstellungen innerhalb des <`service`> Tags von <`system.serviceModel`> ignoriert. Konzeptionell ist <`host`> die Host Konfiguration, nicht die Dienst Konfiguration, und Sie wird geladen, bevor die Configure-Methode ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Diensten mit Konfigurationsdateien](configuring-services-using-configuration-files.md)
- [Konfigurieren von Clientverhalten](configuring-client-behaviors.md)
- [Vereinfachte Konfiguration](simplified-configuration.md)
- [Konfiguration](./samples/configuration-sample.md)
- [Konfigurationsbasierte Aktivierung unter IIS und WAS](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [Konfiguration und Metadatenunterstützung](./extending/configuration-and-metadata-support.md)
- [Konfiguration](./diagnostics/exceptions-reference/configuration.md)
- [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](how-to-specify-a-service-binding-in-configuration.md)
- [Vorgehensweise: Erstellen eines Dienstendpunkts in einer Konfiguration](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration](how-to-specify-a-client-binding-in-configuration.md)
