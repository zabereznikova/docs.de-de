---
title: Hosten in einer verwalteten Anwendung
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: c1f4d91994ba44407ff5c93dbd34aa0bdef9332b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591731"
---
# <a name="hosting-in-a-managed-application"></a>Hosten in einer verwalteten Anwendung
Windows Communication Foundation (WCF)-Dienste können in jeder .NET Framework-Anwendung gehostet werden. Die Selbsthosting-Option ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt. Es ist jedoch auch die am wenigsten robuste Hostingoption, da verwaltete Anwendungen keine erweiterten hosten und Verwaltungsfunktionen von anderen Hostingoptionen in WCF, z. B. Internet Information Services (IIS) und Windows-Dienste bereitstellen.  
  
 Zur Erstellung eines selbst gehosteten Diensts erstellen und öffnen Sie eine Instanz von <xref:System.ServiceModel.ServiceHost>, der die Dienstüberwachung für Nachrichten startet. Weitere Informationen finden Sie unter [Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Ein vollständiges Beispiel zum Definieren eines Dienstvertrags, den Vertrag zu implementieren und Hosten eines Diensts in einer verwalteten Anwendung finden Sie unter den [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md) und [Selbsthosting](../../../../docs/framework/wcf/samples/self-host.md).  
  
 In den folgenden Abschnitten werden allgemeine Szenarien beschrieben, die diese Hostingoption verwenden.  
  
## <a name="console-applications"></a>Konsolenanwendungen  
 Häufige Szenarien, die es Self-hosting ermöglicht sind WCF-Dienste, die in konsolenanwendungen ausgeführt. Hosten eines WCF-Diensts in einer Konsolenanwendung eignet sich in der Regel während der Entwicklungsphase des Diensts. Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren.  
  
## <a name="rich-client-applications"></a>Rich Client-Anwendungen  
 Andere allgemeine Szenarien, in denen Selbsthosting geeignete rich Client-Anwendungen, z. B. jene auf Grundlage von Windows Presentation Foundation (WPF) oder Windows Forms (WinForms) sind. Diese Hostingoption erleichtert es Rich&#160;Client-Anwendungen, wie [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] - und WinForms-Anwendungen, mit der Außenwelt zu kommunizieren. Beispielsweise ein Zusammenarbeitsclient-Peer-zu-Peer-, verwendet [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] für seine Benutzeroberfläche und hostet außerdem einen WCF-Dienst, der ermöglicht es anderen Clients, die dem Cache herstellen und Informationen austauschen.  
  
## <a name="see-also"></a>Siehe auch

- [Hosting-Dienste](../../../../docs/framework/wcf/hosting-services.md)
- [Tutorial mit ersten Schritten](../../../../docs/framework/wcf/getting-started-tutorial.md)
