---
title: "Erstellen meines ersten Ansprüche unterstützenden WCF-Diensts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: a27420609a6bcb6e30a351e4b84a899da9583d5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="building-my-first-claims-aware-wcf-service"></a>Erstellen meines ersten Ansprüche unterstützenden WCF-Diensts
## <a name="applies-to"></a>Gilt für  
  
-   Windows Identity Foundation (WIF)  
  
-   Windows Communication Foundation (WCF)  
  
## <a name="overview"></a>Übersicht  
 In diesem Thema wird beschrieben, wie Sie Ansprüche unterstützende WCF-Dienste mithilfe von WIF erstellen. In einem Ansprüche unterstützenden Webdienstszenario sind normalerweise drei Parteien beteiligt: der Webdienst selbst, der Endbenutzer und der Sicherheitstokendienst (STS). Die folgende Abbildung beschreibt dieses Szenario:  
  
 ![WIF Basic Claims Aware WCF Service (WIF grundlegende, Ansprüche unterstützende WCF-Dienste)](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")  
  
1.  Der WCF-Dienstclient (mitunter auch als Agent bezeichnet) verwendet WIF, um Anmeldeinformationen an den STS zu senden. Nach erfolgreicher Authentifizierung gibt der STS ein Token für den Agent aus.  
  
2.  Der Agent sendet dieses vom STS ausgegebene Token an den WCF-Dienst.  
  
3.  Der Ansprüche unterstützende WCF-Dienst wird so konfiguriert, dass er dem STS und den Token, die er ausgibt, vertraut. Der Ansprüche unterstützende WCF-Dienst verwendet WIF, um das Token zu überprüfen und zu analysieren. Entwickler verwenden die entsprechende WIF-API und -Typen wie **ClaimsPrincipal** für die Anforderungen der Anwendung, z.B. das Implementieren der entsprechenden Autorisierung.  
  
 Ab .NET 4.5 ist WIF Bestandteil von .NET Framework. Da die WIF-Klassen direkt im Framework selbst verfügbar sind, ist eine weitaus umfassendere Integration der anspruchsbasierten Identität in .NET möglich, sodass Ansprüche einfacher verwendet werden können. Mit WIF 4.5 müssen keine Out-of-Band-Komponenten installiert werden, um Ansprüche unterstützende Webanwendungen zu entwickeln. WIF-Klassen sind nun über mehrere Assemblys verteilt. Die wichtigsten Klassen hierbei sind System.Security.Claims, System.IdentityModel und System.IdentityModel.Services.  
  
 STS ist ein Dienst, der Token nach erfolgreicher Authentifizierung ausgibt. Microsoft bietet zwei STS-Dienste nach Industriestandard an:  
  
-   [Active Directory-Verbunddienste (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)  
  
-   [Windows Azure-Zugriffssteuerungsdienst (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).  
  
 AD FS 2.0 ist Bestandteil von Windows Server R2 und kann als STS für lokale Szenarien verwendet werden. Azure Active Directory Access Control (auch bekannt als Access Control Service oder ACS) ist ein Clouddienst, der als Bestandteil von Microsoft Azure angeboten wird. Zu Test- oder Schulungszwecken können Sie auch andere STS verwenden, um die Ansprüche unterstützenden Anwendungen zu erstellen. Beispielsweise können Sie den lokalen Entwicklungs-STS verwenden, der Teil des [Identitäts- und Zugriffs-Tools für Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) ist, welches kostenlos online erhältlich ist.  
  
 Informationen zum Erstellen Ihres ersten Ansprüche unterstützenden WCF-Diensts mithilfe von WIF finden Sie unter [Vorgehensweise: Erstellen eines Ansprüche unterstützenden WCF-Diensts mithilfe von WIF](http://msdn.microsoft.com/en-us/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte mit WIF](../../../docs/framework/security/getting-started-with-wif.md)
