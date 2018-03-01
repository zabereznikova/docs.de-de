---
title: Hosten in WAS (Windows Process Activation Service)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hosting services [WCF], WAS
ms.assetid: d2b9d226-15b7-41fc-8c9a-cb651ac20ecd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 40122670c84f87590a31b79f39695e9626ea9883
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-in-windows-process-activation-service"></a>Hosten in WAS (Windows Process Activation Service)
Der Windows Process Activation Service (WAS) verwaltet die Aktivierung und Lebensdauer der Arbeitsprozesse, die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste hostende Anwendungen enthalten. Das WAS-Prozessmodell verallgemeinert das [!INCLUDE[iis601](../../../../includes/iis601-md.md)]-Prozessmodell für den HTTP-Server durch das Entfernen der Abhängigkeit von HTTP. Dies ermöglicht [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensten die Verwendung von HTTP- und Nicht-HTTP-Protokollen, beispielsweise Net.TCP, in einer Hostumgebung, die nachrichtenbasierte Aktivierung unterstützt und die Möglichkeit zum Hosten vieler Anwendungen auf einem bestimmten Computer bietet.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Erstellen einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in WAS ausgeführte Hostingumgebung Dienst finden Sie unter [wie: Hosten eines WCF-Diensts in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
 Das WAS-Prozessmodell bietet verschiedene Funktionen, die ermöglichen, Anwendungen auf robustere, besser verwaltbare und ressourcenschonendere Weise zu hosten:  
  
-   Nachrichtenbasierte Aktivierung von Anwendungen und Arbeitsprozessen. Anwendungen werden dynamisch gestartet und beendet, in Reaktion auf mithilfe von HTTP- und Nicht-HTTP-Netzwerkprotokollen eintreffende Arbeitsaufgaben.  
  
-   Robustes Wiederverwenden von Anwendungen und Arbeitsprozessen, um den Systemzustand laufender Anwendungen aufrechtzuerhalten.  
  
-   Zentralisierte Anwendungskonfiguration und -verwaltung.  
  
-   Ermöglicht Anwendungen, die Vorteile des IIS-Prozessmodells zu nutzen, ohne dass der Bereitstellungsaufwand einer vollständigen IIS-Installation erforderlich wäre.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]WAS-Features finden Sie unter [IIS 7.0 Beta: IIS 7.0-Webverwaltungs](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
 [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) arbeitet mit [!INCLUDE[iisver](../../../../includes/iisver-md.md)] und Windows Process Activation Service (WAS) eine vielseitige anwendungshostingumgebung für NET4 WCF- und WF-Dienste bereitstellen. Vorteile sind u. a. die Verwaltung von Prozesslebenszyklen, die Prozesswiederverwendung, freigegebenes Hosting, rascher Ausfallschutz, Verwaisen von Prozessen, die Aktivierung bei Bedarf und die Systemüberwachung. Ausführliche Informationen finden Sie unter [AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=196494) und [AppFabric-Hostingkonzepte](http://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="elements-of-the-was-addressing-model"></a>Elemente des WAS-Adressierungsmodells  
 Anwendungen besitzen Uniform Resource Identifier (URI)-Adressen. Diese stellen die Codeeinheiten dar, deren Lebensdauer und Ausführungsumgebung vom Server verwaltet werden. Eine einzelne WAS-Serverinstanz kann viele verschiedene Anwendungen beherbergen. Server zu organisieren, Anwendungen in Gruppen, genannt *Sites*. Innerhalb einer Site sind die Anwendungen entsprechend der Struktur der URIs, die als ihre externen Adressen dienen, hierarchisch angeordnet.  
  
 Anwendungsadressen bestehen aus zwei Teilen: einem Basis-URI-Präfix und einer anwendungsspezifischen, relativen Adresse (Pfad), die zusammen die externe Adresse einer Anwendung ergeben. Das Basis-URI-Präfix wird aus der Sitebindung erstellt und für alle Anwendungen innerhalb dieser Site verwendet. Anwendungsadressen werden anschließend erstellt, indem Sie anwendungsspezifische pfadfragmente (wie z. B. "/ ApplicationOne") und sie an der Basis-URI-Präfix (beispielsweise "Net. TCP://localhost") ankommen vollständiger Anwendungs-URI angefügt werden.  
  
 In der folgenden Tabelle werden mehrere mögliche Adressierungsszenarien für WAS-Sites mit HTTP- und Nicht-HTTP-Sitebindungen gezeigt.  
  
|Szenario|Sitebindungen|Anwendungspfad|Basis-URIs der Anwendung|  
|--------------|-------------------|----------------------|---------------------------|  
|Nur HTTP|http: *: 80:\*|/appTwo|http://localhost/appTwo/|  
|Sowohl HTTP als auch Nicht-HTTP|http: *: 80:\*<br /><br /> NET.TCP: 808:\*|/appTwo|http://localhost/appTwo/<br />net.tcp://localhost/appTwo/|  
|Nur Nicht-HTTP|net.pipe: *|/appThree|net.pipe://appThree/|  
  
 Dienste und Ressourcen innerhalb einer Anwendung können ebenfalls adressiert werden. Innerhalb einer Anwendung werden Anwendungsressourcen mit zum Basisanwendungspfad relativen Adressen angesprochen. Nehmen Sie zum Beispiel an, eine Site auf einem Computer namens contoso.com verfügt über Sitebindungen sowohl für das HTTP- als auch das Net.TCP-Protokoll. Nehmen Sie weiter an, dass die Site eine Anwendung im Verzeichnis /Billing enthält, die den Dienst GetOrders.svc verfügbar macht. Wenn dann der Dienst GetOrders.svc einen Endpunkt mit der relativen Adresse SecureEndpoint verfügbar macht, kann der Dienstendpunkt über die beiden folgenden URIs angesprochen werden:  
  
 http://contoso.com/Billing/GetOrders.svc/SecureEndpoint  
net.tcp://contoso.com/Billing/GetOrders.svc/SecureEndpoint  
  
## <a name="the-was-runtime"></a>Die WAS-Laufzeit  
 Anwendungen werden für die Zwecke der Adressierung und Verwaltung in Sites organisiert. Zur Laufzeit werden Anwendungen auch in Anwendungspools zusammengefasst. Ein Anwendungspool kann viele verschiedene Anwendungen vieler anderer Sites enthalten. Alle Anwendungen innerhalb eines Anwendungspools teilen sich einen Satz allgemeiner Laufzeiteigenschaften. Sie alle werden beispielsweise unter der gleichen Version der Common Language Runtime (CLR) ausgeführt und verwenden eine gemeinsame Prozessidentität. Jeder Anwendungspool entspricht einer Instanz eines Arbeitsprozesses (w3wp.exe). Jede innerhalb eines gemeinsamen Anwendungspools ausgeführte verwaltete Anwendung ist mittels einer CLR-AppDomain von anderen Anwendungen isoliert.  
  
## <a name="see-also"></a>Siehe auch  
 [WAS-Aktivierungsarchitektur](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)  
 [Konfigurieren von WAS für die Verwendung mit WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)  
 [How to: Host a WCF Service in IIS (Vorgehensweise: Hosten eines WCF-Diensts in WAS)](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
