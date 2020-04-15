---
title: Entwickeln und Bereitstellen von WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: 4591175da5078a194bfe69884701e5432a0c38a3
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389728"
---
# <a name="develop-and-deploy-wcf-data-services"></a>Entwickeln und Bereitstellen von WCF-Datendiensten

Dieser Artikel enthält Informationen zum Entwickeln und Bereitstellen von WCF-Datendiensten. Weitere grundlegende Informationen zu WCF Data Services finden Sie unter [Erste Schritte](getting-started-with-wcf-data-services.md) und [Übersicht](wcf-data-services-overview.md).

## <a name="develop-wcf-data-services"></a>WCF Data Services entwickeln

Wenn Sie WCF Data Services zum Erstellen eines Datendienstes verwenden, der das Open Data Protocol (OData) unterstützt, müssen Sie während der Entwicklung die folgenden grundlegenden Aufgaben ausführen:

1. **Definieren des Datenmodells**

     WCF Data Services unterstützt eine Vielzahl von Datendienstanbietern, mit denen Sie ein Datenmodell basierend auf Daten aus einer Vielzahl von Datenquellen definieren können, von relationalen Datenbanken bis hin zu spät gebundenen Datentypen. Weitere Informationen finden Sie unter [Data Services Providers](data-services-providers-wcf-data-services.md).

