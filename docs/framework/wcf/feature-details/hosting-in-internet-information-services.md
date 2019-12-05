---
title: Hosten in Internetinformationsdiensten
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 8ea7602e82d13425bb678555dde1f44ccbbf5a0f
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837466"
---
# <a name="hosting-in-internet-information-services"></a>Hosten in Internetinformationsdiensten
Eine Option zum Hosting Windows Communication Foundation (WCF)-Dienste befindet sich in einer Internetinformationsdienste (IIS)-Anwendung. Dieses Hostingmodell ähnelt dem Modell, das von ASP.net-und ASP.NET-Webdiensten (ASMX) verwendet wird.  
  
## <a name="versions-of-iis"></a>Versionen von IIS  
 WCF kann auf den folgenden Versionen von IIS unter den folgenden Betriebssystemen gehostet werden:  
  
- IIS 5.1 unter [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Diese Umgebung ist nützlich für Entwurf und Entwicklung von IIS-gehosteten Anwendungen, die später unter einem Server-Betriebssystem, beispielsweise [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] bereitgestellt werden.  
  
- IIS 6,0 auf [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. IIS 6.0 bietet ein erweitertes Prozessmodell, das verbesserte Skalierbarkeit, Zuverlässigkeit und Anwendungsisolation bereitstellt. Diese Umgebung eignet sich für die Produktions Bereitstellung von WCF-Diensten, die ausschließlich HTTP-Kommunikation verwenden.  
  
- IIS 7,0 unter Windows Vista und [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. IIS 7,0 bietet dasselbe erweiterte Prozessmodell wie IIS 6,0, verwendet jedoch den Windows-Prozess Aktivierungs Dienst (was), um die Aktivierung und Netzwerkkommunikation über andere Protokolle als http zuzulassen. Diese Umgebung eignet sich für die Entwicklung von WCF-Diensten, die über alle von WCF unterstützten Netzwerkprotokolle kommunizieren (einschließlich http, net. TCP, net. Pipe und net. MSMQ). Weitere Informationen zu was finden Sie unter [Hosting in Windows Process Activation Service](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
- [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496) funktioniert mit IIS 7,0 und Windows Process Activation Service (was), um eine umfangreiche anwendungshostingumgebung für NET4 WCF-und WF-Dienste bereitzustellen. Vorteile sind u. a. die Verwaltung von Prozesslebenszyklen, die Prozesswiederverwendung, freigegebenes Hosting, rascher Ausfallschutz, Verwaisen von Prozessen, die Aktivierung bei Bedarf und die Systemüberwachung. Ausführliche Informationen finden Sie unter [AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=196494) und [AppFabric-hostingkonzepte](https://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Vorteile des IIS-Hosting  
 Das Hosting von WCF-Diensten in IIS bietet mehrere Vorteile:  
  
- WCF-Dienste, die in IIS gehostet werden, werden wie jede andere Art von IIS-Anwendung bereitgestellt und verwaltet, einschließlich ASP.NET-Anwendungen und ASMX.  
  
- IIS stellt Prozessaktivierung, Systemüberwachung und Wiederverwendungsfähigkeiten bereit, um die Zuverlässigkeit der gehosteten Anwendungen zu erhöhen.  
  
- Wie ASP.net können auch in ASP.NET gehostete WCF-Dienste das ASP.net Shared-Hostingmodell nutzen, bei dem sich mehrere Anwendungen in einem gemeinsamen Arbeitsprozess befinden, um die Server Dichte und die Skalierbarkeit zu verbessern.  
  
- In IIS gehostete WCF-Dienste verwenden das gleiche dynamische Kompilierungs Modell wie ASP.NET 2,0, das die Entwicklung und Bereitstellung gehosteter Dienste vereinfacht.  
  
 Bei der Entscheidung, WCF-Dienste in IIS zu hosten, ist es wichtig zu beachten, dass IIS 5,1 und IIS 6,0 ausschließlich auf die HTTP-Kommunikation beschränkt sind. Weitere Informationen zum Auswählen einer [Hostingumgebung](../../../../docs/framework/wcf/hosting-services.md)finden Sie unter Hosting-Dienste.  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Diensts  
 Das entwickeln und Bereitstellen eines IIS-gehosteten WCF-Dienstanbieter besteht aus den folgenden Aufgaben:  
  
- Stellen Sie sicher, dass IIS, ASP.net, WCF und die WCF-HTTP-Aktivierungs Komponente ordnungsgemäß installiert und registriert sind.  
  
- Erstellen Sie eine neue IIS-Anwendung, oder verwenden Sie eine vorhandene ASP.NET-Anwendung erneut.  
  
- Erstellen Sie eine SVC-Datei für den WCF-Dienst.  
  
- Bereitstellen der Dienstimplementierung für die IIS-Anwendung.  
  
- Konfigurieren Sie den WCF-Dienst.  
  
 Eine Erläuterung zu den einzelnen Aufgaben finden Sie unter Bereitstellen [eines Internetinformationsdienste gehosteten WCF-Dienstanbieter](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>WCF-Dienste und ASP.NET  
 WCF-Dienste können entweder parallel mit ASP.net oder im ASP.NET-Kompatibilitätsmodus gehostet werden, in dem Dienste in vollem Umfang von den Funktionen profitieren können, die von der ASP.NET-Webanwendungs Plattform bereitgestellt werden. Eine Erläuterung dieser Features finden Sie unter [WCF-Dienste und ASP.net](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erweitern des Hosting mit ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)
- [Bereitstellen eines von IIS gehosteten WCF-Diensts](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)
- [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [Bewährte Methoden für das Hosten in IIS (Internetinformationsdienste)](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [Konfigurieren von IIS 7.0 (Internetinformationsdienste) für Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)
- [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=201276)
