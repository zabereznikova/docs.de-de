---
title: Hosten in Internetinformationsdiensten
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 588e069280afc369256fdbee0132f732348ffc37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-in-internet-information-services"></a>Hosten in Internetinformationsdiensten
Eine Möglichkeit zum Hosten von Windows Communication Foundation (WCF)-Dienste ist innerhalb einer Anwendung (Internet Information Services, IIS). Dieses Hostmodell ist dem Modell ähnlich, das von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]- und ASP.NET-Webdiensten (ASMX) verwendet wird.  
  
## <a name="versions-of-iis"></a>Versionen von IIS  
 WCF kann unter den folgenden Versionen von IIS unter den folgenden Betriebssystemen gehostet werden:  
  
-   IIS 5.1 unter [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Diese Umgebung ist nützlich für Entwurf und Entwicklung von IIS-gehosteten Anwendungen, die später unter einem Server-Betriebssystem, beispielsweise [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] bereitgestellt werden.  
  
-   [!INCLUDE[iis601](../../../../includes/iis601-md.md)] für [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] stellt ein erweitertes Prozessmodell bereit, das verbesserte Skalierbarkeit, Zuverlässigkeit und Anwendungsisolation bietet. Diese Umgebung ist geeignet für die produktionsbereitstellung von WCF-Diensten, die ausschließlich HTTP-Kommunikation verwenden.  
  
-   IIS&#160;7.0 unter [!INCLUDE[wv](../../../../includes/wv-md.md)] und [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. IIS&#160;7.0 bietet das gleiche erweiterte Prozessmodell wie [!INCLUDE[iis601](../../../../includes/iis601-md.md)], verwendet jedoch WAS (Windows Process Activation Service), um die Aktivierung und die Netzwerkkommunikation über andere Protokolle als HTTP zu ermöglichen. Diese Umgebung ist geeignet für die Entwicklung von WCF-Dienste, die für die Kommunikation über jedes Netzwerkprotokoll von WCF (z. B. HTTP, net.tcp, net.pipe und net.msmq) unterstützt. Weitere Informationen zu den WAS, finden Sie unter [Hosten in Windows Process Activation Service](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
-   [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) arbeitet mit [!INCLUDE[iisver](../../../../includes/iisver-md.md)] und Windows Process Activation Service (WAS) eine vielseitige anwendungshostingumgebung für NET4 WCF- und WF-Dienste bereitstellen. Vorteile sind u. a. die Verwaltung von Prozesslebenszyklen, die Prozesswiederverwendung, freigegebenes Hosting, rascher Ausfallschutz, Verwaisen von Prozessen, die Aktivierung bei Bedarf und die Systemüberwachung. Ausführliche Informationen finden Sie unter [AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=196494) und [AppFabric-Hostingkonzepte](http://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Vorteile des IIS-Hosting  
 Hosten von WCF-Diensten in IIS bietet mehrere Vorteile:  
  
-   In IIS gehostete WCF-Dienste werden bereitgestellt und verwaltet wie jeder andere Typ von IIS-Anwendung, einschließlich [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendungen und ASMX.  
  
-   IIS stellt Prozessaktivierung, Systemüberwachung und Wiederverwendungsfähigkeiten bereit, um die Zuverlässigkeit der gehosteten Anwendungen zu erhöhen.  
  
-   Wie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], WCF-Dienste gehostet werden, [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] nutzen die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] freigegebenen hosting-Modell, in denen mehrere Anwendungen, in einem gemeinsamen Arbeitsprozess für verbesserte Serverdichte und Skalierbarkeit befinden.  
  
-   In IIS gehostete WCF-Dienste verwenden das gleiche dynamische Kompilierungsmodell wie [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)], das die Entwicklung und Bereitstellung von gehosteten Diensten.  
  
 Wenn Sie zum Hosten von WCF-Diensten in IIS zu entscheiden, es ist wichtig, denken Sie daran, dass IIS 5.1 und [!INCLUDE[iis601](../../../../includes/iis601-md.md)] auf HTTP-Kommunikation beschränkt sind. Weitere Informationen zum Auswählen einer hostumgebung finden Sie unter [Hostingdienste](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts  
 Entwickeln und Bereitstellen eines IIS-gehosteten WCF-Diensts umfasst die folgenden Aufgaben:  
  
-   Stellen Sie sicher, dass IIS, ASP.NET, WCF und der WCF-HTTP-aktivierungskomponente ordnungsgemäß installiert und registriert sind.  
  
-   Erstellen einer neuen IIS-Anwendung oder Wiederverwenden einer vorhandenen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung.  
  
-   Erstellen Sie eine SVC-Datei für den WCF-Dienst.  
  
-   Bereitstellen der Dienstimplementierung für die IIS-Anwendung.  
  
-   Konfigurieren Sie den WCF-Dienst.  
  
 Eine Erläuterung der einzelnen Aufgaben, finden Sie unter [Bereitstellen eines WCF-Diensts (englischsprachig)](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>WCF-Dienste und ASP.NET  
 WCF-Dienste kann entweder Seite-an-Seite mit gehostet [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] oder im [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Kompatibilitätsmodus in der Dienste alle Vorteile der gebotenen Funktionen der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Webanwendungsplattform. Eine Erörterung dieser Features finden Sie unter [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern des Hosting mit ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 [Bereitstellen eines von IIS gehosteten WCF-Diensts](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)  
 [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [Bewährte Methoden für das Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Konfigurieren von IIS 7.0 (Internetinformationsdienste) für Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
