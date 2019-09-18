---
title: Erstellen meines ersten Ansprüche unterstützenden WCF-Diensts
ms.date: 03/30/2017
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
author: BrucePerlerMS
ms.openlocfilehash: 330d785721cb434f74ec746310a71bfd39fefd0b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045554"
---
# <a name="building-my-first-claims-aware-wcf-service"></a>Erstellen meines ersten Ansprüche unterstützenden WCF-Diensts
## <a name="applies-to"></a>Gilt für  
  
- Windows Identity Foundation (WIF)  
  
- Windows Communication Foundation (WCF)  
  
## <a name="overview"></a>Übersicht  
 In diesem Thema wird beschrieben, wie Sie Ansprüche unterstützende WCF-Dienste mithilfe von WIF erstellen. In einem Ansprüche unterstützenden Webdienstszenario sind normalerweise drei Parteien beteiligt: der Webdienst selbst, der Endbenutzer und der Sicherheitstokendienst (STS). Die folgende Abbildung beschreibt dieses Szenario:  
  
 ![Diagramm mit WIF-grundlegenden WCF-Dienst Komponenten, die auf Ansprüche achten](./media/building-my-first-claims-aware-wcf-service/windows-identify-foundation-basic-claims-aware-windows-communication-foundation-service.gif)  
  
1. Der WCF-Dienstclient (mitunter auch als Agent bezeichnet) verwendet WIF, um Anmeldeinformationen an den STS zu senden. Nach erfolgreicher Authentifizierung gibt der STS ein Token für den Agent aus.  
  
2. Der Agent sendet dieses vom STS ausgegebene Token an den WCF-Dienst.  
  
3. Der Ansprüche unterstützende WCF-Dienst wird so konfiguriert, dass er dem STS und den Token, die er ausgibt, vertraut. Der Ansprüche unterstützende WCF-Dienst verwendet WIF, um das Token zu überprüfen und zu analysieren. Entwickler verwenden die entsprechende WIF-API und -Typen wie **ClaimsPrincipal** für die Anforderungen der Anwendung, z.B. das Implementieren der entsprechenden Autorisierung.  
  
 Ab .NET 4.5 ist WIF Bestandteil von .NET Framework. Da die WIF-Klassen direkt im Framework selbst verfügbar sind, ist eine weitaus umfassendere Integration der anspruchsbasierten Identität in .NET möglich, sodass Ansprüche einfacher verwendet werden können. Mit WIF 4.5 müssen keine Out-of-Band-Komponenten installiert werden, um Ansprüche unterstützende Webanwendungen zu entwickeln. WIF-Klassen sind nun über mehrere Assemblys verteilt. Die wichtigsten Klassen hierbei sind System.Security.Claims, System.IdentityModel und System.IdentityModel.Services.  
  
 STS ist ein Dienst, der Token nach erfolgreicher Authentifizierung ausgibt. Microsoft bietet zwei STS-Dienste nach Industriestandard an:  
  
- [Active Directory-Verbunddienste (AD FS) (AD FS) 2,0](https://go.microsoft.com/fwlink/?LinkID=247516)
  
- [Windows Azure-Access Control Service (ACS)](https://docs.microsoft.com/previous-versions/azure/azure-services/hh147631(v=azure.100))
  
 AD FS 2.0 ist Bestandteil von Windows Server R2 und kann als STS für lokale Szenarien verwendet werden. Azure Active Directory Access Control (auch bekannt als Access Control Service oder ACS) ist ein Clouddienst, der als Bestandteil von Microsoft Azure angeboten wird. Zu Test- oder Schulungszwecken können Sie auch andere STS verwenden, um die Ansprüche unterstützenden Anwendungen zu erstellen. Beispielsweise können Sie den lokalen Entwicklungs-STS verwenden, der Teil des [Identitäts-und Zugriffs Tools für Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) ist, das kostenlos online verfügbar ist.  
  
 Informationen zum Erstellen Ihres ersten Ansprüche unterstützenden WCF-Dienstanbieter mithilfe [von WIF finden Sie unter Gewusst wie: Aktivieren Sie WIF für eine WCF-Webdienst Anwendung](how-to-enable-wif-for-a-wcf-web-service-application.md).
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit WIF](getting-started-with-wif.md)
