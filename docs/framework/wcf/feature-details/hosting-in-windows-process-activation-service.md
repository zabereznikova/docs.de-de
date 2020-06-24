---
title: Hosten in WAS (Windows Process Activation Service)
description: Informieren Sie sich darüber, wie die Aktivierung und Lebensdauer von Arbeitsprozessen verwaltet, die Anwendungen enthalten, die WCF-Dienste hosten.
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], WAS
ms.assetid: d2b9d226-15b7-41fc-8c9a-cb651ac20ecd
ms.openlocfilehash: 6b0b23c21762009341fd62c029431824dd26d6c3
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247259"
---
# <a name="hosting-in-windows-process-activation-service"></a>Hosten in WAS (Windows Process Activation Service)
Der Windows-Prozessaktivierungsdienst (Windows Process Activation Service, WAS) verwaltet die Aktivierung und Lebensdauer der Workerprozesse, die Anwendungen enthalten, die WCF-Dienste (Windows Communication Foundation) hosten. Das WAS-Prozessmodell generalisiert das IIS 6.0-Prozessmodell für den HTTP-Server, indem die Abhängigkeit von HTTP entfernt wird. Dadurch können WCF-Dienste sowohl HTTP-als auch nicht-HTTP-Protokolle, wie z. b. net. TCP, in einer Hostingumgebung verwenden, die Nachrichten basierte Aktivierung unterstützt und die Möglichkeit bietet, eine große Anzahl von Anwendungen auf einem bestimmten Computer zu hosten.  
  
 Weitere Informationen zum Aufbau eines WCF-Diensts, der in der was-Host Umgebung ausgeführt wird, finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in was](how-to-host-a-wcf-service-in-was.md).  
  
 Das WAS-Prozessmodell bietet verschiedene Funktionen, die ermöglichen, Anwendungen auf robustere, besser verwaltbare und ressourcenschonendere Weise zu hosten:  
  
- Nachrichtenbasierte Aktivierung von Anwendungen und Arbeitsprozessen. Anwendungen werden dynamisch gestartet und beendet, in Reaktion auf mithilfe von HTTP- und Nicht-HTTP-Netzwerkprotokollen eintreffende Arbeitselemente.  
  
- Robustes Wiederverwenden von Anwendungen und Arbeitsprozessen, um den Systemzustand laufender Anwendungen aufrechtzuerhalten.  
  
- Zentralisierte Anwendungskonfiguration und -verwaltung.  
  
- Ermöglicht Anwendungen, die Vorteile des IIS-Prozessmodells zu nutzen, ohne dass der Bereitstellungsaufwand einer vollständigen IIS-Installation erforderlich wäre.  
[Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff384253(v=azure.10)) funktioniert mit IIS 7,0 und Windows Process Activation Service (was), um eine umfangreiche anwendungshostingumgebung für NET4 WCF-und WF-Dienste bereitzustellen. Vorteile sind u. a. die Verwaltung von Prozesslebenszyklen, die Prozesswiederverwendung, freigegebenes Hosting, rascher Ausfallschutz, Verwaisen von Prozessen, die Aktivierung bei Bedarf und die Systemüberwachung. Ausführliche Informationen finden Sie unter [AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10)) und [AppFabric-hostingkonzepte](https://docs.microsoft.com/previous-versions/appfabric/ee677371(v=azure.10)).  
  
## <a name="elements-of-the-was-addressing-model"></a>Elemente des WAS-Adressierungsmodells  
 Anwendungen besitzen Uniform Resource Identifier (URI)-Adressen. Diese stellen die Codeeinheiten dar, deren Lebensdauer und Ausführungsumgebung vom Server verwaltet werden. Eine einzelne WAS-Serverinstanz kann viele verschiedene Anwendungen beherbergen. Server organisieren Anwendungen in Gruppen, die als *Sites*bezeichnet werden. Innerhalb einer Site sind die Anwendungen entsprechend der Struktur der URIs, die als ihre externen Adressen dienen, hierarchisch angeordnet.  
  
 Anwendungsadressen bestehen aus zwei Teilen: einem Basis-URI-Präfix und einer anwendungsspezifischen, relativen Adresse (Pfad), die zusammen die externe Adresse einer Anwendung ergeben. Das Basis-URI-Präfix wird aus der Sitebindung erstellt und für alle Anwendungen innerhalb dieser Site verwendet. Anwendungs Adressen werden dann mithilfe von anwendungsspezifischen Pfad Fragmenten (z. b. "/applicationOne") erstellt und an das Basis-URI-Präfix angehängt (z. b. "net. TCP://localhost"), um den vollständigen Anwendungs-URI zu erhalten.  
  
 In der folgenden Tabelle werden mehrere mögliche Adressierungsszenarien für WAS-Sites mit HTTP- und Nicht-HTTP-Sitebindungen gezeigt.  
  
|Szenario|Sitebindungen|Anwendungspfad|Basis-URIs der Anwendung|  
|--------------|-------------------|----------------------|---------------------------|  
|Nur HTTP|http: *: 80:\*|/appTwo|`http://localhost/appTwo/`|  
|Sowohl HTTP als auch Nicht-HTTP|http: *: 80:\*<br /><br /> NET. TCP: 808:\*|/appTwo|`http://localhost/appTwo/`<br />`net.tcp://localhost/appTwo/`|  
|Nur Nicht-HTTP|net.pipe: *|/appThree|`net.pipe://appThree/`|  
  
 Dienste und Ressourcen innerhalb einer Anwendung können ebenfalls adressiert werden. Innerhalb einer Anwendung werden Anwendungsressourcen mit zum Basisanwendungspfad relativen Adressen angesprochen. Nehmen Sie zum Beispiel an, eine Site auf einem Computer namens contoso.com verfügt über Sitebindungen sowohl für das HTTP- als auch das Net.TCP-Protokoll. Nehmen Sie weiter an, dass die Site eine Anwendung im Verzeichnis /Billing enthält, die den Dienst GetOrders.svc verfügbar macht. Wenn dann der Dienst GetOrders.svc einen Endpunkt mit der relativen Adresse SecureEndpoint verfügbar macht, kann der Dienstendpunkt über die beiden folgenden URIs angesprochen werden:  
  
- `http://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
- `net.tcp://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
  
## <a name="the-was-runtime"></a>Die WAS-Laufzeit  
 Anwendungen werden für die Zwecke der Adressierung und Verwaltung in Sites organisiert. Zur Laufzeit werden Anwendungen auch in Anwendungspools zusammengefasst. Ein Anwendungspool kann viele verschiedene Anwendungen vieler anderer Sites enthalten. Alle Anwendungen innerhalb eines Anwendungspools teilen sich einen Satz allgemeiner Laufzeiteigenschaften. Sie alle werden beispielsweise unter der gleichen Version der Common Language Runtime (CLR) ausgeführt und verwenden eine gemeinsame Prozessidentität. Jeder Anwendungspool entspricht einer Instanz eines Arbeitsprozesses (w3wp.exe). Jede innerhalb eines gemeinsamen Anwendungspools ausgeführte verwaltete Anwendung ist mittels einer CLR-AppDomain von anderen Anwendungen isoliert.  
  
## <a name="see-also"></a>Weitere Informationen

- [WAS-Aktivierungsarchitektur](was-activation-architecture.md)
- [Konfigurieren von WAS für die Verwendung mit WCF](configuring-the-wpa--service-for-use-with-wcf.md)
- [Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten](how-to-install-and-configure-wcf-activation-components.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in WAS](how-to-host-a-wcf-service-in-was.md)
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
