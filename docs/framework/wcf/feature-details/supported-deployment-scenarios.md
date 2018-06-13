---
title: Unterstützte Bereitstellungsszenarien
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: d0afd12b1c17f9356146aa13c90f8db65ed9ec0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498061"
---
# <a name="supported-deployment-scenarios"></a>Unterstützte Bereitstellungsszenarien
Die Teilmenge der Windows Communication Foundation (WCF)-Funktionen, die für die Verwendung in teilweise vertrauenswürdigen Anwendungen unterstützt dient zum Erfüllen der Anforderungen einiger, aber nicht sämtlicher Szenarien für die Verwendung von WCF. Auf dem Server freigegeben WCF erfüllt die Anforderungen der Internetebene Hostinganbieter erhalten die Möglichkeit, die Anwendung eines Drittanbieters ausführen in den [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] mit mittlerer Vertrauenswürdigkeit Berechtigungssatz aus Sicherheitsgründen. Auf dem Client-Unterstützung für teilweise Vertrauenswürdigkeit WCF sollen die Anforderungen von bereitstellungstechnologien erfüllen zu können, wie etwa [ClickOnce-Bereitstellung](http://go.microsoft.com/fwlink/?LinkId=83712) oder [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]des XAML Browser Application-Technologie, mit der eine nahtlose und sichere zulassen Bereitstellung von desktopanwendungen von nicht vertrauenswürdigen Standorten.  
  
## <a name="minimum-permission-requirements"></a>Minimal erforderliche Berechtigungen  
 WCF unterstützt eine Teilmenge der Funktionen in Anwendungen, die unter einem der folgenden benannten Standardberechtigungssätze ausgeführt:  
  
-   Berechtigungen für mittlere Vertrauenswürdigkeit  
  
-   Internetzonenberechtigungen  
  
 Versuch WCF in teilweise vertrauenswürdigen Anwendungen mit strikteren Berechtigungen zu verwenden, kann zur Laufzeit zu Sicherheitsausnahmen führen.  
  
 Weitere Informationen zu den verschiedenen Funktionen, die von diesen Berechtigungssätzen unterstützt werden, finden Sie unter [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="partial-trust-on-the-server"></a>Teilweise Vertrauenswürdigkeit auf dem Server  
 Viele kommerzielle Anbieter von Hostingdiensten für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Webanwendungen verlangen, dass auf ihren Servern ausgeführte Anwendungen mit dem [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] -Berechtigungssatz für mittlere Vertrauenswürdigkeit ausgeführt werden. WCF-Dienste können in diesen Umgebungen ausgeführt, sofern sie verwenden die <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WebHttpBinding>, oder <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> mit Sicherheit auf Transportebene.  
  
 WCF-Dienste, die in Hostumgebungen mit mittlerer Vertrauenswürdigkeit ausgeführt können auch als Dienste der mittleren Ebene fungieren, durch das Senden von Nachrichten an andere Server in Reaktion auf Clientanforderungen. Szenarien der mittleren Ebene werden auf dem Server unterstützt, wenn die Hostumgebung der Anwendung die geeignete <xref:System.Net.WebPermission> gewährt hat, damit diese ausgehende Anforderungen an den gewünschten Server senden kann.  
  
 Neben dem SOAP-Nachrichtenaustausch über eine der unterstützten SOAP-Bindungen, WCF unterstützt die <xref:System.ServiceModel.WebHttpBinding> zur Erstellung von webdienstähnlichen Diensten in teilweise vertrauenswürdigen Anwendungen. Die [WCF Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), und [AJAX-Integration und JSON-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) Funktionen von WCF werden unter teilweiser Vertrauenswürdigkeit unterstützt.  
  
 Workflowdienste erfordern die Berechtigung "Volles Vertrauen" und können nicht in teilweise vertrauenswürdigen Anwendungen verwendet werden.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden der mittleren Vertrauensebene in ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=84603).  
  
## <a name="partial-trust-on-the-client"></a>Teilweise Vertrauenswürdigkeit auf dem Client  
 Bestimmte Sicherheitsvorkehrungen müssen getroffen werden, wenn Code von nicht vertrauenswürdigen Internetsites heruntergeladen oder ausgeführt wird. Sowohl bei der [ClickOnce-Bereitstellung](http://go.microsoft.com/fwlink/?LinkId=83712) als auch der XBAP-Technologie (XAML Browser Application) von [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]wird teilweise Vertrauenswürdigkeit verwendet, um nicht vertrauenswürdigem Code eingeschränkte Berechtigungen zu erteilen.  
  
 WCF kann verwendet werden, um die Kommunikation mit Remoteservern von teilweise vertrauenswürdigen Anwendungen bereitgestellt, indem entweder [ClickOnce-Bereitstellung](http://go.microsoft.com/fwlink/?LinkId=83712) oder XBAP. Der Berechtigungssatz der Internetzone umfasst <xref:System.Net.WebPermission> für den Ausgangshost Dies ermöglicht es diesen Anwendungen für die Kommunikation mit ihrem Ursprungsserver mit einer der unterstützten WCF-Bindungen, die in beschriebenen [Funktionskompatibilität für teilweise Vertrauenswürdigkeit ](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Codezugriffssicherheit](http://go.microsoft.com/fwlink/?LinkId=83717)  
 [Windows Presentation Foundation im Browser gehostete Anwendungen (Übersicht)](http://go.microsoft.com/fwlink/?LinkId=98397)  
 [Teilweise Vertrauenswürdigkeit](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 [Mittlere Vertrauensebene in ASP.Net](http://go.microsoft.com/fwlink/?LinkId=69328)
