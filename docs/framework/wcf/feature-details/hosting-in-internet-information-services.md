---
title: Hosten in Internetinformationsdiensten
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: baf13af39fe575a75f1304b21f3b4ad70dd370ab
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597318"
---
# <a name="host-in-internet-information-services"></a>In Internetinformationsdienste hosten

Eine Option zum Hosting Windows Communication Foundation (WCF)-Dienste befindet sich in einer Internetinformationsdienste (IIS)-Anwendung. Dieses Hostingmodell ähnelt dem Modell, das von ASP.net-und ASP.NET-Webdiensten (ASMX) verwendet wird.

## <a name="versions-of-iis"></a>Versionen von IIS

WCF kann auf den folgenden Versionen von IIS unter den folgenden Betriebssystemen gehostet werden:

- IIS 5,1 unter Windows XP SP2. Diese Umgebung ist nützlich für das Entwerfen und entwickeln von IIS-gehosteten Anwendungen, die später auf einem Server Betriebssystem wie Windows Server 2003 bereitgestellt werden.

- IIS 6.0 unter Windows Server 2003. IIS 6.0 bietet ein erweitertes Prozessmodell, das verbesserte Skalierbarkeit, Zuverlässigkeit und Anwendungsisolation bereitstellt. Diese Umgebung eignet sich für die Produktions Bereitstellung von WCF-Diensten, die ausschließlich HTTP-Kommunikation verwenden.

- IIS 7.0 unter Windows Vista und Windows Server 2008. IIS 7,0 bietet dasselbe erweiterte Prozessmodell wie IIS 6,0, verwendet jedoch den Windows-Prozess Aktivierungs Dienst (was), um die Aktivierung und Netzwerkkommunikation über andere Protokolle als http zuzulassen. Diese Umgebung eignet sich für die Entwicklung von WCF-Diensten, die über alle von WCF unterstützten Netzwerkprotokolle kommunizieren (einschließlich http, net. TCP, net. Pipe und net. MSMQ). Weitere Informationen zu was finden Sie unter [Hosting in Windows Process Activation Service](hosting-in-windows-process-activation-service.md).

- [Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10)) funktioniert mit IIS 7,0 und Windows Process Activation Service (was), um eine umfangreiche anwendungshostingumgebung für NET4 WCF-und WF-Dienste bereitzustellen. Vorteile sind u. a. die Verwaltung von Prozesslebenszyklen, die Prozesswiederverwendung, freigegebenes Hosting, rascher Ausfallschutz, Verwaisen von Prozessen, die Aktivierung bei Bedarf und die Systemüberwachung. Ausführliche Informationen finden Sie unter [AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10)) und [AppFabric-hostingkonzepte](https://docs.microsoft.com/previous-versions/appfabric/ee677371(v=azure.10)).

## <a name="benefits-of-iis-hosting"></a>Vorteile des IIS-Hosting

Das Hosting von WCF-Diensten in IIS bietet mehrere Vorteile:

- WCF-Dienste, die in IIS gehostet werden, werden wie jede andere Art von IIS-Anwendung bereitgestellt und verwaltet, einschließlich ASP.NET-Anwendungen und ASMX.

- IIS stellt Prozessaktivierung, Systemüberwachung und Wiederverwendungsfähigkeiten bereit, um die Zuverlässigkeit der gehosteten Anwendungen zu erhöhen.

- Wie ASP.net können auch in ASP.NET gehostete WCF-Dienste das ASP.net Shared-Hostingmodell nutzen, bei dem sich mehrere Anwendungen in einem gemeinsamen Arbeitsprozess befinden, um die Server Dichte und die Skalierbarkeit zu verbessern.

- In IIS gehostete WCF-Dienste verwenden das gleiche dynamische Kompilierungs Modell wie ASP.NET 2,0, das die Entwicklung und Bereitstellung gehosteter Dienste vereinfacht.

Bei der Entscheidung, WCF-Dienste in IIS zu hosten, ist es wichtig zu beachten, dass IIS 5,1 und IIS 6,0 ausschließlich auf die HTTP-Kommunikation beschränkt sind. Weitere Informationen zum Auswählen einer [Hostingumgebung](../hosting-services.md)finden Sie unter Hosting-Dienste.

## <a name="deploy-an-iis-hosted-wcf-service"></a>Bereitstellen eines IIS-gehosteten WCF-Dienstanbieter

Das entwickeln und Bereitstellen eines IIS-gehosteten WCF-Dienstanbieter besteht aus den folgenden Aufgaben:

- Stellen Sie sicher, dass IIS, ASP.net, WCF und die WCF-HTTP-Aktivierungs Komponente ordnungsgemäß installiert und registriert sind.

- Erstellen Sie eine neue IIS-Anwendung, oder verwenden Sie eine vorhandene ASP.NET-Anwendung erneut.

- Erstellen Sie eine SVC-Datei für den WCF-Dienst.

- Bereitstellen der Dienstimplementierung für die IIS-Anwendung.

- Konfigurieren Sie den WCF-Dienst.

Eine Erläuterung zu den einzelnen Aufgaben finden Sie unter Bereitstellen [eines Internetinformationsdienste gehosteten WCF-Dienstanbieter](deploying-an-internet-information-services-hosted-wcf-service.md).

## <a name="wcf-services-and-aspnet"></a>WCF-Dienste und ASP.net

WCF-Dienste können entweder parallel mit ASP.net oder im ASP.NET-Kompatibilitätsmodus gehostet werden, in dem Dienste in vollem Umfang von den Funktionen profitieren können, die von der ASP.NET-Webanwendungs Plattform bereitgestellt werden. Eine Erläuterung dieser Features finden Sie unter [WCF-Dienste und ASP.net](wcf-services-and-aspnet.md).

## <a name="see-also"></a>Weitere Informationen

- [Erweitern des Hosting mit ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md)
- [Bereitstellen eines IIS-gehosteten WCF-Diensts](deploying-an-internet-information-services-hosted-wcf-service.md)
- [WCF-Dienste und ASP.NET](wcf-services-and-aspnet.md)
- [Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten](internet-information-services-hosting-best-practices.md)
- [Konfigurieren von Internetinformationsdienste 7.0 für Windows Communication Foundation](configuring-iis-for-wcf.md)
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