2. **Erstellen des Datendiensts**

     Der einfachste Datendienst macht eine Klasse, die von der <xref:System.Data.Services.DataService%601> -Klasse erbt, mit einem Typ `T` verfügbar, bei dem es sich um den namespacequalifizierten Namen des Entitätscontainers handelt. Weitere Informationen finden Sie unter [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Konfigurieren des Datendiensts**

     Standardmäßig deaktiviert WCF Data Services den Zugriff auf Ressourcen, die von einem Entitätscontainer verfügbar gemacht werden. Die <xref:System.Data.Services.DataServiceConfiguration> Schnittstelle ermöglicht es Ihnen, den Zugriff auf Ressourcen und Dienstvorgänge zu konfigurieren, die unterstützte Version von OData anzugeben und andere dienstweite Verhaltensweisen zu definieren, z. B. Batchverhalten oder die maximale Anzahl von Entitäten, die in einem einzelnen Antwortfeed zurückgegeben werden können. Weitere Informationen finden Sie unter [Konfigurieren des Datendienstes](configuring-the-data-service-wcf-data-services.md).

Dieser Artikel behandelt in erster Linie die Entwicklung und Bereitstellung von Datendiensten mithilfe von Visual Studio. Informationen zur Flexibilität von WCF Data Services für die Offenlegung Ihrer Daten als OData-Feeds finden Sie unter [Definieren von WCF Data Services](defining-wcf-data-services.md).

### <a name="choose-a-development-web-server"></a>Auswählen eines Entwicklungswebservers

Wenn Sie einen WCF-Datendienst als ASP.NET Anwendung oder ASP.NET Website mithilfe von Visual Studio 2015 entwickeln, haben Sie die Wahl zwischen Webservern, auf denen der Datendienst während der Entwicklung ausgeführt werden soll. Die folgenden Webserver werden in Visual Studio integriert, um das Testen und Debuggen der Datendienste auf dem lokalen Computer zu vereinfachen.

1. **Lokaler IIS-Server**

     Wenn Sie einen Datendienst erstellen, der eine ASP.NET Anwendung oder ASP.NET Website ist, die auf Internetinformationsdiensten (Internet Information Services, IIS) ausgeführt wird, wird empfohlen, dass Sie den Datendienst mithilfe von IIS auf dem lokalen Computer entwickeln und testen. Die Ausführung des Datendiensts unter IIS erleichtert die Ablaufverfolgung von HTTP-Anforderungen während des Debuggens. Zudem können Sie so vorab die Rechte bestimmen, die IIS für den Zugriff auf Dateien, Datenbanken und andere für den Datendienst erforderliche Ressourcen erfordert. Stellen Sie zum Ausführen des Datendienstes auf IIS sicher, dass sowohl IIS als auch Windows Communication Foundation (WCF) ordnungsgemäß installiert und konfiguriert sind, und gewähren Sie Zugriff auf IIS-Konten im Dateisystem und in datenbanken. Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

    > [!NOTE]
    > Sie müssen Visual Studio mit Administratorrechten ausführen, damit die Entwicklungsumgebung den lokalen IIS-Server konfigurieren kann.

2. **Visual Studio Development Server**

     Visual Studio enthält einen integrierten Webserver, den Visual Studio Development Server, der der Standardwebserver für ASP.NET Projekte ist. Dieser Webserver wurde entwickelt, um ASP.NET Projekte während der Entwicklung auf dem lokalen Computer auszuführen. Der [WCF Data Services-Schnellstart](quickstart-wcf-data-services.md) zeigt, wie ein Datendienst erstellt wird, der im Visual Studio Development Server ausgeführt wird.

     Beachten Sie die folgenden Einschränkungen, wenn Sie Visual Studio Development Server zum Entwickeln des Datendienstes verwenden:

    - Auf diesen Server kann nur auf dem lokalen Computer zugegriffen werden.

    - Dieser Server lauscht an `localhost` und an einem bestimmten Anschluss auf Nachrichten, nicht an Anschluss 80, dem Standardanschluss für HTTP-Nachrichten. Weitere Informationen finden Sie unter [Webserver in Visual Studio für ASP.NET-Webprojekte](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).

    - Dieser Server führt den Datendienst im Kontext Ihres aktuellen Benutzerkontos aus. Wenn Sie beispielsweise als Benutzer auf Administratorebene ausgeführt werden, verfügt ein Datendienst, der im Visual Studio Development Server ausgeführt wird, über Berechtigungen auf Administratorebene. Dies kann dazu führen, dass der Datendienst auf Ressourcen zugreifen kann, für die er bei der Bereitstellung auf einem IIS-Server keine Zugriffsrechte besitzt.

    - Die zusätzlichen Funktionen von IIS sind auf diesem Server nicht verfügbar (z. B. die Authentifizierung).

    - Dieser Server kann keine geblockten HTTP-Streams verarbeiten, die standardmäßig vom WCF Data Services-Client gesendet werden, wenn er auf große Binärdaten vom Datendienst zugreift. Weitere Informationen finden Sie unter [Streaming Provider](streaming-provider-wcf-data-services.md).

    - Dieser Server hat Probleme bei`.`der Verarbeitung des Zeitraums ( ) in einer URL, obwohl dieses Zeichen von WCF Data Services in Schlüsselwerten unterstützt wird.

    > [!TIP]
    > Obwohl Sie Visual Studio Development Server verwenden können, um Ihre Datendienste während der Entwicklung zu testen, sollten Sie sie nach der Bereitstellung auf einem Webserver, auf dem IIS ausgeführt wird, erneut testen.

3. **Microsoft Azure-Entwicklungsumgebung**

     Windows Azure Tools für Visual Studio enthält einen integrierten Satz von Tools zum Entwickeln von Windows Azure-Diensten in Visual Studio. Mit diesen Tools können Sie einen Datendienst entwickeln, der unter Windows Azure bereitgestellt werden kann, und den Datendienst vor der Bereitstellung auf dem lokalen Computer testen. Verwenden Sie diese Tools, wenn Sie Visual Studio verwenden, um einen Datendienst zu entwickeln, der auf der Windows Azure-Plattform ausgeführt wird. Informationen zum Installieren der Tools finden Sie unter [Azure-Tools für Visual Studio 2015](../../../azure/sdk/vs2015-install.md). Weitere Informationen zum Entwickeln eines Datendienstes, der unter Windows Azure ausgeführt wird, finden Sie im Beitrag [Bereitstellen eines OData-Dienstes in Windows Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="development-tips"></a>Tipps für die Entwicklung

Berücksichtigen Sie beim Entwickeln eines Datendienstes Folgendes:

- Wenn Sie beabsichtigen, Benutzer zu authentifizieren oder den Zugriff für bestimmte Benutzer einzuschränken, legen Sie die Sicherheitsanforderungen Ihres Datendienstes fest. Weitere Informationen finden Sie unter [Securing WCF Data Services](securing-wcf-data-services.md).

- Ein HTTP-Inspektionsprogramm kann beim Debuggen eines Datendienstes hilfreich sein, indem Es Ihnen ermöglicht, den Inhalt von Anforderungs- und Antwortnachrichten zu überprüfen. Zum Überprüfen von HTTP-Anforderungen an den Datendienst und HTTP-Antworten vom Datendienst kann eine beliebige Netzwerkpaketanalyse verwendet werden, die die Anzeige von Rohpaketen unterstützt.

- Beim Debuggen eines Datendienstes möchten Sie möglicherweise mehr Informationen über einen Fehler vom Datendienst abrufen als während des regulären Betriebs. Sie können zusätzliche Fehlerinformationen vom Datendienst abrufen, indem Sie die <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> -Eigenschaft in der <xref:System.Data.Services.DataServiceConfiguration> auf `true` festlegen und die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> -Eigenschaft des <xref:System.ServiceModel.Description.ServiceDebugBehavior> -Attributs der Datendienstklasse auf `true`festlegen. Weitere Informationen finden Sie im Beitrag [Debugging WCF Data Services](https://docs.microsoft.com/archive/blogs/phaniraj/debugging-wcf-data-services). Sie können die Ablaufverfolgung in WCF auch aktivieren, um Ausnahmen anzuzeigen, die im HTTP-Messaging-Layer ausgelöst wurden. Weitere Informationen finden Sie unter [Configuring Tracing](../../wcf/diagnostics/tracing/configuring-tracing.md).

- Ein Datendienst wird in der Regel als ASP.NET Anwendungsprojekt entwickelt, aber Sie können auch den Datendienst als ASP.NET Websiteprojekts in Visual Studio erstellen. Informationen zu den Unterschieden zwischen den beiden Projekttypen finden Sie unter [Webanwendungsprojekte im Vergleich zu Websiteprojekten in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd547590(v=vs.110)).

- Wenn Sie einen Datendienst mithilfe des Dialogfelds **Neues Element hinzufügen** in Visual Studio erstellen, wird der Datendienst von ASP.NET in IIS gehostet. Während ASP.NET und IIS der Standardhost für einen Datendienst ist, werden andere Hostingoptionen unterstützt. Weitere Informationen finden Sie unter [Hosten des Datendienstes](hosting-the-data-service-wcf-data-services.md).

## <a name="deploy-wcf-data-services"></a>Bereitstellen von WCF-Datendiensten

Ein WCF Data Service bietet Flexibilität bei der Auswahl des Prozesses, von dem der Datendienst gehostet wird. Sie können Visual Studio verwenden, um einen Datendienst auf den folgenden Plattformen bereitzustellen:

- **IIS-gehosteter Webserver**

    Wenn ein Datendienst als ASP.NET Projekt entwickelt wird, kann er mithilfe der standardASP.NET Bereitstellungsprozesse auf einem IIS-Webserver bereitgestellt werden.  Visual Studio stellt die folgenden Bereitstellungstechnologien für ASP.NET bereit, abhängig von der Art des ASP.NET Projekts, das den Datendienst hostet, den Sie bereitstellen.

  - **Bereitstellungstechnologien für ASP.NET-Webanwendungen**

    - [Gewusst wie: Erstellen eines Webbereitstellungspakets in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465323(v=vs.110))

    - [Gewusst wie: Bereitstellen eines Webprojekts mithilfe von Ein-Klick-Veröffentlichung in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))

  - **Bereitstellungstechnologien für ASP.NET-Websites**

    - [Gewusst wie: Kopieren von Websitedateien mit dem Tool Website kopieren](https://docs.microsoft.com/previous-versions/aspnet/c95809c0(v=vs.100))

    - [Gewusst wie: Veröffentlichen von Websites](https://docs.microsoft.com/previous-versions/aspnet/20yh9f1b(v=vs.100))

    - [Exemplarische Vorgehensweise: Bereitstellen einer ASP.NET Webanwendung mithilfe von XCOPY](https://docs.microsoft.com/previous-versions/aspnet/f735abw9(v=vs.100))

     Weitere Informationen zu den Bereitstellungsoptionen für eine ASP.NET Anwendung finden Sie unter [Webbereitstellungsübersicht für Visual Studio und ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/dd394698(v=vs.110)).

    > [!TIP]
    > Bevor Sie versuchen, den Datendienst unter IIS bereitzustellen, muss die Bereitstellung auf einem Webserver mit IIS getestet werden. Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

- **Microsoft Azure**

     Sie können einen Datendienst in Windows Azure mithilfe von Windows Azure Tools für Visual Studio bereitstellen. Sie können die Windows Azure Tools für Visual Studio aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=201848)herunterladen. Weitere Informationen zum Bereitstellen eines Datendienstes in Windows Azure finden Sie im Beitrag [Bereitstellen eines OData-Dienstes in Windows Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="deployment-considerations"></a>Überlegungen zur Bereitstellung

Berücksichtigen Sie bei der Bereitstellung eines Datendienstes Folgendes:

- Wenn Sie einen Datendienst bereitstellen, der den Entity Framework-Anbieter für den Zugriff auf eine SQL Server-Datenbank verwendet, müssen Sie möglicherweise auch Datenstrukturen, Daten oder beides mit der Datendienstbereitstellung weitergeben. Visual Studio kann automatisch Skripts (.sql-Dateien) erstellen, um dies in der Zieldatenbank zu tun, und diese Skripts können in das Webbereitstellungspaket einer ASP.NET Anwendung aufgenommen werden. Weitere Informationen finden Sie unter [Gewusst wie: Bereitstellen einer Datenbank mit einem Webanwendungsprojekt](https://docs.microsoft.com/previous-versions/dd465343(v=vs.100)). Bei einer ASP.NET Website können Sie dies mithilfe des **Datenbankveröffentlichungs-Assistenten** in Visual Studio tun. Weitere Informationen finden Sie unter [Veröffentlichen einer SQL-Datenbank](https://docs.microsoft.com/previous-versions/aspnet/bb907585(v=vs.100)).

- Da WCF Data Services eine grundlegende WCF-Implementierung enthält, können Sie Windows Server AppFabric verwenden, um einen Datendienst zu überwachen, der auf IIS bereitgestellt wird und unter Windows Server ausgeführt wird. Weitere Informationen zur Verwendung von Windows Server AppFabric zum Überwachen eines Datendienstes finden Sie im Beitrag Nachverfolgung von [WCF-Datendiensten mit Windows Server AppFabric](https://docs.microsoft.com/archive/blogs/rjacobs/tracking-wcf-data-services-with-windows-server-appfabric).

## <a name="see-also"></a>Weitere Informationen

- [Hosten des Datendiensts](hosting-the-data-service-wcf-data-services.md)
- [Sichern von WCF Data Services](securing-wcf-data-services.md)
- [Definieren von WCF Data Services](defining-wcf-data-services.md)
