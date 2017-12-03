---
title: Entwickeln und Bereitstellen von WCF Data Services
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 87a074b96583f44e8655c9efde145e28b490f6e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="developing-and-deploying-wcf-data-services"></a>Entwickeln und Bereitstellen von WCF Data Services
Dieses Thema enthält Informationen zum Entwickeln und Bereitstellen von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Weitere grundlegende Informationen zu [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], finden Sie unter [Einstieg](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md) und [Übersicht](../../../../docs/framework/data/wcf/wcf-data-services-overview.md).  
  
## <a name="developing-wcf-data-services"></a>Entwickeln von WCF Data Services  
 Wenn Sie mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] einen Datendienst erstellen, der das [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]unterstützt, müssen Sie während der Entwicklung die folgenden grundlegenden Aufgaben ausführen:  
  
1.  **Definieren des Datenmodells**  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt eine Vielzahl von Datendienstanbietern, die es Ihnen ermöglichen, ein Datenmodell basierend auf Daten aus unterschiedlichen Datenquellen zu definieren, angefangen bei relationalen Datenbanken bis hin zu spät gebundenen Datentypen. Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
2.  **Erstellen des Datendiensts**  
  
     Der einfachste Datendienst macht eine Klasse, die von der <xref:System.Data.Services.DataService%601> -Klasse erbt, mit einem Typ `T` verfügbar, bei dem es sich um den namespacequalifizierten Namen des Entitätscontainers handelt. Weitere Informationen finden Sie unter [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Konfigurieren des Datendiensts**  
  
     Standardmäßig deaktiviert [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] den Zugriff auf die von einem Entitätscontainer verfügbar gemachten Ressourcen. Die <xref:System.Data.Services.DataServiceConfiguration> -Schnittstelle ermöglicht Ihnen das Konfigurieren des Zugriffs auf Ressourcen und Dienstvorgänge, das Angeben der unterstützten [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Version und das Definieren anderer dienstweiter Verhalten wie das Batchverarbeitungsverhalten oder die maximale Anzahl von Entitäten, die in einem einzelnen Antwortfeed zurückgegeben werden können. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Den Schwerpunkt dieses Themas bilden die Entwicklung und Bereitstellung von Datendiensten mithilfe von [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Informationen zur Flexibilität, die Ihnen [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] für das Verfügbarmachen der Daten als [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Feeds bietet, finden Sie unter [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
### <a name="choosing-a-development-web-server"></a>Auswählen eines Entwicklungswebservers  
 Wenn Sie einen WCF Data Service mithilfe von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] als [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung oder [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]-Website entwickeln, können Sie den Webserver auswählen, auf dem der Datendienst während der Entwicklung ausgeführt werden soll. Die folgenden Webserver sind in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] integriert, um das Testen und Debuggen der Datendienste auf dem lokalen Computer zu vereinfachen.  
  
1.  **Lokaler IIS-Server**  
  
     Wenn Sie einen Datendienst erstellen, bei dem es sich um eine unter Internetinformationsdienste (IIS) ausgeführte [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung oder [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Website handelt, sollten Sie den Datendienst mit IIS auf dem lokalen Computer entwickeln und testen. Die Ausführung des Datendiensts unter IIS erleichtert die Ablaufverfolgung von HTTP-Anforderungen während des Debuggens. Zudem können Sie so vorab die Rechte bestimmen, die IIS für den Zugriff auf Dateien, Datenbanken und andere für den Datendienst erforderliche Ressourcen erfordert. Für die Ausführung des Datendiensts unter IIS müssen IIS und [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] installiert und korrekt konfiguriert sein, und es muss Zugriff auf IIS-Konten im Dateisystem und Datenbanken gewährt werden. Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
    > [!NOTE]
    >  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] muss mit Administratorrechten ausgeführt werden, um die Konfiguration des lokalen IIS-Servers in der Entwicklungsumgebung zu ermöglichen.  
  
2.  **Visual Studio Development Server**  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] enthält einen integrierten Webserver, den [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Development Server, der der Standardwebserver für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Projekte ist. Dieser Webserver dient dazu, [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Projekte während der Entwicklung auf dem lokalen Computer auszuführen. Das Erstellen eines auf dem [Development Server ausgeführten Datendiensts wird unter](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) WCF Data Services-Schnellstart [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] beschrieben.  
  
     Beachten Sie die folgenden Einschränkungen, wenn Sie den [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Development Server zum Entwickeln eines Datendiensts verwenden:  
  
    -   Auf diesen Server kann nur auf dem lokalen Computer zugegriffen werden.  
  
    -   Dieser Server lauscht an `localhost` und an einem bestimmten Anschluss auf Nachrichten, nicht an Anschluss 80, dem Standardanschluss für HTTP-Nachrichten. Weitere Informationen finden Sie unter [Webserver in Visual Studio für ASP.NET-Webprojekte](http://msdn.microsoft.com/en-us/31d4f588-df59-4b7e-b9ea-e1f2dd204328).  
  
    -   Dieser Server führt den Datendienst im Kontext Ihres aktuellen Benutzerkontos aus. Wenn Sie z. B. als Administrator angemeldet sind, verfügt ein auf dem [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Development Server ausgeführter Datendienst über Administratorrechte. Dies kann dazu führen, dass der Datendienst auf Ressourcen zugreifen kann, für die er bei der Bereitstellung auf einem IIS-Server keine Zugriffsrechte besitzt.  
  
    -   Die zusätzlichen Funktionen von IIS sind auf diesem Server nicht verfügbar (z. B. die Authentifizierung).  
  
    -   Dieser Server kann keine aufgeteilten HTTP-Streams verarbeiten, die beim Zugriff auf umfassende Binärdaten vom Datendienst standardmäßig vom [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Client gesendet werden. Weitere Informationen finden Sie unter [Streaming Provider](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).  
  
    -   Auf diesem Server treten bei der Verarbeitung des Punkts (`.`) in einer URL Probleme auf, obwohl dieses Zeichen von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] in Schlüsselwerten unterstützt wird.  
  
    > [!TIP]
    >  Obwohl die Datendienste während der Entwicklung mit dem [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Development Server getestet werden können, sollten Sie sie nach der Bereitstellung auf einem Webserver mit IIS erneut testen.  
  
3.  **Microsoft Azure-Entwicklungsumgebung**  
  
     Die Windows Azure Tools für [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] enthalten einen integrierten Satz von Tools für die Entwicklung von Windows Azure-Diensten in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Mit diesen Tools können Sie einen Datendienst entwickeln, der unter Windows Azure bereitgestellt werden kann, und den Datendienst vor der Bereitstellung auf dem lokalen Computer testen. Verwenden Sie diese Tools, wenn Sie mit [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] einen auf der Windows Azure-Plattform ausgeführten Datendienst entwickeln. Sie können die Microsoft Azure-Tools für [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] aus dem [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=201848)herunterladen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Entwicklung eines Datendiensts, der auf Microsoft Azure ausgeführt wird finden Sie im Beitrag [Bereitstellen eines OData-Diensts in Windows Azure](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="development-tips"></a>Tipps für die Entwicklung  
 Beachten Sie beim Entwickeln eines Datendiensts die folgenden Hinweise:  
  
-   Bestimmen Sie die Sicherheitsanforderungen des Datendiensts, wenn Sie vorhaben, Benutzer zu authentifizieren oder den Zugriff für bestimmte Benutzer einzuschränken. Weitere Informationen finden Sie unter [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
-   Ein HTTP-Überprüfungsprogramm kann beim Debuggen eines Datendiensts hilfreich sein, da es Ihnen die Möglichkeit bietet, den Inhalt von Anforderungs- und Antwortnachrichten zu überprüfen. Zum Überprüfen von HTTP-Anforderungen an den Datendienst und HTTP-Antworten vom Datendienst kann eine beliebige Netzwerkpaketanalyse verwendet werden, die die Anzeige von Rohpaketen unterstützt.  
  
-   Beim Debuggen eines Datendiensts möchten Sie möglicherweise mehr Informationen zu einem Fehler vom Datendienst erhalten als während der normalen Ausführung. Sie können zusätzliche Fehlerinformationen vom Datendienst abrufen, indem Sie die <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> -Eigenschaft in der <xref:System.Data.Services.DataServiceConfiguration> auf `true` festlegen und die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> -Eigenschaft des <xref:System.ServiceModel.Description.ServiceDebugBehavior> -Attributs der Datendienstklasse auf `true`festlegen. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] im Beitrag [Debuggen von WCF Data Services](http://go.microsoft.com/fwlink/?LinkId=201868). Sie können auch die Ablaufverfolgung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aktivieren, um in der HTTP-Messagingebene ausgelöste Ausnahmen anzuzeigen. Weitere Informationen finden Sie unter [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
-   Ein Datendienst wird normalerweise als [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendungsprojekt entwickelt, Sie können den Datendienst in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] jedoch auch als [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]-Websiteprojekt erstellen. Informationen über die Unterschiede zwischen den zwei Projekttypen finden Sie unter [NIB: Vergleich von Webanwendungsprojekten und Websiteprojekten in Visual Studio](http://msdn.microsoft.com/en-us/2861815e-f5a2-4378-a2f8-b8a86dc012f5).  
  
-   Wenn Sie einen Datendienst mithilfe des Dialogfelds **Neues Element hinzufügen** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]erstellen, wird der Datendienst von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] in IIS gehostet. Dies ( [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] und IIS) ist zwar der Standardhost für einen Datendienst, es werden jedoch auch andere Hostingoptionen unterstützt. Weitere Informationen finden Sie unter [Hosting des Datendiensts](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md).  
  
## <a name="deploying-wcf-data-services"></a>Bereitstellen von WCF Data Services  
 Ein WCF Data Service bietet Flexibilität bei der Auswahl des Prozesses, von dem der Datendienst gehostet wird. Mit [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] können Sie einen Datendienst auf den folgenden Plattformen bereitstellen:  
  
-   **IIS-gehosteter Webserver**  
  
     Wenn ein Datendienst als [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Projekt entwickelt wird, kann es mit den standardmäßigen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Bereitstellungstechnologien auf einem IIS-Webserver bereitgestellt werden.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] stellt die folgenden Bereitstellungstechnologien für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]bereit, abhängig von der Art des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Projekts, das den Datendienst hostet, den Sie bereitstellen.  
  
    -   **Bereitstellungstechnologien für ASP.NET-Webanwendungen**  
  
        -   [Webbereitstellungspaket](http://msdn.microsoft.com/en-us/1f9713c8-9540-494c-b80d-9893b970ad6f)  
  
        -   [One-Click-Veröffentlichung](http://msdn.microsoft.com/en-us/59226246-99ad-4aec-975d-7c61e8a8911c)  
  
    -   **Bereitstellungstechnologien für ASP.NET-Websites**  
  
        -   [Tool "Website kopieren"](http://msdn.microsoft.com/library/b819aed4-014b-427e-be80-02317b1bb003)  
  
        -   [Tool "Website veröffentlichen"](http://msdn.microsoft.com/library/d0a1a20f-15be-4940-9485-cb8e4aa8181b)  
  
        -   [XCopy](http://msdn.microsoft.com/library/4312c651-2119-49be-bbeb-ee28bdbfe71e)  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu den Bereitstellungsoptionen für eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung finden Sie unter [Übersicht über die Bereitstellung von Webanwendungsprojekten für Visual Studio und ASP.NET](http://msdn.microsoft.com/en-us/99bd1927-b59f-4e02-87b4-55c6ba2adbc3).  
  
    > [!TIP]
    >  Bevor Sie versuchen, den Datendienst unter IIS bereitzustellen, muss die Bereitstellung auf einem Webserver mit IIS getestet werden. Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).  
  
-   **Windows Azure**  
  
     Sie können einen Datendienst mithilfe der Windows Azure Tools für [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]unter Windows Azure bereitstellen. Sie können die Microsoft Azure-Tools für [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] aus dem [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=201848)herunterladen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] das Bereitstellen eines Datendiensts unter Windows Azure finden Sie im Beitrag [Bereitstellen eines OData-Diensts in Windows Azure](http://go.microsoft.com/fwlink/?LinkId=201847).  
  
### <a name="deployment-considerations"></a>Überlegungen zur Bereitstellung  
 Beachten Sie beim Bereitstellen eines Datendiensts die folgenden Hinweise:  
  
-   Wenn Sie einen Datendienst bereitstellen, der den [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] -Anbieter verwendet, um auf eine SQL Server-Datenbank zuzugreifen, müssen Sie möglicherweise auch Datenstrukturen, Daten oder beides mit der Datendienstbereitstellung weitergeben. [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] kann zu diesem Zweck automatisch Skripts (SQL-Dateien) in der Zieldatenbank erstellen, die in das Webbereitstellungspaket einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Anwendung eingeschlossen werden können. Weitere Informationen finden Sie unter [NIB: Gewusst wie: Bereitstellen einer Datenbank mit einem Webanwendungsprojekt](http://msdn.microsoft.com/en-us/683b33f1-8a3d-45cf-af6e-61ab50fc518b). Bei einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Website kann für diese Aufgabe der **Datenbankveröffentlichungs-Assistent** in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]verwendet werden. Weitere Informationen finden Sie unter [Deploying a Database by Using the Database Publishing Wizard](http://msdn.microsoft.com/library/1e3682e7-8b57-4da6-a393-af9640ccf8b7).  
  
-   Da [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] eine einfache [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] -Implementierung enthält, können Sie Windows Server AppFabric verwenden, um einen unter IIS bereitgestellten Datendienst unter Windows Server zu überwachen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] das Überwachen eines Datendiensts mit Windows Server AppFabric finden Sie im Beitrag [Nachverfolgung von WCF Data Services mit Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=202005).  
  
## <a name="see-also"></a>Siehe auch  
 [Hosting des Datendiensts](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
