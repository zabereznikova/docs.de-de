---
title: Schnellstart (WCF Data Services)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121226"
---
# <a name="quickstart-wcf-data-services"></a>Schnellstart (WCF Data Services)

Diese Schnellstartanleitung hilft Ihnen, sich mit WCF Data Services und dem Open Data Protocol (OData) durch eine Reihe von Aufgaben vertraut zu machen, die die Themen unter [Erste Schritte](getting-started-with-wcf-data-services.md)unterstützen.

## <a name="what-youll-learn"></a>Sie lernen Folgendes

Die erste Aufgabe in dieser Schnellstartanleitung zeigt, wie Sie einen Datendienst erstellen, um einen OData-Feed aus der Northwind-Beispieldatenbank verfügbar zu machen. In späteren Themen greifen Sie über einen Webbrowser auf den OData-Feed zu und erstellen außerdem eine Windows Presentation Foundation (WPF)-Clientanwendung, die den OData-Feed mithilfe von Clientbibliotheken verwendet.

## <a name="prerequisites"></a>Voraussetzungen

Um diese Schnellstartanleitung abzuschließen, installieren Sie die folgenden Komponenten:

- Visual Studio

- Eine Instanz von SQL Server. Dies schließt SQL Server Express ein, das in einer Standardinstallation von Visual Studio 2015 oder als Teil der **Datenspeicherung und Verarbeitungsworkload** in Visual Studio 2017 oder höher enthalten ist.

- Die Beispieldatenbank Northwind. Um die Datenbank zu installieren, führen Sie das Transact-SQL-Skript von [Northwind und pubs Beispieldatenbanken für Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)aus.

## <a name="wcf-data-services-quickstart-tasks"></a>WCF-Datendienste-Schnellstartaufgaben

 [Erstellen des Datendienstes](creating-the-data-service.md)

 Definieren Sie die ASP.NET-Anwendung, definieren Sie das Datenmodell, erstellen Sie den Datendienst und aktivieren Sie den Zugriff auf Ressourcen.

 [Zugriff auf den Dienst über einen Webbrowser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 Starten Sie den Dienst aus Visual Studio, und greifen Sie auf den Dienst zu, indem Sie HTTP GET-Anforderungen über einen Webbrowser an den verfügbar gemachten Feed senden.

 [Erstellen der .NET Framework Client-Anwendung](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 Erstellen Sie eine WPF-App, um den OData-Feed zu nutzen, Daten an Windows-Steuerelemente zu binden, Daten in den gebundenen Steuerelementen zu ändern und die Änderungen dann an den Datendienst zurückzusenden.

> [!NOTE]
> Projektdateien aus einer fertigen Version des Schnellstarts können von [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))heruntergeladen werden.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Starten Sie den Schnellstart](creating-the-data-service.md)

## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Framework](../adonet/ef/index.md)
