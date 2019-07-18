---
title: Hosten in einer verwalteten Anwendung
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: 1895f6622f7c528979badd741f5994970bbd1a8c
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169793"
---
# <a name="hosting-in-a-managed-application"></a>Hosten in einer verwalteten Anwendung
Windows Communication Foundation (WCF)-Dienste können in jeder .NET Framework-Anwendung gehostet werden. Die Selbsthosting-Option ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt. Es ist jedoch auch die am wenigsten robuste Hostingoption, da verwaltete Anwendungen keine erweiterten hosten und Verwaltungsfunktionen von anderen Hostingoptionen in WCF, z. B. Internet Information Services (IIS) und Windows-Dienste bereitstellen.  
  
 Zur Erstellung eines selbst gehosteten Diensts erstellen und öffnen Sie eine Instanz von <xref:System.ServiceModel.ServiceHost>, der die Dienstüberwachung für Nachrichten startet. Weitere Informationen finden Sie unter [Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Ein vollständiges Beispiel zum Definieren eines Dienstvertrags, den Vertrag zu implementieren und Hosten eines Diensts in einer verwalteten Anwendung finden Sie unter den [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md) und [Selbsthosting](../../../../docs/framework/wcf/samples/self-host.md).  
  
 In den folgenden Abschnitten werden allgemeine Szenarien beschrieben, die diese Hostingoption verwenden.  
  
## <a name="console-applications"></a>Konsolenanwendungen  
 Häufige Szenarien, die es Self-hosting ermöglicht sind WCF-Dienste, die in konsolenanwendungen ausgeführt. Hosten eines WCF-Diensts in einer Konsolenanwendung eignet sich in der Regel während der Entwicklungsphase des Diensts. Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren.  
  
## <a name="rich-client-applications"></a>Rich Client-Anwendungen  
 Andere allgemeine Szenarien, in denen Selbsthosting geeignete rich Client-Anwendungen, z. B. jene auf Grundlage von Windows Presentation Foundation (WPF) oder Windows Forms (WinForms) sind. Diese Hostingoption erleichtert auch die für rich Client-Anwendungen, z. B. WPF und WinForms-Anwendungen, für die Kommunikation mit der Außenwelt. Z. B. ein Peer-zu-Peer Zusammenarbeitsclient, der WPF für seine Benutzeroberfläche verwendet und auch hostet einen WCF-Dienst, der von anderen Clients herstellen und Informationen austauschen.  
  
## <a name="see-also"></a>Siehe auch

- [Hosting-Dienste](../../../../docs/framework/wcf/hosting-services.md)
- [Tutorial mit ersten Schritten](../../../../docs/framework/wcf/getting-started-tutorial.md)
