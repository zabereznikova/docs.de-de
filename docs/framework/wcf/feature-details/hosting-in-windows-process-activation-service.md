---
title: Hosten in WAS (Windows Process Activation Service)
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], WAS
ms.assetid: d2b9d226-15b7-41fc-8c9a-cb651ac20ecd
ms.openlocfilehash: 5b234a00f3194fcf40a33d25302cff16d5999b05
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039376"
---
# <a name="hosting-in-windows-process-activation-service"></a>Hosten in WAS (Windows Process Activation Service)
Der Windows Process Activation Service (WAS) verwaltet die Aktivierung und Lebensdauer der Arbeitsprozesse, die Anwendungen, die Hostdienste Windows Communication Foundation (WCF) enthalten. Das WAS-Prozessmodell verallgemeinert das [!INCLUDE[iis601](../../../../includes/iis601-md.md)]-Prozessmodell für den HTTP-Server durch das Entfernen der Abhängigkeit von HTTP. Dadurch wird ein WCF-Diensten für die Verwendung von HTTP- und nicht-HTTP-Protokolle, z. B. Net.TCP, in einer hostumgebung, die Nachrichtenbasierte Aktivierung unterstützt und bietet die Möglichkeit, eine große Anzahl von Anwendungen auf einem bestimmten Computer hosten.  
  
 Weitere Informationen zum Erstellen eines WCF-Diensts, die in der WAS-hostumgebung ausgeführt wird, finden Sie unter [Vorgehensweise: Hosten eines WCF-Diensts in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
 Das WAS-Prozessmodell bietet verschiedene Funktionen, die ermöglichen, Anwendungen auf robustere, besser verwaltbare und ressourcenschonendere Weise zu hosten:  
  
- Nachrichtenbasierte Aktivierung von Anwendungen und Arbeitsprozessen. Anwendungen werden dynamisch gestartet und beendet, in Reaktion auf mithilfe von HTTP- und Nicht-HTTP-Netzwerkprotokollen eintreffende Arbeitselemente.  
  
- Robustes Wiederverwenden von Anwendungen und Arbeitsprozessen, um den Systemzustand laufender Anwendungen aufrechtzuerhalten.  
  
- Zentralisierte Anwendungskonfiguration und -verwaltung.  
  
- Ermöglicht Anwendungen, die Vorteile des IIS-Prozessmodells zu nutzen, ohne dass der Bereitstellungsaufwand einer vollständigen IIS-Installation erforderlich wäre.  
  
 Weitere Informationen zu WAS-Funktionen, finden Sie unter [IIS 7.0 Beta: IIS 7.0 Web Administration](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
 [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496) arbeitet mit [!INCLUDE[iisver](../../../../includes/iisver-md.md)] und Windows Process Activation Service (WAS) eine vielseitige anwendungshostingumgebung für NET4 WCF- und WF-Dienste bereitstellen. Vorteile sind u. a. die Verwaltung von Prozesslebenszyklen, die Prozesswiederverwendung, freigegebenes Hosting, rascher Ausfallschutz, Verwaisen von Prozessen, die Aktivierung bei Bedarf und die Systemüberwachung. Ausführliche Informationen finden Sie unter [AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=196494) und [AppFabric-Hostingkonzepte](https://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="elements-of-the-was-addressing-model"></a>Elemente des WAS-Adressierungsmodells  
 Anwendungen besitzen Uniform Resource Identifier (URI)-Adressen. Diese stellen die Codeeinheiten dar, deren Lebensdauer und Ausführungsumgebung vom Server verwaltet werden. Eine einzelne WAS-Serverinstanz kann viele verschiedene Anwendungen beherbergen. Server organisieren, Anwendungen in Gruppen, genannt *Websites*. Innerhalb einer Site sind die Anwendungen entsprechend der Struktur der URIs, die als ihre externen Adressen dienen, hierarchisch angeordnet.  
  
 Anwendungsadressen bestehen aus zwei Teilen: einem Basis-URI-Präfix und einer anwendungsspezifischen, relativen Adresse (Pfad), die zusammen die externe Adresse einer Anwendung ergeben. Das Basis-URI-Präfix wird aus der Sitebindung erstellt und für alle Anwendungen innerhalb dieser Site verwendet. Anwendungsadressen werden anschließend mithilfe einer anwendungsspezifischen Pfad-Fragmente erstellt (z. B. "/ ApplicationOne") und Anfügen an die Basis URI-Präfix (z. B. "Net. TCP://localhost") um den vollständigen Anwendungs-URI zu erreichen.  
  
 In der folgenden Tabelle werden mehrere mögliche Adressierungsszenarien für WAS-Sites mit HTTP- und Nicht-HTTP-Sitebindungen gezeigt.  
  
|Szenario|Sitebindungen|Anwendungspfad|Basis-URIs der Anwendung|  
|--------------|-------------------|----------------------|---------------------------|  
|Nur HTTP|http: *: 80:\*|/appTwo|http://localhost/appTwo/|  
|Sowohl HTTP als auch Nicht-HTTP|http: *: 80:\*<br /><br /> net.tcp: 808:\*|/appTwo|http://localhost/appTwo/<br />net.tcp://localhost/appTwo/|  
|Nur Nicht-HTTP|net.pipe: *|/appThree|net.pipe://appThree/|  
  
 Dienste und Ressourcen innerhalb einer Anwendung können ebenfalls adressiert werden. Innerhalb einer Anwendung werden Anwendungsressourcen mit zum Basisanwendungspfad relativen Adressen angesprochen. Nehmen Sie zum Beispiel an, eine Site auf einem Computer namens contoso.com verfügt über Sitebindungen sowohl für das HTTP- als auch das Net.TCP-Protokoll. Nehmen Sie weiter an, dass die Site eine Anwendung im Verzeichnis /Billing enthält, die den Dienst GetOrders.svc verfügbar macht. Wenn dann der Dienst GetOrders.svc einen Endpunkt mit der relativen Adresse SecureEndpoint verfügbar macht, kann der Dienstendpunkt über die beiden folgenden URIs angesprochen werden:  
  
- `http://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
- `net.tcp://contoso.com/Billing/GetOrders.svc/SecureEndpoint`
  
## <a name="the-was-runtime"></a>Die WAS-Laufzeit  
 Anwendungen werden für die Zwecke der Adressierung und Verwaltung in Sites organisiert. Zur Laufzeit werden Anwendungen auch in Anwendungspools zusammengefasst. Ein Anwendungspool kann viele verschiedene Anwendungen vieler anderer Sites enthalten. Alle Anwendungen innerhalb eines Anwendungspools teilen sich einen Satz allgemeiner Laufzeiteigenschaften. Sie alle werden beispielsweise unter der gleichen Version der Common Language Runtime (CLR) ausgeführt und verwenden eine gemeinsame Prozessidentität. Jeder Anwendungspool entspricht einer Instanz eines Arbeitsprozesses (w3wp.exe). Jede innerhalb eines gemeinsamen Anwendungspools ausgeführte verwaltete Anwendung ist mittels einer CLR-AppDomain von anderen Anwendungen isoliert.  
  
## <a name="see-also"></a>Siehe auch

- [WAS-Aktivierungsarchitektur](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [Konfigurieren von WAS für die Verwendung mit WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)
- [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=201276)
