---
title: Hosten in Internetinformationsdiensten
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 3940d8436ba5441d4e884879213a7a782214cb05
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486751"
---
# <a name="hosting-in-internet-information-services"></a>Hosten in Internetinformationsdiensten
Eine Möglichkeit zum Hosten von Windows Communication Foundation (WCF)-Diensten ist innerhalb einer Anwendung (Internet Information Services, IIS). Dieses Hostmodell ist ähnlich dem Modell, die von ASP.NET und Webdienste für ASP.NET Web Services (ASMX) verwendet.  
  
## <a name="versions-of-iis"></a>Versionen von IIS  
 WCF kann auf die folgenden Versionen von IIS unter den folgenden Betriebssystemen gehostet werden:  
  
- IIS 5.1 unter [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Diese Umgebung ist nützlich für Entwurf und Entwicklung von IIS-gehosteten Anwendungen, die später unter einem Server-Betriebssystem, beispielsweise [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] bereitgestellt werden.  
  
- IIS 6.0 unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. IIS 6.0 bietet ein erweitertes Prozessmodell, das verbesserte Skalierbarkeit, Zuverlässigkeit und Anwendungsisolation bietet. Diese Umgebung ist geeignet für die produktionsbereitstellung des WCF-Dienste, die ausschließlich HTTP-Kommunikation zu verwenden.  
  
- IIS&#160;7.0 unter [!INCLUDE[wv](../../../../includes/wv-md.md)] und [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. IIS 7.0 bietet dasselbe erweiterte Prozessmodell wie IIS 6.0, verwendet jedoch den Windows Process Activation Service (WAS) zum Aktivieren und die Netzwerkkommunikation über andere Protokolle als HTTP zu ermöglichen. Diese Umgebung ist geeignet für die Entwicklung von WCF-Dienste, die über eines der von WCF (einschließlich HTTP-, net.tcp, net.pipe und net.msmq) unterstützten Netzwerkprotokolle kommunizieren. Weitere Informationen zu WAS, finden Sie unter [Hosten in Windows Process Activation Service](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
- [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496) arbeitet mit IIS 7.0 und Windows Process Activation Service (WAS), um eine vielseitige anwendungshostingumgebung für NET4 WCF- und WF-Dienste bereitzustellen. Vorteile sind u. a. die Verwaltung von Prozesslebenszyklen, die Prozesswiederverwendung, freigegebenes Hosting, rascher Ausfallschutz, Verwaisen von Prozessen, die Aktivierung bei Bedarf und die Systemüberwachung. Ausführliche Informationen finden Sie unter [AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=196494) und [AppFabric-Hostingkonzepte](https://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Vorteile des IIS-Hosting  
 WCF-Dienste in IIS-Hosting hat mehrere Vorteile:  
  
- In IIS gehosteten WCF-Dienste bereitgestellt und verwaltet wie jeder andere Typ, der IIS-Anwendung, einschließlich von ASP.NET-Anwendungen und ASMX.  
  
- IIS stellt Prozessaktivierung, Systemüberwachung und Wiederverwendungsfähigkeiten bereit, um die Zuverlässigkeit der gehosteten Anwendungen zu erhöhen.  
  
- Wie ASP.NET, profitieren WCF-Dienste, die in ASP.NET gehostet von der freigegebenen Hostingmodell von ASP.NET befinden, in denen mehrere Anwendungen in einem gemeinsamen Arbeitsprozess für verbesserte Serverdichte und Skalierbarkeit.  
  
- In IIS gehosteten WCF-Dienste verwenden das gleiche dynamische Kompilierungsmodell wie ASP.NET 2.0 vereinfacht die Entwicklung und Bereitstellung von gehosteten Diensten.  
  
 Bei der Entscheidung zum Hosten von WCF-Diensten in IIS ist es wichtig zu beachten, dass IIS 5.1 und IIS 6.0 auf HTTP-Kommunikation beschränkt sind. Weitere Informationen zum Auswählen einer Hostingumgebung finden Sie unter [Hostingdienste](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts  
 Entwickeln und Bereitstellen eines IIS-gehosteten WCF-Diensts umfasst die folgenden Aufgaben:  
  
- Stellen Sie sicher, dass IIS, ASP.NET, WCF und der WCF-HTTP-aktivierungskomponente ordnungsgemäß installiert und registriert werden.  
  
- Erstellen einer neuen IIS‑Anwendung oder wiederverwenden einer vorhandenen ASP.NET-Anwendung.  
  
- Erstellen Sie eine SVC-Datei für den WCF-Dienst.  
  
- Bereitstellen der Dienstimplementierung für die IIS-Anwendung.  
  
- Konfigurieren Sie den WCF-Dienst.  
  
 Eine Erläuterung der einzelnen Aufgaben, finden Sie unter [Bereitstellen eines IIS-gehosteten WCF-Diensts](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>WCF-Dienste und ASP.NET  
 WCF-Dienste können sein, die entweder Seite-an-Seite mit ASP.NET oder im ASP.NET-Kompatibilitätsmodus in der Dienste Funktionen von der ASP.NET Web Anwendungsplattform ausnutzen können gehostet. Eine Beschreibung dieser Funktionen finden Sie unter [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erweitern des Hosting mit ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)
- [Bereitstellen eines von IIS gehosteten WCF-Diensts](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)
- [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [Bewährte Methoden für das Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [Konfigurieren von IIS 7.0 (Internetinformationsdienste) für Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)
- [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=201276)
