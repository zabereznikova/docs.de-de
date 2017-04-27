---
title: "Gewusst wie: Hosten eines WCF-Diensts in IIS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Gewusst wie: Hosten eines WCF-Diensts in IIS
In diesem Thema werden die grundlegenden Schritte vorgestellt, die für die Erstellung eines in Internetinformationsdienste (IIS) gehosteten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Diensts erforderlich sind. Es wird vorausgesetzt, dass Sie mit IIS vertraut sind und wissen, wie mithilfe des IIS-Verwaltungstools IIS-Anwendungen erstellt und verwaltet werden. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]IIS finden Sie unter [Internet-Informationsdienste](http://go.microsoft.com/fwlink/?LinkId=132449) ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in der IIS-Umgebung ausgeführte Dienst nutzt die Vorteile des IIS-Features wie z. B. prozesswiederverwendung, Herunterfahren bei Leerlauf, prozessüberwachung und die Nachrichtenbasierte Aktivierung. Diese Hostingoption erfordert, dass IIS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden. Sie können IIS-Hosting nur mit einem HTTP-Transport verwenden.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interagieren, finden Sie unter [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]zum Konfigurieren der Sicherheit finden Sie unter [Security](../../../../docs/framework/wcf/feature-details/security.md).  
  
 Die Quellkopie dieses Beispiels, finden Sie unter [IIS-Hosting mithilfe von Inlinecode](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).  
  
### <a name="to-create-a-service-hosted-by-iis"></a>So erstellen Sie einen von IIS gehosteten Dienst  
  
1.  Vergewissern Sie sich, dass IIS installiert ist und auf dem Computer ausgeführt wird. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Installieren und Konfigurieren von IIS finden Sie unter [installieren und Konfigurieren von IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)  
  
2.  Erstellen Sie einen neuen Ordner namens "IISHostedCalcService" für die Anwendungsdateien, stellen Sie sicher, dass [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] auf den Inhalt des Ordners zugreifen kann, und verwenden Sie das IIS-Verwaltungstool, um eine neue IIS-Anwendung zu erstellen, die physisch in diesem Anwendungsverzeichnis gespeichert wird. Verwenden Sie "IISHostedCalc", wenn Sie einen Alias für das Anwendungsverzeichnis erstellen.  
  
3.  Erstellen Sie eine neue Datei namens "service.svc" im Anwendungsverzeichnis. Diese Datei bearbeiten, indem Sie Folgendes hinzufügen @ServiceHost Element.  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  Erstellen Sie im Stammverzeichnis der Anwendung das Unterverzeichnis App_Code.  
  
5.  Erstellen Sie eine Codedatei namens "Service.svc" im Unterverzeichnis "App_Code".  
  
6.  Fügen Sie am Anfang der Datei "Service.cs" die folgenden using-Anweisungen hinzu:  
  
    ```  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  Fügen Sie nach den using-Anweisungen die folgende Namespacedeklaration hinzu.  
  
    ```  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  Definieren Sie den Dienstvertrag in der Namespacedeklaration, wie im folgenden Code gezeigt.  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. Implementieren Sie den Dienstvertrag nach der Dienstvertragsdefinition, wie im folgenden Code gezeigt.  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. Erstellen Sie eine Datei namens "Web.config" im Anwendungsverzeichnis, und fügen Sie der Datei den folgenden Konfigurationscode hinzu. Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Infrastruktur verwendet diese Informationen, um einen Endpunkt zu erstellen, mit dem Clientanwendungen kommunizieren können.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <!-- This section is optional with the default configuration  
            model introduced in .NET Framework 4 -->  
          <service name="Microsoft.ServiceModel.Samples.CalculatorService">  
  
            <!-- This endpoint is exposed at the base address provided by host:                                        http://localhost/servicemodelsamples/service.svc  -->  
            <endpoint address=""  
                      binding="wsHttpBinding"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  
            <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->  
            <endpoint address="mex"  
                      binding="mexHttpBinding"  
                      contract="IMetadataExchange" />  
          </service>  
        </services>  
      </system.serviceModel>  
  
    </configuration>  
  
    ```  
  
     In diesem Beispiel werden die Endpunkte in der Konfigurationsdatei explizit angegeben. Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Standard-Endpunkte, Bindungen und Verhaltensweisen finden Sie unter [vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
11. Um sicherzustellen, dass der Dienst korrekt gehostet wird, öffnen Sie eine Instanz von Internet Explorer, und navigieren Sie zur URL des Diensts: `http://localhost/IISHostedCalc/Service.svc`  
  
## <a name="example"></a>Beispiel  
 Im Folgenden finden Sie eine vollständige Auflistung des Codes für den von IIS gehosteten Dienst.  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]  
  
 <!-- TODO: review snippet reference [!code[c_HowTo_HostInIIS#100](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  -->  
  
## <a name="see-also"></a>Siehe auch  
 [Hosting in IIS](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)   
 [Hosten von Diensten](../../../../docs/framework/wcf/hosting-services.md)   
 [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)   
 [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)   
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)