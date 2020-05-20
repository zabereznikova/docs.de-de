---
title: Hinzufügen von WCF Web Service Reference
description: Übersicht zum Microsoft WCF Web Service Reference Provider-Tool, über das Funktionen für .NET Core- und ASP.NET Core-Projekte hinzugefügt werden, z.B. das Hinzufügen von Dienstverweisen für .NET Framework-Projekte.
author: dasetser
ms.date: 10/29/2019
ms.custom: mvc
ms.openlocfilehash: cdd6b457d289dd7b752c97c5645f0797f24b72aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715682"
---
# <a name="use-the-wcf-web-service-reference-provider-tool"></a>Verwenden des Provider-Tools für den WCF-Webdienstverweis

Im Laufe der Jahre konnten viele Visual Studio-Entwickler von dem [**Dienstverweis hinzufügen**](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)-Tool profitieren und ihre Produktivität steigern, wenn sie für ihre .NET Framework-Projekte Zugriff auf Webdienste benötigten.  Bei dem **WCF Web Service Reference**-Tool handelt es sich um eine mit Visual Studio verknüpfte Diensterweiterung, die Funktionen wie „Dienstverweis hinzufügen“ für .NET Core und ASP.NET Core-Projekte bereitstellt. Dieses Tool ruft Metadaten von einem Webdienst in der aktuellen Projektmappe, von einer Netzwerkadresse oder aus einer WSDL-Datei ab und generiert eine mit .NET Core kompatible Quelldatei. Diese enthält den Proxycode des WCF-Clients (Windows Communication Foundation), den Sie verwenden können, um auf einen Webdienst zuzugreifen.

> [!IMPORTANT]
> Sie sollten nur auf Dienste aus einer vertrauenswürdigen Quelle verweisen. Wenn Sie Verweise aus nicht vertrauenswürdigen Quellen hinzufügen, hat das möglicherweise Auswirkungen auf die Sicherheit.

## <a name="prerequisites"></a>Voraussetzungen

- [Visual Studio 2017, Version 15.5](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) oder höhere Versionen

## <a name="how-to-use-the-extension"></a>Verwenden der Erweiterung

> [!NOTE]
> Die Option **WCF Web Service Reference** ist auf Projekte anwendbar, die über eine der folgenden Projektvorlagen erstellt werden:
>
> - **Visual C#**  >  **.NET Core**
> - **Visual C#**  >  **.NET Standard**
> - **Visual C#**  > **Web** > **ASP.NET Core-Webanwendung**

In diesem Artikel wird die Projektvorlage **ASP.NET Core-Webanwendung** als Beispiel genommen, um Ihnen exemplarisch zu erläutern, wie Sie einem Projekt einen WCF-Dienstverweis hinzufügen:

