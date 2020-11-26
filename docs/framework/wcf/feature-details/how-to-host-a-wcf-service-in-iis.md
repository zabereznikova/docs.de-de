---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in IIS'
description: Erfahren Sie, wie Sie einen WCF-Dienst erstellen, der in Internetinformationsdienste (IIS) gehostet wird. Sie können IIS-Hosting nur mit einem HTTP-Transport verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: e0eb61e56b20eda6627030700b823042e07d10c9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244443"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a>Vorgehensweise: Hosten eines WCF-Diensts in IIS

In diesem Thema werden die grundlegenden Schritte beschrieben, die zum Erstellen eines in Internetinformationsdienste (IIS) gehosteten Windows Communication Foundation (WCF)-Dienstanbieter erforderlich sind. Es wird vorausgesetzt, dass Sie mit IIS vertraut sind und wissen, wie mithilfe des IIS-Verwaltungstools IIS-Anwendungen erstellt und verwaltet werden. Weitere Informationen zu IIS finden Sie unter [Internetinformationsdienste](https://www.iis.net/). Ein WCF-Dienst, der in der IIS-Umgebung ausgeführt wird, nutzt die IIS-Features, wie z. b. die Prozess Wiederverwendung, das Herunterfahren im Leerlauf, die Prozessüberwachung und die Nachrichten basierte Aktivierung. Diese Hostingoption erfordert, dass IIS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden. Sie können IIS-Hosting nur mit einem HTTP-Transport verwenden.  
  
 Weitere Informationen zur Interaktion von WCF und ASP.net finden Sie unter [WCF-Dienste und ASP.net](wcf-services-and-aspnet.md). Weitere Informationen zum Konfigurieren der Sicherheit finden Sie unter [Sicherheit](security.md).  
  
 Die Quell Kopie dieses Beispiels finden [Sie unter IIS-Hosting mithilfe von Inline Code](../samples/iis-hosting-using-inline-code.md).  
  
### <a name="to-create-a-service-hosted-by-iis"></a>So erstellen Sie einen von IIS gehosteten Dienst  
  
1. Vergewissern Sie sich, dass IIS installiert ist und auf dem Computer ausgeführt wird. Weitere Informationen zum Installieren und Konfigurieren von IIS finden Sie unter [Installieren und Konfigurieren von IIS 7,0](/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista) .  
  
2. Erstellen Sie einen neuen Ordner für die Anwendungs Dateien namens "IISHostedCalcService", stellen Sie sicher, dass ASP.net auf den Inhalt des Ordners zugreifen kann, und erstellen Sie mit dem IIS-Verwaltungs Tool eine neue IIS-Anwendung, die sich physisch in diesem Anwendungsverzeichnis befindet. Verwenden Sie "IISHostedCalc", wenn Sie einen Alias für das Anwendungsverzeichnis erstellen.  
  
3. Erstellen Sie eine neue Datei namens "service.svc" im Anwendungsverzeichnis. Bearbeiten Sie diese Datei, indem Sie das folgende-Element hinzufügen @ServiceHost .  
  
   ```aspx-csharp
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. Erstellen Sie im Stammverzeichnis der Anwendung das Unterverzeichnis App_Code.  
  
5. Erstellen Sie eine Codedatei namens "Service.svc" im Unterverzeichnis "App_Code".  
  
6. Fügen Sie am Anfang der Datei "Service.cs" die folgenden using-Anweisungen hinzu:  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. Fügen Sie nach den using-Anweisungen die folgende Namespacedeklaration hinzu.  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. Definieren Sie den Dienstvertrag in der Namespacedeklaration, wie im folgenden Code gezeigt.  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. Implementieren Sie den Dienstvertrag nach der Dienstvertragsdefinition, wie im folgenden Code gezeigt.  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. Erstellen Sie eine Datei namens "Web.config" im Anwendungsverzeichnis, und fügen Sie der Datei den folgenden Konfigurationscode hinzu. Zur Laufzeit verwendet die WCF-Infrastruktur die Informationen, um einen Endpunkt zu erstellen, mit dem Client Anwendungen kommunizieren können.  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     In diesem Beispiel werden die Endpunkte in der Konfigurationsdatei explizit angegeben. Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt. Weitere Informationen zu Standard Endpunkten, Bindungen und Verhaltensweisen finden Sie in der [vereinfachten Konfiguration](../simplified-configuration.md) und [vereinfachten Konfiguration für WCF-Dienste](../samples/simplified-configuration-for-wcf-services.md).  
  
11. Um sicherzustellen, dass der Dienst korrekt gehostet wird, öffnen Sie eine Instanz von Internet Explorer, und navigieren Sie zur URL des Diensts: `http://localhost/IISHostedCalc/Service.svc`  
  
## <a name="example"></a>Beispiel  

 Im Folgenden finden Sie eine vollständige Auflistung des Codes für den von IIS gehosteten Dienst.  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten in Internetinformationsdiensten](hosting-in-internet-information-services.md)
- [Hosting-Dienste](../hosting-services.md)
- [WCF-Dienste und ASP.NET](wcf-services-and-aspnet.md)
- [Security](security.md)
- [Windows Server AppFabric-Hostingfunktionen](/previous-versions/appfabric/ee677189(v=azure.10))
