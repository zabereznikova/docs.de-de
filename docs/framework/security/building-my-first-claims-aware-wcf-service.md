---
title: "Erstellen des ersten Anspr&#252;che-unterst&#252;tzenden WCF-Dienstes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# Erstellen des ersten Anspr&#252;che-unterst&#252;tzenden WCF-Dienstes
## Gilt für  
  
-   Windows Identity Foundation \(WIF\)  
  
-   Windows Communication Foundation \(WCF\)  
  
## Übersicht  
 In diesem Thema wird beschrieben, wie Sie Ansprüche unterstützende WCF\-Dienste mithilfe von WIF erstellen.  In einem Ansprüche unterstützenden Webdienstszenario sind normalerweise drei Parteien beteiligt: der Webdienst selbst, der Endbenutzer und der Sicherheitstokendienst \(STS\).  Die folgende Abbildung beschreibt dieses Szenario:  
  
 ![WIF Basic Claims Aware WCF&#45;Dienst](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.png "WIFBasicClaimsAwareWCFService")  
  
1.  Der WCF\-Dienstclient \(mitunter auch als Agent bezeichnet\) verwendet WIF, um Anmeldeinformationen an den STS zu senden. Nach erfolgreicher Authentifizierung gibt der STS ein Token für den Agent aus.  
  
2.  Der Agent sendet dieses vom STS ausgegebene Token an den WCF\-Dienst.  
  
3.  Der Ansprüche unterstützende WCF\-Dienst wird so konfiguriert, dass er dem STS und den Token, die er ausgibt, vertraut.  Der Ansprüche unterstützende WCF\-Dienst verwendet WIF, um das Token zu überprüfen und zu analysieren.  Entwickler verwenden die entsprechende WIF\-API und Typen wie **ClaimsPrincipal** für die Anforderungen der Anwendung, z. B. Implementieren der entsprechenden Autorisierung.  
  
 Ab .NET 4.5 ist WIF Bestandteil von .NET Framework.  Da die WIF\-Klassen direkt im Framework selbst verfügbar sind, ist eine weitaus umfassendere Integration der anspruchsbasierten Identität in der .NET\-Plattform möglich, sodass Ansprüche einfacher verwendet werden können.  Mit WIF 4.5 müssen keine Out\-of\-Band\-Komponenten installiert werden, um Ansprüche unterstützende Webanwendungen zu entwickeln.  WIF\-Klassen sind nun über mehrere Assemblys verteilt. Die wichtigsten Klassen hierbei sind System.Security.Claims, System.IdentityModel und System.IdentityModel.Services.  
  
 STS ist ein Dienst, der Token nach erfolgreicher Authentifizierung ausgibt.  Microsoft bietet zwei STS\-Dienste nach Industriestandard an:  
  
-   [Active Directory\-Verbunddienste \(AD FS\) 247516](http://go.microsoft.com/fwlink/?LinkID=247516) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=247516\)  
  
-   [Microsoft Azure Access Control Service \(ACS\) 247516](http://go.microsoft.com/fwlink/?LinkID=247517) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=247517\).  
  
 AD FS 2.0 ist Bestandteil von Windows Server R2 und kann als STS für lokale Szenarien verwendet werden.  Azure Active Directory Access Control \(auch bekannt als Access Control Service oder ACS\) ist ein Clouddienst, der als Bestandteil von Microsoft Azure angeboten wird.  Zu Test\- oder Schulungszwecken können Sie auch andere STS verwenden, um die Ansprüche unterstützenden Anwendungen zu erstellen.  Beispielsweise können Sie den lokalen Entwicklungs\-STS verwenden, der Teil des [Identitäts\- und Zugriffs\-Tools für Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=245849\) ist, das kostenlos online erhältlich ist.  
  
 Informationen zum Erstellen Ihres ersten Ansprüche unterstützenden WCF\-Diensts mithilfe von WIF finden Sie unter [How To: Build Claims\-Aware WCF Service Using WIF](http://msdn.microsoft.com/de-de/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).  
  
## Siehe auch  
 [Erste Schritte mit WIF](../../../docs/framework/security/getting-started-with-wif.md)