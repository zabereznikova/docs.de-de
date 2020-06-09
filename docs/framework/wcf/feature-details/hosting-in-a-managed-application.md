---
title: Hosten in einer verwalteten Anwendung
ms.date: 03/30/2017
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
ms.openlocfilehash: 759257edf89d1af5c453bb98f41361b54cf113ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597344"
---
# <a name="hosting-in-a-managed-application"></a>Hosten in einer verwalteten Anwendung
Windows Communication Foundation (WCF)-Dienste können in jeder .NET Framework Anwendung gehostet werden. Die Selbsthosting-Option ist die flexibelste Option, da sie für die Bereitstellung die geringsten Anforderungen an die Infrastruktur stellt. Es ist jedoch auch die am wenigsten robuste Hostingoption, da verwaltete Anwendungen nicht die erweiterten Hosting-und Verwaltungsfunktionen anderer Hostingoptionen in WCF bereitstellen, wie z. b. Internetinformationsdienste (IIS) und Windows-Dienste.  
  
 Zur Erstellung eines selbst gehosteten Diensts erstellen und öffnen Sie eine Instanz von <xref:System.ServiceModel.ServiceHost>, der die Dienstüberwachung für Nachrichten startet. Weitere Informationen finden Sie unter Vorgehens [Weise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Ein umfassendes Beispiel zum Definieren eines Vertrags, zum Implementieren des Vertrags und zum Hosten eines Diensts in einer verwalteten Anwendung finden Sie im [Tutorial zu](../getting-started-tutorial.md) den ersten Schritten und dem [Self-Host](../samples/self-host.md).  
  
 In den folgenden Abschnitten werden allgemeine Szenarien beschrieben, die diese Hostingoption verwenden.  
  
## <a name="console-applications"></a>Konsolenanwendungen  
 Allgemeine Szenarien, die das Self-Hosting ermöglicht, sind WCF-Dienste, die in Konsolen Anwendungen ausgeführt werden. Das Hosting eines WCF-Diensts in einer Konsolenanwendung ist in der Regel während der Entwicklungsphase des Diensts hilfreich. Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren.  
  
## <a name="rich-client-applications"></a>Rich Client-Anwendungen  
 Andere gängige Szenarien, in denen das Self-Hosting aktiviert ist, sind Rich Client-Anwendungen, wie z. b. auf Windows Presentation Foundation (WPF) oder Windows Forms (WinForms). Diese Hostingoption erleichtert auch die Kommunikation von Rich Client-Anwendungen wie WPF-und WinForms-Anwendungen mit der Außenwelt. Beispielsweise ein Peer-to-Peer-Kollaborations Client, der WPF für die Benutzeroberfläche verwendet und außerdem einen WCF-Dienst hostet, der anderen Clients das Herstellen einer Verbindung mit dem Client und das Freigeben von Informationen ermöglicht.  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosting-Dienste](../hosting-services.md)
- [Tutorial zu den ersten Schritten](../getting-started-tutorial.md)
