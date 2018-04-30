---
title: Hosten in Internetinformationsdiensten
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b933626c2f3f5ee7121d141d3704376efeb54ba5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="hosting-in-internet-information-services"></a>Hosten in Internetinformationsdiensten
Eine Option für das Hosten von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Diensten ist das Hosten innerhalb einer Internetinformationsdienste (IIS)-Anwendung. Dieses Hostmodell ist dem Modell ähnlich, das von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]- und ASP.NET-Webdiensten (ASMX) verwendet wird.  
  
## <a name="versions-of-iis"></a>Versionen von IIS  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann in folgenden Versionen von IIS unter folgenden Betriebssystemen gehostet werden:  
  
-   IIS 5.1 unter [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Diese Umgebung ist nützlich für Entwurf und Entwicklung von IIS-gehosteten Anwendungen, die später unter einem Server-Betriebssystem, beispielsweise [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] bereitgestellt werden.  
  
-   [!INCLUDE[iis601](../../../../includes/iis601-md.md)] für [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] stellt ein erweitertes Prozessmodell bereit, das verbesserte Skalierbarkeit, Zuverlässigkeit und Anwendungsisolation bietet. Diese Umgebung ist für die Produktionsbereitstellung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten geeignet, die ausschließlich HTTP-Kommunikation verwenden.  
  
-   IIS&#160;7.0 unter [!INCLUDE[wv](../../../../includes/wv-md.md)] und [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. IIS&#160;7.0 bietet das gleiche erweiterte Prozessmodell wie [!INCLUDE[iis601](../../../../includes/iis601-md.md)], verwendet jedoch WAS (Windows Process Activation Service), um die Aktivierung und die Netzwerkkommunikation über andere Protokolle als HTTP zu ermöglichen. Diese Umgebung ist für die Entwicklung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten geeignet, die über eines der von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützten Netzwerkprotokolle kommunizieren (HTTP, net.tcp, net.pipe und net.msmq). Weitere Informationen zu den WAS, finden Sie unter [Hosten in Windows Process Activation Service](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
-   [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) arbeitet mit [!INCLUDE[iisver](../../../../includes/iisver-md.md)] und Windows Process Activation Service (WAS) eine vielseitige anwendungshostingumgebung für NET4 WCF- und WF-Dienste bereitstellen. Vorteile sind u. a. die Verwaltung von Prozesslebenszyklen, die Prozesswiederverwendung, freigegebenes Hosting, rascher Ausfallschutz, Verwaisen von Prozessen, die Aktivierung bei Bedarf und die Systemüberwachung. Ausführliche Informationen finden Sie unter [AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=196494) und [AppFabric-Hostingkonzepte](http://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Vorteile des IIS-Hosting  
 Das Hosten von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten in IIS bietet mehrere Vorteile:  
  
-   In IIS gehostete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste werden auf die gleiche Weise bereitgestellt und verwaltet wie jeder andere Typ von IIS-Anwendungen, einschließlich [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendungen und ASMX.  
  
-   IIS stellt Prozessaktivierung, Systemüberwachung und Wiederverwendungsfähigkeiten bereit, um die Zuverlässigkeit der gehosteten Anwendungen zu erhöhen.  
  
-   Wie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Dienste können sich auch in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gehostete [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Dienste die Vorteile des freigegebenen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Hostmodells zunutze machen, bei dem sich mehrere Anwendungen für verbesserte Serverdichte und Skalierbarkeit in einem gemeinsamen Arbeitsprozess befinden.  
  
-   In IIS gehostete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste verwenden das gleiche dynamische Kompilierungsmodell wie [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)], das die Entwicklung und die Bereitstellung von gehosteten Diensten erleichtert.  
  
 Wenn Sie sich dafür entscheiden, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste in IIS zu hosten, müssen Sie unbedingt daran denken, dass IIS 5.1 und [!INCLUDE[iis601](../../../../includes/iis601-md.md)] auf HTTP-Kommunikation beschränkt sind. Weitere Informationen zum Auswählen einer hostumgebung finden Sie unter [Hostingdienste](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts  
 Das Entwickeln und Bereitstellen eines in IIS gehosteten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts umfasst die folgenden Aufgaben:  
  
-   Sicherstellen, dass IIS, ASP.NET, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-HTTP-Aktivierungskomponente ordnungsgemäß installiert und registriert sind.  
  
-   Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendung.  
  
-   Erstellen einer SVC-Datei für den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienst.  
  
-   Bereitstellen der Dienstimplementierung für die IIS-Anwendung.  
  
-   Konfigurieren des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Diensts.  
  
 Eine Erläuterung der einzelnen Aufgaben, finden Sie unter [Bereitstellen eines WCF-Diensts (englischsprachig)](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>WCF-Dienste und ASP.NET  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste können mit [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] entweder parallel oder im [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Kompatibilitätsmodus gehostet werden, in dem die Dienste alle Vorteile der von der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webanwendungsplattform gebotenen Funktionen nutzen können. Eine Erörterung dieser Features finden Sie unter [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern des Hosting mit ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 [Bereitstellen eines von IIS gehosteten WCF-Diensts](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)  
 [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [Bewährte Methoden für das Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Konfigurieren von IIS 7.0 (Internetinformationsdienste) für Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
