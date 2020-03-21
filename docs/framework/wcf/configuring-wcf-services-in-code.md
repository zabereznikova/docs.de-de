---
title: Konfigurieren von WCF-Diensten in Code
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 4ff49b4e17ae179426cc033a955ecf2c71f2a3e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174809"
---
# <a name="configuring-wcf-services-in-code"></a>Konfigurieren von WCF-Diensten in Code
Mit Windows Communication Foundation (WCF) können Entwickler Dienste mithilfe von Konfigurationsdateien oder Code konfigurieren.  Konfigurationsdateien sind nützlich, wenn ein Dienst konfiguriert werden muss, nachdem er bereitgestellt wurde. Bei der Verwendung von Konfigurationsdateien muss ein IT-Experte nur die Konfigurationsdatei aktualisieren, es ist keine Neukompilierung erforderlich. Konfigurationsdateien können jedoch komplex und schwierig zu pflegen sein. Das Debuggen von Konfigurationsdateien wird nicht unterstützt. Auf Konfigurationselemente wird über den Namen verwiesen, was die Erstellung von Konfigurationsdateien fehleranfällig und schwierig macht. Mit WCF können Sie auch Dienste im Code konfigurieren. In früheren Versionen von WCF (4.0 und früher) war das Konfigurieren <xref:System.ServiceModel.ServiceHost> von Diensten im Code in selbst gehosteten Szenarien einfach, die Klasse ermöglichte es Ihnen, Endpunkte und Verhaltensweisen vor dem Aufruf von ServiceHost.Open zu konfigurieren. In webgehosteten Szenarien haben Sie jedoch keinen direkten Zugriff auf die <xref:System.ServiceModel.ServiceHost>-Klasse. Um einen webgehosteten Dienst zu konfigurieren, mussten Sie eine `System.ServiceModel.ServiceHostFactory` erstellen, durch die ein <xref:System.ServiceModel.Activation.ServiceHostFactory> erstellt und alle erforderlichen Konfigurationsschritte ausgeführt wurden. Ab .NET 4.5 bietet WCF eine einfachere Möglichkeit, sowohl selbst gehostete als auch webgehostete Dienste im Code zu konfigurieren.  
  
## <a name="the-configure-method"></a>Die Configure-Methode  
 Definieren Sie einfach in der Dienstimplementierungsklasse die öffentliche statische Methode `Configure` mit der folgenden Signatur:  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Die Configure-Methode akzeptiert eine <xref:System.ServiceModel.ServiceConfiguration>-Instanz, die es den Entwicklern ermöglicht, Endpunkte und Verhalten hinzuzufügen. Diese Methode wird von WCF aufgerufen, bevor der Diensthost geöffnet wird. Sofern definiert, werden alle Dienstkonfigurationseinstellungen in der Datei app.config oder web.config ignoriert.  
  
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
  
 Die Einstellungen im `protocolMappings` Abschnitt <> werden nur verwendet, <xref:System.ServiceModel.ServiceConfiguration> wenn dem programmgesteuerten Abschnitt keine Anwendungsendpunkte hinzugefügt werden. Sie können die Dienstkonfiguration optional aus der Standardanwendungskonfigurationsdatei laden, indem Sie die Einstellungen aufrufen <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> und dann ändern. Sie können auch mit der <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration>-Klasse die Konfiguration aus einer zentralen Konfiguration laden. Im folgenden Code wird veranschaulicht, wie dies implementiert wird:  
  
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
> Beachten <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> Sie, `host` dass <> `service` Einstellungen innerhalb `system.serviceModel` des <>-Tags von <> ignoriert werden. Im Prinzip `host` geht es bei <> um die Hostkonfiguration, nicht um die Dienstkonfiguration, und sie wird geladen, bevor die Configure-Methode ausgeführt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren von Diensten mit Konfigurationsdateien](configuring-services-using-configuration-files.md)
- [Konfigurieren von Clientverhalten](configuring-client-behaviors.md)
- [Vereinfachte Konfiguration](simplified-configuration.md)
- [Konfiguration](./samples/configuration-sample.md)
- [Konfigurationsbasierte Aktivierung unter IIS und WAS](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [Konfiguration und Metadatenunterstützung](./extending/configuration-and-metadata-support.md)
- [Konfiguration](./diagnostics/exceptions-reference/configuration.md)
- [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](how-to-specify-a-service-binding-in-configuration.md)
- [Gewusst wie: Erstellen eines Dienstendpunkts in einer Konfiguration](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration](how-to-specify-a-client-binding-in-configuration.md)
