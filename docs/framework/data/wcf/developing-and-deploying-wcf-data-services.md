---
title: Entwickeln und Bereitstellen von WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- deploying [WCF Data Services
- developing applications [WCF Data Services]
ms.assetid: 6557c0e3-5aea-4f6e-bc14-77ad317a168b
ms.openlocfilehash: e34f7c8a0194e3901453923530a5cd07202801f6
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937460"
---
# <a name="develop-and-deploy-wcf-data-services"></a>Entwickeln und Bereitstellen von WCF Data Services

Dieses Thema enthält Informationen zum entwickeln und Bereitstellen von WCF Data Services. Weitere grundlegende Informationen zu WCF Data Services finden Sie unter [Getting Started](getting-started-with-wcf-data-services.md) and [Overview](wcf-data-services-overview.md).

## <a name="develop-wcf-data-services"></a>Entwickeln WCF Data Services

Wenn Sie WCF Data Services verwenden, um einen Datendienst zu erstellen, der die Open Data Protocol (odata) unterstützt, müssen Sie während der Entwicklung die folgenden grundlegenden Aufgaben ausführen:

1. **Definieren des Datenmodells**

     WCF Data Services unterstützt eine Vielzahl von Daten Dienstanbietern, die es Ihnen ermöglichen, ein Datenmodell auf der Grundlage von Daten aus einer Vielzahl von Datenquellen zu definieren, von relationalen Datenbanken bis hin zu spät gebundenen Datentypen. Weitere Informationen finden Sie unter [Data Services-Anbietern](data-services-providers-wcf-data-services.md).

2. **Erstellen des Datendiensts**

     Der einfachste Datendienst macht eine Klasse, die von der <xref:System.Data.Services.DataService%601> -Klasse erbt, mit einem Typ `T` verfügbar, bei dem es sich um den namespacequalifizierten Namen des Entitätscontainers handelt. Weitere Informationen finden Sie unter [Defining WCF Data Services](defining-wcf-data-services.md).

3. **Konfigurieren des Datendiensts**

     Standardmäßig deaktiviert WCF Data Services den Zugriff auf Ressourcen, die von einem Entitätencontainer verfügbar gemacht werden. Die <xref:System.Data.Services.DataServiceConfiguration>-Schnittstelle ermöglicht Ihnen das Konfigurieren des Zugriffs auf Ressourcen und Dienst Vorgänge, das Angeben der unterstützten Version von odata und das definieren anderer Dienst weiter Verhalten, wie z. b. das Batch Verarbeitungs Verhalten oder die maximale Anzahl von Entitäten, die in einem einzelnen Antwort Feed zurückgegeben werden können. Weitere Informationen finden Sie unter [Konfigurieren des Daten Dienstanbieter](configuring-the-data-service-wcf-data-services.md).

Dieses Thema behandelt primär die Entwicklung und Bereitstellung von Datendiensten mithilfe von Visual Studio. Informationen zur Flexibilität, die WCF Data Services zum verfügbar machen Ihrer Daten als odata-Feeds bietet, finden Sie unter [Definieren von WCF Data Services](defining-wcf-data-services.md).

### <a name="choose-a-development-web-server"></a>Wählen Sie einen entwicklungsweb Server aus.

Wenn Sie einen WCF Data Service mithilfe von Visual Studio 2015 als ASP.NET-Anwendung oder ASP.NET-Website entwickeln, können Sie die Webserver auswählen, auf denen der Datendienst während der Entwicklung ausgeführt werden soll. Die folgenden Webserver sind in Visual Studio integriert, um das Testen und Debuggen der Datendienste auf dem lokalen Computer zu vereinfachen.

1. **Lokaler IIS-Server**

     Wenn Sie einen Datendienst erstellen, bei dem es sich um eine ASP.net-oder ASP.NET-Website handelt, die auf Internetinformationsdienste (IIS) ausgeführt wird, empfiehlt es sich, den Datendienst mithilfe von IIS auf dem lokalen Computer zu entwickeln und zu testen. Die Ausführung des Datendiensts unter IIS erleichtert die Ablaufverfolgung von HTTP-Anforderungen während des Debuggens. Zudem können Sie so vorab die Rechte bestimmen, die IIS für den Zugriff auf Dateien, Datenbanken und andere für den Datendienst erforderliche Ressourcen erfordert. Um den Datendienst unter IIS auszuführen, müssen Sie sicherstellen, dass IIS und Windows Communication Foundation (WCF) installiert und ordnungsgemäß konfiguriert sind und Zugriff auf IIS-Konten im Dateisystem und in den Datenbanken gewähren. Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

    > [!NOTE]
    > Sie müssen Visual Studio mit Administratorrechten ausführen, um die Entwicklungsumgebung für die Konfiguration des lokalen IIS-Servers zu aktivieren.

2. **Visual Studio Development Server**

     Visual Studio enthält einen integrierten Webserver, den Visual Studio Development Server, der der Standardweb Server für ASP.net-Projekte ist. Dieser Webserver ist so konzipiert, dass ASP.net-Projekte während der Entwicklung auf dem lokalen Computer ausgeführt werden. Der [WCF Data Services Schnellstart](quickstart-wcf-data-services.md) zeigt, wie ein Datendienst erstellt wird, der in der Visual Studio Development Server ausgeführt wird.

     Beachten Sie die folgenden Einschränkungen, wenn Sie den Visual Studio Development Server zum Entwickeln des Daten Dienstanbieter verwenden:

    - Auf diesen Server kann nur auf dem lokalen Computer zugegriffen werden.

    - Dieser Server lauscht an `localhost` und an einem bestimmten Anschluss auf Nachrichten, nicht an Anschluss 80, dem Standardanschluss für HTTP-Nachrichten. Weitere Informationen finden Sie unter [Webserver in Visual Studio für ASP.NET-Webprojekte](https://docs.microsoft.com/previous-versions/aspnet/58wxa9w5(v=vs.120)).

    - Dieser Server führt den Datendienst im Kontext Ihres aktuellen Benutzerkontos aus. Wenn Sie z. b. als Administrator auf Administratorebene ausführen, verfügt ein Datendienst, der in der Visual Studio Development Server ausgeführt wird, über Berechtigungen auf Administratorebene. Dies kann dazu führen, dass der Datendienst auf Ressourcen zugreifen kann, für die er bei der Bereitstellung auf einem IIS-Server keine Zugriffsrechte besitzt.

    - Die zusätzlichen Funktionen von IIS sind auf diesem Server nicht verfügbar (z. B. die Authentifizierung).

    - Dieser Server kann keine aufgeteilten http-Streams verarbeiten, die beim Zugriff auf große Binärdaten vom Datendienst standardmäßig vom WCF Data Services Client gesendet werden. Weitere Informationen finden Sie unter [streaminganbieter](streaming-provider-wcf-data-services.md).

    - Bei diesem Server treten Probleme bei der Verarbeitung des Punkt Zeichens (`.`) in einer URL auf, obwohl dieses Zeichen durch WCF Data Services in Schlüsselwerten unterstützt wird.

    > [!TIP]
    > Obwohl Sie die Visual Studio Development Server verwenden können, um Ihre Datendienste während der Entwicklung zu testen, sollten Sie Sie nach der Bereitstellung auf einem Webserver, auf dem IIS ausgeführt wird, erneut testen.

3. **Microsoft Azure-Entwicklungsumgebung**

     Windows Azure-Tools für Visual Studio beinhaltet einen integrierten Satz von Tools für die Entwicklung von Windows Azure-Diensten in Visual Studio. Mit diesen Tools können Sie einen Datendienst entwickeln, der unter Windows Azure bereitgestellt werden kann, und den Datendienst vor der Bereitstellung auf dem lokalen Computer testen. Verwenden Sie diese Tools, wenn Sie Visual Studio verwenden, um einen Datendienst zu entwickeln, der auf der Windows Azure-Plattform ausgeführt wird. Sie können die Windows Azure-Tools für Visual Studio aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=201848)herunterladen. Weitere Informationen zum Entwickeln eines Daten Dienstanbieter, der unter Windows Azure ausgeführt wird, finden Sie im Beitrag bereitstellen [eines odata-Dienstanbieter in Windows Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="development-tips"></a>Tipps für die Entwicklung

Beachten Sie beim Entwickeln eines Datendiensts die folgenden Hinweise:

- Bestimmen Sie die Sicherheitsanforderungen des Datendiensts, wenn Sie vorhaben, Benutzer zu authentifizieren oder den Zugriff für bestimmte Benutzer einzuschränken. Weitere Informationen finden Sie unter [Securing WCF Data Services](securing-wcf-data-services.md).

- Ein HTTP-Überprüfungsprogramm kann beim Debuggen eines Datendiensts hilfreich sein, da es Ihnen die Möglichkeit bietet, den Inhalt von Anforderungs- und Antwortnachrichten zu überprüfen. Zum Überprüfen von HTTP-Anforderungen an den Datendienst und HTTP-Antworten vom Datendienst kann eine beliebige Netzwerkpaketanalyse verwendet werden, die die Anzeige von Rohpaketen unterstützt.

- Wenn Sie einen Datendienst Debuggen, können Sie weitere Informationen zu einem Fehler vom Datendienst als während des normalen Vorgangs abrufen. Sie können zusätzliche Fehlerinformationen vom Datendienst abrufen, indem Sie die <xref:System.Data.Services.DataServiceConfiguration.UseVerboseErrors%2A> -Eigenschaft in der <xref:System.Data.Services.DataServiceConfiguration> auf `true` festlegen und die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A> -Eigenschaft des <xref:System.ServiceModel.Description.ServiceDebugBehavior> -Attributs der Datendienstklasse auf `true`festlegen. Weitere Informationen finden Sie unter WCF Data Services nach dem [Debuggen](https://blogs.msdn.microsoft.com/phaniraj/?m=20086). Sie können die Ablauf Verfolgung auch in WCF aktivieren, um Ausnahmen anzuzeigen, die in der http-Messaging Schicht ausgelöst werden. Weitere Informationen finden Sie unter [Configuring Tracing](../../wcf/diagnostics/tracing/configuring-tracing.md).

- Ein Datendienst wird normalerweise als ASP.NET-Anwendungsprojekt entwickelt, Sie können den Datendienst aber auch als ASP.NET-Website Projekt in Visual Studio erstellen. Informationen zu den Unterschieden zwischen den beiden Projekttypen finden Sie unter [Webanwendungs Projekte im Vergleich zu Website Projekten in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd547590(v=vs.110)).

- Wenn Sie einen Datendienst mithilfe des Dialog Felds **Neues Element hinzufügen** in Visual Studio erstellen, wird der Datendienst von ASP.net in IIS gehostet. Während ASP.net und IIS der Standard Host für einen Datendienst sind, werden andere Hostingoptionen unterstützt. Weitere Informationen finden Sie unter [Hosting the Data Service](hosting-the-data-service-wcf-data-services.md).

## <a name="deploy-wcf-data-services"></a>WCF Data Services bereitstellen

Ein WCF Data Service bietet Flexibilität bei der Auswahl des Prozesses, von dem der Datendienst gehostet wird. Sie können Visual Studio verwenden, um einen Datendienst auf den folgenden Plattformen bereitzustellen:

- **IIS-gehosteter Webserver**

    Wenn ein Datendienst als ASP.net-Projekt entwickelt wird, kann er mithilfe der standardmäßigen ASP.net-Bereitstellungs Prozesse auf einem IIS-Webserver bereitgestellt werden.  Visual Studio bietet die folgenden Bereitstellungs Technologien für ASP.net, abhängig von der Art des ASP.NET-Projekts, das den Datendienst hostet, den Sie bereitstellen.

  - **Bereitstellungstechnologien für ASP.NET-Webanwendungen**

    - [Vorgehensweise: Erstellen eines Webbereitstellungs Pakets in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465323(v=vs.110))

    - [Gewusst wie: Bereitstellen eines Webprojekts mithilfe der One-Click-Veröffentlichung in Visual Studio](https://docs.microsoft.com/previous-versions/aspnet/dd465337(v=vs.110))

  - **Bereitstellungstechnologien für ASP.NET-Websites**

    - [Gewusst wie: Kopieren von Website Dateien mit dem Tool "Website kopieren"](https://docs.microsoft.com/previous-versions/aspnet/c95809c0(v=vs.100))

    - [Vorgehensweise: Veröffentlichen von Websites](https://docs.microsoft.com/previous-versions/aspnet/20yh9f1b(v=vs.100))

    - [Exemplarische Vorgehensweise: Bereitstellen einer ASP.NET-Webanwendung mit XCOPY](https://docs.microsoft.com/previous-versions/aspnet/f735abw9(v=vs.100))

     Weitere Informationen zu den Bereitstellungs Optionen für eine ASP.NET-Anwendung finden Sie unter Übersicht über die [Webbereitstellung für Visual Studio und ASP.net](https://docs.microsoft.com/previous-versions/aspnet/dd394698(v=vs.110)).

    > [!TIP]
    > Bevor Sie versuchen, den Datendienst unter IIS bereitzustellen, muss die Bereitstellung auf einem Webserver mit IIS getestet werden. Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](how-to-develop-a-wcf-data-service-running-on-iis.md).

- **Windows Azure**

     Sie können einen Datendienst mithilfe der Windows Azure-Tools für Visual Studio in Windows Azure bereitstellen. Sie können die Windows Azure-Tools für Visual Studio aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=201848)herunterladen. Weitere Informationen zum Bereitstellen eines Daten Dienstanbieter in Windows Azure finden Sie im Beitrag bereitstellen [eines odata-Dienstanbieter in Windows Azure](https://docs.microsoft.com/archive/blogs/astoriateam/deploying-an-odata-service-in-windows-azure).

### <a name="deployment-considerations"></a>Überlegungen zur Bereitstellung

Beachten Sie beim Bereitstellen eines Datendiensts die folgenden Hinweise:

- Wenn Sie einen Datendienst bereitstellen, der den Entity Framework Anbieter für den Zugriff auf eine SQL Server Datenbank verwendet, müssen Sie möglicherweise auch Datenstrukturen, Daten oder beides mit der Datendienst Bereitstellung weitergeben. Visual Studio kann automatisch Skripts (SQL-Dateien) in der Zieldatenbank erstellen, und diese Skripts können im Webbereitstellungs Paket einer ASP.NET-Anwendung enthalten sein. Weitere Informationen finden Sie unter Gewusst [wie: Bereitstellen einer Datenbank mit einem Webanwendungs Projekt](https://docs.microsoft.com/previous-versions/dd465343(v=vs.100)). Für eine ASP.NET-Website können Sie dazu den Assistenten für die **Daten Bank Veröffentlichung** in Visual Studio verwenden. Weitere Informationen finden Sie unter [Veröffentlichen einer SQL-Datenbank](https://docs.microsoft.com/previous-versions/aspnet/bb907585(v=vs.100)).

- Da WCF Data Services eine einfache WCF-Implementierung enthält, können Sie Windows Server AppFabric verwenden, um einen Datendienst zu überwachen, der unter IIS unter Windows Server bereitgestellt wird. Weitere Informationen zur Verwendung von Windows Server AppFabric zum Überwachen eines Daten dienstanzdienstanbieter finden Sie im Beitrag nach [Verfolgung WCF Data Services mit Windows Server AppFabric](https://docs.microsoft.com/archive/blogs/rjacobs/tracking-wcf-data-services-with-windows-server-appfabric).

## <a name="see-also"></a>Siehe auch

- [Hosten des Datendiensts](hosting-the-data-service-wcf-data-services.md)
- [Sichern von WCF Data Services](securing-wcf-data-services.md)
- [Defining WCF Data Services](defining-wcf-data-services.md)
