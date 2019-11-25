---
title: Schnellstart (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: d0002182c5ae519c36348acdd2587bca499fe72e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975141"
---
# <a name="quickstart-wcf-data-services"></a>Schnellstart (WCF Data Services)

Dieser Schnellstart hilft Ihnen, sich mit WCF Data Services und der Open Data Protocol (odata) durch eine Reihe von Aufgaben vertraut zu machen, die die [Themen in den](getting-started-with-wcf-data-services.md)ersten Schritten unterstützen.

## <a name="what-youll-learn"></a>Was Sie lernen

Die erste Aufgabe in diesem Schnellstart zeigt, wie Sie einen Datendienst erstellen, um einen odata-Feed aus der Northwind-Beispieldatenbank verfügbar zu machen. In späteren Themen greifen Sie mithilfe eines Webbrowsers auf den odata-Feed zu und erstellen eine Windows Presentation Foundation (WPF)-Client Anwendung, die den odata-Feed mithilfe von Client Bibliotheken nutzt.

## <a name="prerequisites"></a>Erforderliche Voraussetzungen

Um diesen Schnellstart durchzuführen, müssen Sie die folgenden Komponenten installieren:

- Visual Studio

- Eine Instanz von SQL Server. Dies umfasst SQL Server Express, das in einer Standardinstallation von Visual Studio 2015 enthalten ist, oder als Teil der Arbeitsauslastung für die **Datenspeicherung und-Verarbeitung** in Visual Studio 2017.

- Die Beispieldatenbank Northwind. Diese Beispieldatenbank kann von der Downloadseite [Beispieldatenbanken für SQL Server](https://go.microsoft.com/fwlink/?linkid=24758)heruntergeladen werden.

## <a name="wcf-data-services-quickstart-tasks"></a>WCF Data Services-Schnellstart Aufgaben

 [Erstellen des Daten Dienstanbieter](creating-the-data-service.md)

 Definieren Sie die ASP.NET-Anwendung, definieren Sie das Datenmodell, erstellen Sie den Datendienst und aktivieren Sie den Zugriff auf Ressourcen.

 [Zugreifen auf den Dienst über einen Webbrowser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Starten Sie den Dienst aus Visual Studio, und greifen Sie auf den Dienst zu, indem Sie HTTP GET-Anforderungen über einen Webbrowser an den verfügbar gemachten Feed senden.

 [Erstellen der .NET Framework Client Anwendung](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Erstellen Sie eine WPF-App, um den odata-Feed zu nutzen, binden Sie Daten an Windows-Steuerelemente, ändern Sie Daten in den gebundenen Steuerelementen, und senden Sie die Änderungen dann an den Datendienst zurück.

> [!NOTE]
> Projektdateien einer abgeschlossenen Version des Schnellstarts können von der Seite [WCF Data Services Quickstart (OData Service and WPF Client)](https://go.microsoft.com/fwlink/?LinkId=179994) (WCF Data Services-Schnellstart (OData-Dienst und WPF-Client)) heruntergeladen werden.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Starten des Schnellstarts](creating-the-data-service.md)

## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Framework](../adonet/ef/index.md)
