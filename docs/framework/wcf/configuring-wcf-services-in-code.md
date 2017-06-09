---
title: "Konfigurieren von WCF-Diensten in Code | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Konfigurieren von WCF-Diensten in Code
Mit [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] können Entwickler Dienste mithilfe von Konfigurationsdateien oder Code konfigurieren.Konfigurationsdateien sind nützlich, wenn ein Dienst konfiguriert werden muss, nachdem er bereitgestellt wurde.Bei der Verwendung von Konfigurationsdateien muss ein IT\-Fachmann nur die Konfigurationsdatei aktualisieren, es ist keine Neukompilierung erforderlich.Konfigurationsdateien können jedoch komplex und schwierig sein zu warten.Es gibt keine Unterstützung zum Debuggen von Konfigurationsdateien. Konfigurationselemente werden durch Namen referenziert, was die Erstellung von Konfigurationsdateien fehleranfällig und schwierig macht.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ermöglicht auch das Konfigurieren von Diensten im Code.In früheren Versionen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(4.0 und früher\) was das Konfigurieren von Diensten im Code in selbstgehosteten Szenarien einfach, die <xref:System.ServiceModel.ServiceHost>\-Klasse ermöglichte es, Endpunkte und Verhalten vor dem Aufrufen von ServiceHost.Open zu konfigurieren.In webgehosteten Szenarien haben Sie jedoch keinen direkten Zugriff auf die <xref:System.ServiceModel.ServiceHost>\-Klasse.Um einen webgehosteten Dienst zu konfigurieren, mussten Sie eine <xref:System.ServiceModel.ServiceHostFactory> erstellen, die einen <xref:System.ServiceModel.ServiceHost> erstellte und jede erforderliche Konfiguration ausführte.Ab .NET 4.5 stellt [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] eine einfachere Möglichkeit bereit, um selbstgehostete und webgehostete Dienste im Code zu konfigurieren.  
  
## Die Configure\-Methode  
 Definieren Sie eine öffentliche statische Methode `Configure` mit der folgenden Signatur in der Dienstimplementierungsklasse:  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Die Configure\-Methode akzeptiert eine <xref:System.ServiceModel.ServiceConfiguration>\-Instanz, die den Entwicklern ermöglicht, Endpunkte und Verhalten hinzuzufügen.Diese Methode wird von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] aufgerufen, bevor der Diensthost geöffnet wird.Wenn sie definiert sind, werden alle Dienstkonfigurationseinstellungen in einer app.config\- oder web.config\-Datei ignoriert.  
  
 Der folgende Codeausschnitt zeigt, wie die `Configure`\-Methode definiert und ein Dienstendpunkt, ein Endpunktverhalten und Dienstverhalten hinzugefügt werden:  
  
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
  
 Um ein Protokoll wie HTTPS für einen Dienst zu aktivieren, können Sie entweder explizit einen Endpunkt hinzufügen, der das Protokoll verwendet, oder Sie können automatisch Endpunkte durch Aufrufen von ServiceConfiguration.EnableProtocol\(Binding\) hinzufügen. Dabei wird ein Endpunkt für jede Basisadresse, die mit dem Protokoll kompatibel ist, und für jeden definierten Dienstvertrag hinzugefügt.Der folgende Code veranschaulicht die Verwendung der ServiceConfiguration.EnableProtocol\-Methode:  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable “Add Service Reference” support   
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
  
 Die Einstellungen im \<`protocolMappings`\>\-Abschnitt werden nur verwendet, wenn keine Anwendungsendpunkte programmgesteuert zu <xref:System.ServiceModel.ServiceConfiguration> hinzugefügt werden. Sie können die Dienstkonfiguration aus der Standardanwendungskonfigurationsdatei optional laden, indem Sie <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> aufrufen und die Einstellungen dann ändern.Mit der <xref:System.ServiceModel.ServiceConfiguration>\-Klasse können Sie die Konfiguration auch aus einer zentralen Konfiguration laden.Im folgenden Code wird veranschaulicht, wie dies implementiert wird:  
  
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
>  Beachten Sie, dass <xref:System.ServiceModel.LoadFromConfiguration%2A> \<`host`\>\-Einstellungen im \<`service`\>\-Tag von \<`system.serviceModel`\> ignoriert.Im Prinzip bezieht sich \<`host`\> auf die Hostkonfiguration, nicht auf die Dienstkonfiguration, und wird geladen, bevor die Configure\-Methode ausgeführt wird.  
  
## Siehe auch  
 [Konfigurieren von Diensten mit Konfigurationsdateien](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)   
 [Konfigurieren von Clientverhalten](../../../docs/framework/wcf/configuring-client-behaviors.md)   
 [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md)   
 [Konfigurationsbasierte Aktivierung](../../../docs/framework/wcf/samples/configuration-based-activation.md)   
 [Konfiguration](../../../docs/framework/wcf/samples/configuration-sample.md)   
 [Konfigurationsbasierte Aktivierung unter IIS und WAS](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)   
 [Konfiguration und Metadatenunterstützung](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)   
 [Konfiguration](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)   
 [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)   
 [Gewusst wie: Erstellen eines Dienstendpunkts in einer Konfiguration](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)   
 [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)   
 [Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)