1. Doppelklicken Sie im Projektmappen-Explorer auf den Knoten **Verbundene Dienste** des Projekts. Bei .NET Core- oder .NET Standard-Projekten finden Sie diese Option, wenn Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Knoten **Abhängigkeiten** des Projekts klicken.

    Die Seite **Verbundene Dienste** wird wie in der folgenden Abbildung dargestellt angezeigt:

    ![Registerkarte „Verbundene Dienste in Visual Studio“ für .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. Klicken Sie auf der Seite **Verbundene Dienste** auf **Microsoft WCF Web Service Reference Provider**. Dann wird der Assistent **zum Konfigurieren von WCF-Webdienstverweisen** angezeigt:

    ![Registerkarte „Dienstendpunkt in Visual Studio“ für .NET Core](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. Wählen Sie einen Dienst aus.

    3a. Es sind einige Suchoptionen für den Dienst im Assistenten zum **Konfigurieren von WCF-Webdienstverweisen** verfügbar:

     * Klicken Sie auf die Schaltfläche **Ermitteln**, um nach Diensten zu suchen, die in der aktuellen Projektmappe definiert sind.
     * Geben Sie eine Dienst-URL im Feld **Adresse** ein, und klicken Sie auf die Schaltfläche **Gehe zu**, um nach Diensten zu suchen, die an einer bestimmten Adresse gehostet werden.
     * Klicken Sie auf die Schaltfläche **Durchsuchen**, um eine WSDL-Datei auszuwählen, die die Metadateninformationen des Webdiensts enthält.

    3b. Wählen Sie den Dienst aus der Liste der Suchergebnisse im Feld **Dienste** aus. Geben Sie ggf. den Namespace für den generierten Code im entsprechenden Textfeld **Namespace** ein.

    3c. Klicken Sie auf die Schaltfläche **Weiter**, um die **Datentypoptionen** und die Seiten **Clientoptionen** zu öffnen. Sie können stattdessen auch auf die Schaltfläche **Fertig stellen** klicken, um die Standardoptionen zu verwenden.

4. Mithilfe des Formulars **Datentypoptionen** können Sie die generierten Einstellungen für die Dienstverweise einschränken:

    ![Registerkarte „Datentypoptionen in Visual Studio“ für .NET Core](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

    > [!NOTE]
    > Die Kontrollkästchenoption **Typen in Assemblys, auf die verwiesen wird, wiederverwenden** ist nützlich, wenn Datentypen, die für die Codegenerierung für Dienstverweise benötigt werden, in einer der Assemblys definiert werden, auf die Ihr Projekt verweist.  Es ist wichtig, dass Sie die vorhandenen Datentypen wiederverwenden, um Typkollisionen oder Probleme mit der Runtime zur Kompilierzeit zu vermeiden.

    Es kann zu Verzögerungen kommen, während die Typinformationen geladen werden. Dies ist von der Anzahl von Projektabhängigkeiten und anderen die Systemleistung betreffenden Faktoren abhängig. Die Schaltfläche **Fertig stellen** wird beim Laden deaktiviert. Dies ist nicht der Fall, wenn das Kontrollkästchen **Typen in Assemblys, auf die verwiesen wird, wiederverwenden** deaktiviert ist.

5. Klicken Sie auf **Fertig stellen**, wenn Sie so weit sind.

Das Tool führt folgende Schritte aus, während es den Fortschritt anzeigt:

- Metadaten werden von dem WCF-Dienst heruntergeladen.
- Der Dienstverweiscode in einer Datei mit dem Namen *reference.cs* wird generiert und Ihrem Projekt unter dem Knoten **Verbundene Dienste** hinzugefügt.
- Aktualisiert die Projektdatei (.csproj) mit NuGet-Paketverweisen, die erforderlich sind, damit diese Datei auf der Zielplattform kompiliert und ausgeführt werden kann.

![Visual Studio-Fortschrittsfenster](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

Nachdem die Prozesse abgeschlossen sind, können Sie eine Instanz des generierten WCF-Clienttyps generieren und die Dienstvorgänge ausrufen.

## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte mit Windows Communication Foundation-Anwendungen](../../framework/wcf/getting-started-tutorial.md)
- [Windows Communication Foundation-Dienste und WCF Data Services in Visual Studio](/visualstudio/data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio)
- [Von WCF unterstützte Features in .NET Core](https://github.com/dotnet/wcf/blob/master/release-notes/SupportedFeatures-v2.1.0.md)

## <a name="feedback--questions"></a>Feedback und Fragen

Wenn Sie Fragen haben oder uns Feedback geben möchten, können Sie dies über die [Entwicklercommunity](/visualstudio/ide/how-to-report-a-problem-with-visual-studio) mithilfe des Tools [Problem melden](https://developercommunity.visualstudio.com/) tun.

## <a name="release-notes"></a>Anmerkungen zu diesem Release

- Aktualisierte Informationen zu den einzelnen Versionen, einschließlich bekannter Probleme, finden Sie in den [Anmerkungen zu den jeweiligen Versionen](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md).
