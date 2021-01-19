---
title: Migrieren von .NET Web-Apps oder -Diensten zu Azure App Service
description: Hier erfahren Sie, wie Sie eine .NET-Web-App oder einen .NET-Dienst aus einer lokalen Umgebung zu Azure App Service migrieren.
ms.topic: conceptual
ms.date: 07/08/2020
ms.openlocfilehash: 0e2aaa23aedabef007878901ec7297711f140533
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189251"
---
# <a name="migrate-your-net-web-app-or-service-to-azure-app-service"></a>Migrieren von .NET Web-Apps oder -Diensten zu Azure App Service

Bei [App Service](/azure/app-service/overview) handelt es sich um einen vollständig verwalteten Computeplattformdienst, der für das Hosten skalierbarer Websites und Webanwendungen optimiert ist. In diesem Artikel erfahren Sie, wie Sie eine vorhandene Anwendung per Lift & Shift zu Azure App Service migrieren, welche Änderungen ggf. erforderlich sind und welche zusätzlichen Ressourcen für den [Umzug in die Cloud](https://azure.microsoft.com/migration/web-applications/) benötigt werden. Die meisten ASP.NET-Websites (Webforms, MVC) und -Dienste (Web-API) können ohne Änderungen direkt in Azure App Service verschoben werden. Einige erfordern möglicherweise kleinere Änderungen, während andere ein wenig umgestaltet werden müssen.

Sind Sie bereit? [Veröffentlichen Sie Ihre ASP.NET- und SQL-Anwendung in Azure App Service.](https://tutorials.visualstudio.com/azure-webapp-migrate/intro)

## <a name="considerations"></a>Weitere Überlegungen

### <a name="on-premises-resources-including-sql-server"></a>Lokale Ressourcen (einschließlich SQL Server)

Überprüfen Sie den Zugriff auf lokale Ressourcen, da diese möglicherweise migriert oder geändert werden müssen. Folgende Optionen für Maßnahmen im Zusammenhang mit dem Zugriff auf lokale Ressourcen sind verfügbar:

* Erstellen Sie mithilfe von [Azure Virtual Networks](/azure/app-service/web-sites-integrate-with-vnet) ein VPN für die Verbindung von App Service mit lokalen Ressourcen.
* Machen Sie lokale Dienste mithilfe von [Azure Relay](/azure/service-bus-relay/relay-what-is-it) ohne Firewall Änderungen sicher in der Cloud verfügbar.
* Migrieren Sie Abhängigkeiten wie eine [SQL-Datenbank](./sql.md) zu Azure.
* Verwenden Sie Platform-as-a-Service-Angebote in der Cloud, um Abhängigkeiten zu reduzieren. Erwägen Sie beispielsweise die Verwendung von [SendGrid](/azure/sendgrid-dotnet-how-to-send-email) anstatt eine Verbindung mit einem lokalen Mailserver herzustellen.

### <a name="port-bindings"></a>Portbindungen

Azure App Service unterstützt nur Port 80 für HTTP- und Port 443 für HTTPS-Datenverkehr.

Für WCF werden die folgenden Bindungen unterstützt:

| Bindung | Hinweise |
|--|--|
| `BasicHttp` |  |
| `WSHttp` |  |
| `WSDualHttpBinding` | [WebSocket-Unterstützung](/azure/app-service/web-sites-configure) muss aktiviert sein. | [WebSocket-Unterstützung](/azure/app-service/web-sites-configure) muss aktiviert sein. |
| `NetHttpBinding` | [WebSocket-Unterstützung](/azure/app-service/web-sites-configure) muss für Duplexverträge aktiviert sein. | [WebSocket-Unterstützung](/azure/app-service/web-sites-configure) muss für Duplexverträge aktiviert sein. |
| `NetHttpsBinding` | [WebSocket-Unterstützung](/azure/app-service/web-sites-configure) muss für Duplexverträge aktiviert sein. | [WebSocket-Unterstützung](/azure/app-service/web-sites-configure) muss für Duplexverträge aktiviert sein. |
| `BasicHttpContextBinding` |  |
| `WebHttpBinding` |  |
| `WSHttpContextBinding` |  |

### <a name="authentication"></a>Authentifizierung

Azure App Service unterstützt die anonyme Authentifizierung standardmäßig und die Formularauthentifizierung, wenn diese vorgesehen ist. Windows-Authentifizierung kann nur durch die Integration in Azure Active Directory und ADFS verwendet werden. Weitere Informationen zum Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory finden Sie [hier](/azure/active-directory/connect/active-directory-aadconnect).

### <a name="assemblies-in-the-gac-global-assembly-cache"></a>Assemblys im GAC (globaler Assemblycache)

Dies wird nicht unterstützt. Gegebenenfalls sollten Sie die erforderlichen Assemblys in den *\bin*-Ordner der App kopieren. Auf dem Server installierte benutzerdefinierte *MSI*-Dateien (z. B. PDF-Generatoren usw.) können nicht verwendet werden.

### <a name="iis-settings"></a>IIS-Einstellungen

Alles, was in Ihrer Anwendung üblicherweise über „applicationHost.config“ konfiguriert wurde, kann jetzt über das Azure-Portal konfiguriert werden. Das gilt beispielsweise für die AppPool-Bitanzahl, für das Aktivieren/Deaktivieren von WebSocket-Protokollen, für die verwaltete Pipelineversion und für die .NET Framework-Version (2.0/4.0). Öffnen Sie zum Ändern Ihrer [Anwendungseinstellungen](/azure/app-service/web-sites-configure) im [Azure-Portal](https://portal.azure.com) das Blatt für Ihre Web-App, und klicken Sie auf die Registerkarte **Anwendungseinstellungen**.

#### <a name="iis5-compatibility-mode"></a>IIS5-Kompatibilitätsmodus

IIS5-Kompatibilitätsmodus wird Apps nicht unterstützt. In Azure App Service werden jede Web-App und alle Anwendungen darunter im gleichen Workerprozess mit bestimmten [Anwendungspools](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc735247(v=ws.10)) ausgeführt.

#### <a name="iis7-schema-compliance"></a>IIS7+-Schemakompatibilität

Einige Elemente und Attribute sind im Azure App Service-IIS-Schema nicht definiert. Sollten Probleme auftreten, ziehen Sie die Verwendung von [XDT-Transformationen](/azure/app-service/configure-common) in Betracht.

#### <a name="single-application-pool-per-site"></a>Ein Anwendungspool pro Website

In Azure App Service werden jede Web-App und alle Anwendungen darunter im gleichen Anwendungspool ausgeführt. Erwägen Sie das Einrichten eines zentralen Anwendungspools mit gemeinsamen Einstellungen oder das Erstellen einer separaten Web-App für jede Anwendung.

### <a name="com-and-com-components"></a>COM- und COM+-Komponenten

Azure App Service lässt keine Registrierung von COM-Komponenten auf der Plattform zu. Wenn Ihre App COM-Komponenten verwendet, müssen diese in verwaltetem Code neu geschrieben und mit der Website oder Anwendung bereitgestellt werden.

### <a name="physical-directories"></a>Physische Verzeichnisse

Azure App Service lässt keinen Zugriff auf physische Laufwerke zu. Möglicherweise müssen Sie [Azure Files](/azure/storage/files/storage-files-introduction) für den Zugriff auf Dateien über SMB verwenden. [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction) kann Dateien für den Zugriff über HTTPS speichern.

### <a name="isapi-filters"></a>ISAPI-Filter

Azure App Service kann die Verwendung von ISAPI-Filter unterstützen, allerdings muss die ISAPI-DLL mit der Website bereitgestellt und über „web.config“ registriert werden.

### <a name="https-bindings-and-ssl"></a>HTTPS-Bindungen und SSL

HTTPS-Bindungen werden nicht migriert, und die SSL-Zertifikate werden nicht Ihren Websites zugeordnet. SSL-Zertifikate können jedoch nach Abschluss der Websitemigration [manuell hochgeladen werden](/azure/app-service/app-service-web-tutorial-custom-ssl).

### <a name="sharepoint-and-frontpage"></a>SharePoint und FrontPage

SharePoint- und FrontPage-Servererweiterungen (FPSE) werden nicht unterstützt.

### <a name="web-site-size"></a>Websitegröße

Für kostenlose Websites gilt eine Größenbeschränkung von 1 GB für Inhalte. Wenn Ihre Website größer als 1 GB ist, müssen Sie auf eine kostenpflichtige SKU upgraden. Informationen dazu finden Sie unter [App Service – Preise](https://azure.microsoft.com/pricing/details/app-service/windows/).

### <a name="database-size"></a>Datenbankgröße

Überprüfen Sie für SQL Server-Datenbanken die aktuelle [Preisübersicht für SQL-Datenbank](https://azure.microsoft.com/pricing/details/sql-database).

### <a name="azure-active-directory-aad-integration"></a>Azure Active Directory (AAD)-Integration

AAD funktioniert nicht mit kostenlosen Apps. Zur Verwendung von AAD müssen Sie die App-SKU upgraden. Informationen dazu finden Sie unter [App Service – Preise](https://azure.microsoft.com/pricing/details/app-service/windows/).

### <a name="monitoring-and-diagnostics"></a>Überwachung und Diagnose

Ihre aktuellen lokalen Überwachungs- und Diagnoselösungen funktionieren in der Cloud wahrscheinlich nicht. Azure bietet jedoch Tools für die Protokollierung, Überwachung und Diagnose, um Probleme mit Web-Apps identifizieren und debuggen zu können. Die Diagnose für Ihre Web-App kann ganz einfach in der App-Konfiguration aktiviert werden, und die erfassten Protokolle können in Azure Application Insights angezeigt werden. Weitere Informationen zum Aktivieren der Diagnoseprotokollierung für Web-Apps finden Sie [hier](/azure/app-service/web-sites-enable-diagnostic-log).

### <a name="connection-strings-and-application-settings"></a>Verbindungszeichenfolgen und Anwendungseinstellungen

Erwägen Sie die Verwendung von [Azure Key Vault](/azure/key-vault/). Hierbei handelt es sich um einen Dienst zum sicheren Speichern vertraulicher Informationen Ihrer Anwendung. Alternativ können Sie die Daten als App Service-Einstellung speichern.

### <a name="dns"></a>DNS

Abhängig von den Anforderungen Ihrer Anwendung ist unter Umständen eine Aktualisierung von DNS-Konfigurationen erforderlich. Diese DNS-Einstellungen können in den [App Service-Einstellungen für die benutzerdefinierte Domäne](/azure/app-service/app-service-web-tutorial-custom-domain) konfiguriert werden.

## <a name="azure-app-service-with-windows-containers"></a>Azure App Service mit Windows-Containern

Wenn Ihre App nicht direkt zu App Service migriert werden kann, können Sie App Service mit Windows-Containern verwenden. Dies ermöglicht die Verwendung von GAC, COM-Komponenten, MSIs sowie den vollen Zugriff auf .NET FX-APIs, DirectX und mehr.

## <a name="see-also"></a>Siehe auch

* [Bestimmen, ob Ihre App für App Service geeignet ist](https://appmigration.microsoft.com/)
* [Verschieben Ihrer Datenbank in die Cloud](sql.md)
* [Sandbox für Azure-Web-Apps](https://github.com/projectkudu/kudu/wiki/Azure-Web-App-sandbox)
