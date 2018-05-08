---
title: Hosten in einer verwalteten Anwendung
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: f374c199fb1982ab8854e41c0c8308f46451d9d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-in-a-managed-application"></a>Hosten in einer verwalteten Anwendung
Windows Communication Foundation (WCF)-Dienste gehostet werden können, in einem [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Anwendung. Die Selbsthosting-Option ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt. Es ist jedoch auch die am wenigsten robuste Hostingoption, weil verwaltete Anwendungen nicht die erweiterten Hosting- und Verwaltungsfunktionen von anderen Hostingoptionen in WCF, z. B. Internet Information Services (IIS) und Windows-Dienste bereitstellen.  
  
 Zur Erstellung eines selbst gehosteten Diensts erstellen und öffnen Sie eine Instanz von <xref:System.ServiceModel.ServiceHost>, der die Dienstüberwachung für Nachrichten startet. Weitere Informationen finden Sie unter [wie: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Ein vollständiges Beispiel zum Definieren eines Dienstvertrags, den Vertrag zu implementieren und Hosten eines Diensts innerhalb einer verwalteten Anwendung finden Sie unter der [Lernprogramm für erste Schritte](../../../../docs/framework/wcf/getting-started-tutorial.md) und [Selbsthosting](../../../../docs/framework/wcf/samples/self-host.md).  
  
 In den folgenden Abschnitten werden allgemeine Szenarien beschrieben, die diese Hostingoption verwenden.  
  
## <a name="console-applications"></a>Konsolenanwendungen  
 Allgemeine Szenarien, die es Selbsthosting ermöglicht sind WCF-Dienste, die in konsolenanwendungen ausgeführt. Hosten eines WCF-Diensts in einer Konsolenanwendung eignet sich in der Regel während der Entwicklungsphase des Diensts. Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren.  
  
## <a name="rich-client-applications"></a>Rich Client-Anwendungen  
 Weitere häufige Szenarien sind Selbsthosting rich Client-Anwendungen wie jene auf Grundlage von Windows Presentation Foundation (WPF) oder Windows Forms (WinForms). Diese Hostingoption erleichtert es Rich&amp;#160;Client-Anwendungen, wie [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] - und WinForms-Anwendungen, mit der Außenwelt zu kommunizieren. Z. B. eine Peer-zu-Peer Zusammenarbeitsclient, verwendet [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] für die Benutzeroberfläche und einen WCF-Dienst, der es anderen Clients zum Verbinden und Daten auszutauschen ermöglicht auch hostet.  
  
## <a name="see-also"></a>Siehe auch  
 [Hosting-Dienste](../../../../docs/framework/wcf/hosting-services.md)  
 [Tutorial mit ersten Schritten](../../../../docs/framework/wcf/getting-started-tutorial.md)
