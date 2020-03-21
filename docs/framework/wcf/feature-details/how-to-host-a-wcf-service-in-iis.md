---
title: 'Gewusst wie: Hosten eines WCF-Diensts in IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 580b380a6c6349c6a4efa26e3eefe38bd660fa1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184923"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a>Gewusst wie: Hosten eines WCF-Diensts in IIS
In diesem Thema werden die grundlegenden Schritte beschrieben, die zum Erstellen eines Windows Communication Foundation (WCF)-Dienstes erforderlich sind, der in Internetinformationsdiensten (Internet Information Services, IIS) gehostet wird. Es wird vorausgesetzt, dass Sie mit IIS vertraut sind und wissen, wie mithilfe des IIS-Verwaltungstools IIS-Anwendungen erstellt und verwaltet werden. Weitere Informationen zu IIS finden Sie unter [Internetinformationsdienste](https://www.iis.net/). Ein WCF-Dienst, der in der IIS-Umgebung ausgeführt wird, nutzt die IIS-Funktionen voll aus, z. B. Prozessrecycling, Herunterfahren im Leerlauf, Überwachung des Prozesszustands und nachrichtenbasierte Aktivierung. Diese Hostingoption erfordert, dass IIS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden. Sie können IIS-Hosting nur mit einem HTTP-Transport verwenden.  
  
 Weitere Informationen zur Interaktion zwischen WCF und ASP.NET finden Sie unter [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md). Weitere Informationen zum Konfigurieren der Sicherheit finden Sie unter [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md).  
  
 Die Quellkopie dieses Beispiels finden Sie unter [IIS-Hosting mit Inlinecode](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).  
  
### <a name="to-create-a-service-hosted-by-iis"></a>So erstellen Sie einen von IIS gehosteten Dienst  
  
1. Vergewissern Sie sich, dass IIS installiert ist und auf dem Computer ausgeführt wird. Weitere Informationen zum Installieren und Konfigurieren von IIS finden [Sie unter Installieren und Konfigurieren von IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)  
  
2. Erstellen Sie einen neuen Ordner für Ihre Anwendungsdateien mit dem Namen "IISHostedCalcService", stellen Sie sicher, dass ASP.NET Zugriff auf den Inhalt des Ordners hat, und verwenden Sie das IIS-Verwaltungstool, um eine neue IIS-Anwendung zu erstellen, die sich physisch in diesem Anwendungsverzeichnis befindet. Verwenden Sie "IISHostedCalc", wenn Sie einen Alias für das Anwendungsverzeichnis erstellen.  
  
3. Erstellen Sie eine neue Datei namens "service.svc" im Anwendungsverzeichnis. Bearbeiten Sie diese Datei, indem Sie das folgende @ServiceHost Element hinzufügen.  
  
   ```
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
  
10. Erstellen Sie eine Datei namens "Web.config" im Anwendungsverzeichnis, und fügen Sie der Datei den folgenden Konfigurationscode hinzu. Zur Laufzeit verwendet die WCF-Infrastruktur die Informationen, um einen Endpunkt zu erstellen, mit dem Clientanwendungen kommunizieren können.  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     In diesem Beispiel werden die Endpunkte in der Konfigurationsdatei explizit angegeben. Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt. Weitere Informationen zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie [unter Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
11. Um sicherzustellen, dass der Dienst korrekt gehostet wird, öffnen Sie eine Instanz von Internet Explorer, und navigieren Sie zur URL des Diensts: `http://localhost/IISHostedCalc/Service.svc`  
  
## <a name="example"></a>Beispiel  
 Im Folgenden finden Sie eine vollständige Auflistung des Codes für den von IIS gehosteten Dienst.  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten in Internetinformationsdiensten](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [Hosting-Dienste](../../../../docs/framework/wcf/hosting-services.md)
- [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
