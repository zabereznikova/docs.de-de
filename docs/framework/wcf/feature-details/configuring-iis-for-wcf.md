---
title: Konfigurieren von Internetinformationsdienste 7.0 für Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 53ba48d47d30bd94ae5544920041cd430526223b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710296"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Konfigurieren von Internetinformationsdienste 7.0 für Windows Communication Foundation

Internetinformationsdienste (IIS) 7.0 weist einen modularen Aufbau auf, der es Ihnen ermöglicht, die benötigten Komponenten selektiv zu installieren. Dieser Aufbau basiert auf der neuen manifest-gesteuerten Komponententechnologie, die in [!INCLUDE[wv](../../../../includes/wv-md.md)] eingeführt wurde. Es gibt mehr als 40 eigenständige Funktionskomponenten von IIS 7.0, die unabhängig voneinander installiert werden kann. Dies ermöglicht es IT-Profis, die Installation problemlos nach Bedarf anzupassen. In diesem Thema erläutert das Konfigurieren von IIS 7.0 für die Verwendung mit Windows Communication Foundation (WCF) und bestimmen, welche Komponenten erforderlich sind.

## <a name="minimal-installation-installing-was"></a>Minimale Installation: Installieren von WAS
 Die minimale Installation des gesamten Pakets IIS 7.0 ist zum Installieren der Windows Process Activation Service (WAS). Ist eine eigenständige Funktion war, und es ist die einzige Funktion in IIS 7.0, die für alle verfügbar ist [!INCLUDE[wv](../../../../includes/wv-md.md)] Betriebssysteme (Home Basic, Home Premium, Business und Ultimate und Enterprise).

 Klicken Sie in der Systemsteuerung auf **Programme** , und klicken Sie dann auf **Aktivieren von Windows-Funktionen ein- oder ausschalten** die finden Sie unter **Programme und Funktionen**, die WAS-Komponente wird angezeigt, der die Liste wie in der folgenden Abbildung.

 ![-Funktionen ein-oder ausschalten Dialogfeld](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "Wcfc_TurnFeaturesOnOrOffs")

 Diese Funktion weist die folgenden untergeordneten Komponenten auf:

-   .NET-Umgebung

-   Konfigurations-APIs

-   Prozessmodell

 Wenn Sie nur den Stammknoten von WAS Auswählen der **Prozessmodell** Unterknoten ist standardmäßig aktiviert. Beachten Sie, dass Sie mit dieser Installation lediglich WAS installieren, da kein Webserver unterstützt wird.

 Um WCF oder ASP.NET Application Arbeit machen, überprüfen Sie die **.NET Umgebung** Kontrollkästchen. Dies bedeutet, dass alle WAS-Komponenten erforderlich, damit WCF und ASP.NET für eine gute Lösung sind. Diese werden automatisch überprüft, sobald Sie eine dieser Komponenten installieren.

## <a name="iis-70-default-installation"></a>IIS 7.0: Standardinstallation
 Durch Überprüfen der **Internet Information Services** Feature, einige der untergeordneten Knoten werden automatisch überprüft werden, wie in der folgenden Abbildung dargestellt.

 ![Standardeinstellungen für IIS 7.0-Features](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")

 Dies ist die Standardinstallation von IIS 7.0. Mit dieser Installation können Sie IIS 7.0 zum Verarbeiten von statischem Inhalt (z. B. HTML-Seiten und andere Inhalte). Sie können nicht jedoch, ASP.NET oder CGI-Anwendungen oder Host WCF-Dienste ausführen.

## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: Installation mit ASP.NET-Unterstützung
 Sie müssen ASP.NET zum Stellen von ASP.NET in IIS 7.0 funktionieren installieren. Nach der Überprüfung **ASP.NET**, Ihr Bildschirm sollte wie in der folgenden Abbildung aussehen.

 ![Asp.NET Erforderliche Einstellungen](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")

 Dies ist die minimale Umgebung für Anwendungen mit WCF und ASP.NET in IIS 7.0 funktioniert.

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: Installation mit IIS 6.0-Kompatibilitätskomponenten
 Bei der Installation von IIS 7.0 auf einem System mit Visual Studio 2005 oder einige andere Automatisierungsskripts oder Tools (z. B. Adsutil.vbs), die virtuelle Anwendungen zu konfigurieren, die IIS 6.0-Metabase-API verwenden, stellen Sie sicher, dass Sie überprüfen, dass die IIS 6.0 **Skriptingtools**. Dies überprüft automatisch die anderen untergeordneten Knoten von IIS 6.0 **-Verwaltungskompatibilität**. Die folgende Abbildung zeigt den Bildschirm nach Abschluss dieses Vorgangs ist:

 ![Einstellungen für die Kompatibilität von IIS 6.0 Verwaltung](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")

 Bei dieser Installation müssen Sie alle notwendigen Schritte zur IIS 7.0, ASP.NET und WCF-Features und Beispielen, die verfügbar sind im Web verwenden.

## <a name="request-limits"></a>Anforderungsbeschränkungen
 Unter [!INCLUDE[wv](../../../../includes/wv-md.md)] mit IIS 7 wurden der Standardwert von `maxUri` und die `maxQueryStringSize`-Einstellungen geändert. Standardmäßig sind in Anforderungsfiltern in IIS 7.0 eine URL-Länge von 4096 Zeichen und Abfragezeichenfolgen mit einer Länge von 2048 Zeichen zulässig. Um diese Standardwerte zu ändern, fügen Sie das folgende XML der Datei App.config hinzu.

```xml
 <system.webServer>
    <security>
        <requestFiltering>
            <requestLimits maxUrl="8192" maxQueryString="8192" />
        </requestFiltering>
    </security>
 </system.webServer>
 ```

## <a name="see-also"></a>Siehe auch

- [WAS-Aktivierungsarchitektur](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [Konfigurieren von WAS für die Verwendung mit WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [Vorgehensweise: Installieren und Konfigurieren von WCF-Aktivierungskomponenten](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [Windows Server AppFabric-Hostingfunktionen](https://go.microsoft.com/fwlink/?LinkId=201276)
