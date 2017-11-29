---
title: Hosten in einer verwalteten Anwendung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 30d531d436937bf5183ac0c28d59425ea71762e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="hosting-in-a-managed-application"></a>Hosten in einer verwalteten Anwendung
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] -Dienste können in jeder [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Anwendung gehostet werden. Die Selbsthosting-Option ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt. Sie ist jedoch auch die am wenigsten robuste Hostingoption, weil verwaltete Anwendungen nicht die erweiterten Hosting- und Verwaltungsfunktionen bereitstellen wie die anderen Hostingoptionen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], z.&amp;#160;B. Internetinformationsdienste (IIS) und Windows-Dienste.  
  
 Zur Erstellung eines selbst gehosteten Diensts erstellen und öffnen Sie eine Instanz von <xref:System.ServiceModel.ServiceHost>, der die Dienstüberwachung für Nachrichten startet. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Wie: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Ein vollständiges Beispiel zum Definieren eines Dienstvertrags, den Vertrag zu implementieren und Hosten eines Diensts innerhalb einer verwalteten Anwendung finden Sie unter der [Lernprogramm für erste Schritte](../../../../docs/framework/wcf/getting-started-tutorial.md) und [Selbsthosting](../../../../docs/framework/wcf/samples/self-host.md).  
  
 In den folgenden Abschnitten werden allgemeine Szenarien beschrieben, die diese Hostingoption verwenden.  
  
## <a name="console-applications"></a>Konsolenanwendungen  
 Allgemeine, für das Selbsthosting geeignete Szenarien sind [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienste, die in Konsolenanwendungen ausgeführt werden. Das Hosten eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Diensts in einer Konsolenanwendung ist in der Regel während der Entwicklungsphase der Anwendung nützlich. Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren.  
  
## <a name="rich-client-applications"></a>Rich Client-Anwendungen  
 Andere, für das Selbsthosting geeignete allgemeine Szenarien sind Rich&amp;#160;Client-Anwendungen wie jene, die auf [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] oder Windows&amp;#160;Forms (WinForms) basieren. Diese Hostingoption erleichtert es Rich&amp;#160;Client-Anwendungen, wie [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] - und WinForms-Anwendungen, mit der Außenwelt zu kommunizieren. Ein Beispiel dafür ist ein Peer-to-Peer-Kollaborationsclient, der [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] als Benutzeroberfläche nutzt und darüber hinaus als Host für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Dienst fungiert, der es anderen Clients ermöglicht, eine Verbindung mit ihm herzustellen und Daten auszutauschen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hosting-Dienste](../../../../docs/framework/wcf/hosting-services.md)  
 [Tutorial mit ersten Schritten](../../../../docs/framework/wcf/getting-started-tutorial.md)
