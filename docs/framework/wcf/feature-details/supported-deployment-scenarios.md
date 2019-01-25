---
title: Unterstützte Bereitstellungsszenarien
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 605521cb91945812db178db3a82883b4d13bc636
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614483"
---
# <a name="supported-deployment-scenarios"></a>Unterstützte Bereitstellungsszenarien
Die Teilmenge der Windows Communication Foundation (WCF)-Funktionen, die für die Verwendung in teilweise vertrauenswürdigen Anwendungen unterstützt soll die Anforderungen der einige, aber nicht alle Szenarien für die Verwendung von WCF. Auf dem Server, freigegebenen WCF erfüllt die Anforderungen der internetweite Hostinganbieter, die Anwendung eines Drittanbieters ausführen in den [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] mittlere Vertrauenswürdigkeit Berechtigungssatz aus Sicherheitsgründen. Auf dem Client, Unterstützung von teilweiser Vertrauenswürdigkeit WCF soll die Anforderungen von bereitstellungstechnologien erfüllen zu können, wie etwa [ClickOnce-Bereitstellung](https://go.microsoft.com/fwlink/?LinkId=83712) oder [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]der XAML Browser Application-Technologie, die nahtlose und sichere zulassen Bereitstellung von desktopanwendungen von nicht vertrauenswürdigen Sites.  
  
## <a name="minimum-permission-requirements"></a>Minimal erforderliche Berechtigungen  
 WCF unterstützt eine Teilmenge von Funktionen in Anwendungen, die in eines der folgenden benannten Standardberechtigungssätze ausgeführt:  
  
-   Berechtigungen für mittlere Vertrauenswürdigkeit  
  
-   Internetzonenberechtigungen  
  
 Es wird versucht, WCF in teilweise vertrauenswürdigen Anwendungen mit strikteren Berechtigungen zu verwenden, kann zur Laufzeit zu Sicherheitsausnahmen führen.  
  
 Weitere Informationen zu den verschiedenen Funktionen, die von diesen Berechtigungssätzen unterstützt werden, finden Sie unter [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="partial-trust-on-the-server"></a>Teilweise Vertrauenswürdigkeit auf dem Server  
 Viele kommerzielle Anbieter von Hostingdiensten für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Webanwendungen verlangen, dass auf ihren Servern ausgeführte Anwendungen mit dem [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] -Berechtigungssatz für mittlere Vertrauenswürdigkeit ausgeführt werden. WCF-Dienste können in diesen Umgebungen ausführen, sofern sie verwenden die <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WebHttpBinding>, oder die <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> mit Sicherheit auf Transportebene.  
  
 WCF-Dienste in der mittleren Vertrauensebene Hostingumgebungen, können auch als Dienste der mittleren Ebene fungieren, durch Senden von Nachrichten an andere Server in Reaktion auf Clientanforderungen. Szenarien der mittleren Ebene werden auf dem Server unterstützt, wenn die Hostumgebung der Anwendung die geeignete <xref:System.Net.WebPermission> gewährt hat, damit diese ausgehende Anforderungen an den gewünschten Server senden kann.  
  
 Zusätzlich zu SOAP-Nachrichten mit einer der unterstützten SOAP-Bindungen, WCF unterstützt die <xref:System.ServiceModel.WebHttpBinding> für die Erstellung von webdienstähnlichen Diensten in teilweise vertrauenswürdigen Anwendungen. Die [WCF-HTTP-Webprogrammierungsmodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), und [AJAX-Integration und JSON-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) Funktionen von WCF werden alle bei teilweiser Vertrauenswürdigkeit unterstützt.  
  
 Workflowdienste erfordern die Berechtigung "Volles Vertrauen" und können nicht in teilweise vertrauenswürdigen Anwendungen verwendet werden.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden der mittleren Vertrauensebene in ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=84603).  
  
## <a name="partial-trust-on-the-client"></a>Teilweise Vertrauenswürdigkeit auf dem Client  
 Bestimmte Sicherheitsvorkehrungen müssen getroffen werden, wenn Code von nicht vertrauenswürdigen Internetsites heruntergeladen oder ausgeführt wird. Sowohl bei der [ClickOnce-Bereitstellung](https://go.microsoft.com/fwlink/?LinkId=83712) als auch der XBAP-Technologie (XAML Browser Application) von [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]wird teilweise Vertrauenswürdigkeit verwendet, um nicht vertrauenswürdigem Code eingeschränkte Berechtigungen zu erteilen.  
  
 WCF kann verwendet werden, um die Kommunikation mit Remoteservern von teilweise vertrauenswürdigen Anwendungen bereitgestellt, indem entweder [ClickOnce-Bereitstellung](https://go.microsoft.com/fwlink/?LinkId=83712) oder XBAP. Der Berechtigungssatz der Internetzone umfasst <xref:System.Net.WebPermission> für den Ausgangshost Dies ermöglicht es diesen Anwendungen für die Kommunikation mit ihrem Ursprungsserver, die mit einer der unterstützten WCF-Bindungen, die in beschriebenen [Partial Trust Feature Compatibility ](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="see-also"></a>Siehe auch
- [Codezugriffssicherheit](https://go.microsoft.com/fwlink/?LinkId=83717)
- [Übersicht über die im Browser gehostete Anwendungen von Windows Presentation Foundation](https://go.microsoft.com/fwlink/?LinkId=98397)
- [Teilweise Vertrauenswürdigkeit](../../../../docs/framework/wcf/feature-details/partial-trust.md)
- [Mittlere Vertrauensebene in ASP.Net](https://go.microsoft.com/fwlink/?LinkId=69328)
