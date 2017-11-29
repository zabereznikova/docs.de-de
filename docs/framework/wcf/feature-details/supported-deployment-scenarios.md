---
title: "Unterstützte Bereitstellungsszenarien"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 22dcace51b2c73193356450b4b210d1c1a899e28
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="supported-deployment-scenarios"></a>Unterstützte Bereitstellungsszenarien
Die Teilmenge der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] -Funktionen, die für die Verwendung in teilweise vertrauenswürdigen Anwendungen vorgesehen sind, sollen die Anforderungen einiger, aber nicht sämtlicher Szenarien für den Einsatz von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]erfüllen. Auf dem Server erfüllt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Anforderungen von gemeinsamen Hostanbietern auf Internetebene, die aus Sicherheitsgründen Anwendungen von Drittanbietern mit dem [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] -Berechtigungssatz für mittlere Vertrauenswürdigkeit ausführen. Auf dem Client soll die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Unterstützung für teilweise Vertrauenswürdigkeit die Anforderungen von Bereitstellungstechnologien erfüllen, wie etwa der [ClickOnce-Bereitstellung](http://go.microsoft.com/fwlink/?LinkId=83712) oder der XAML Browser Application-Technologie von [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)], die eine reibungslose und sichere Bereitstellung von Desktopanwendungen von nicht vertrauenswürdigen Sites ermöglichen.  
  
## <a name="minimum-permission-requirements"></a>Minimal erforderliche Berechtigungen  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt eine Teilmenge von Funktionen in Anwendungen, die unter einem der beiden folgenden benannten Standardberechtigungssätze ausgeführt werden:  
  
-   Berechtigungen für mittlere Vertrauenswürdigkeit  
  
-   Internetzonenberechtigungen  
  
 Der Versuch, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in teilweise vertrauenswürdigen Anwendungen mit strikteren Berechtigungen zu verwenden, kann zur Laufzeit zu Sicherheitsausnahmen führen.  
  
 Weitere Informationen zu den verschiedenen Funktionen, die von diesen Berechtigungssätzen unterstützt werden, finden Sie unter [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## <a name="partial-trust-on-the-server"></a>Teilweise Vertrauenswürdigkeit auf dem Server  
 Viele kommerzielle Anbieter von Hostingdiensten für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Webanwendungen verlangen, dass auf ihren Servern ausgeführte Anwendungen mit dem [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] -Berechtigungssatz für mittlere Vertrauenswürdigkeit ausgeführt werden. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste können in diesen Umgebungen ausgeführt, sofern sie verwenden die <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WebHttpBinding>, oder <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> mit Sicherheit auf Transportebene.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste, die in Hostumgebungen mit mittlerer Vertrauenswürdigkeit ausgeführt werden, können auch als Dienste der mittleren Ebene fungieren, indem sie in Reaktion auf Clientanforderungen Nachrichten an andere Server senden. Szenarien der mittleren Ebene werden auf dem Server unterstützt, wenn die Hostumgebung der Anwendung die geeignete <xref:System.Net.WebPermission> gewährt hat, damit diese ausgehende Anforderungen an den gewünschten Server senden kann.  
  
 Neben dem SOAP-Nachrichtenaustausch über eine der unterstützten SOAP-Bindungen unterstützt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auch die <xref:System.ServiceModel.WebHttpBinding> zur Erstellung von webdienstähnlichen Diensten in teilweise vertrauenswürdigen Anwendungen. Die [WCF Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md), [WCF Syndication](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), und [AJAX-Integration und JSON-Unterstützung](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) Funktionen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden in teilweiser Vertrauenswürdigkeit unterstützt.  
  
 Workflowdienste erfordern die Berechtigung "Volles Vertrauen" und können nicht in teilweise vertrauenswürdigen Anwendungen verwendet werden.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: verwenden mittlerer Vetrauenswürdigkeit in ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=84603).  
  
## <a name="partial-trust-on-the-client"></a>Teilweise Vertrauenswürdigkeit auf dem Client  
 Bestimmte Sicherheitsvorkehrungen müssen getroffen werden, wenn Code von nicht vertrauenswürdigen Internetsites heruntergeladen oder ausgeführt wird. Sowohl bei der [ClickOnce-Bereitstellung](http://go.microsoft.com/fwlink/?LinkId=83712) als auch der XBAP-Technologie (XAML Browser Application) von [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]wird teilweise Vertrauenswürdigkeit verwendet, um nicht vertrauenswürdigem Code eingeschränkte Berechtigungen zu erteilen.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann verwendet werden, um von teilweise vertrauenswürdigen Anwendungen aus, die über die [ClickOnce-Bereitstellung](http://go.microsoft.com/fwlink/?LinkId=83712) oder XBAP bereitgestellt wurden, mit Remoteservern zu kommunizieren. Der Berechtigungssatz für die Internetzone umfasst die <xref:System.Net.WebPermission> für den Ausgangshost. Dies ermöglicht es diesen Anwendungen, über eine der unterstützten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Bindungen mit ihrem Ursprungsserver zu kommunizieren (siehe [Partial Trust Feature Compatibility](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md)erfüllen.  
  
## <a name="see-also"></a>Siehe auch  
 [Codezugriffssicherheit](http://go.microsoft.com/fwlink/?LinkId=83717)  
 [Windows Presentation Foundation im Browser gehostete Anwendungen (Übersicht)](http://go.microsoft.com/fwlink/?LinkId=98397)  
 [Teilweise Vertrauenswürdigkeit](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 [Mittlere Vertrauensebene in ASP.Net](http://go.microsoft.com/fwlink/?LinkId=69328)
