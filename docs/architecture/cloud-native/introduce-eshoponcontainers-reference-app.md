---
title: Einführung in die eshoponcontainers-Referenz-App
description: Einführung in die systemeigene cloudbasierte Webdienst-Referenz-App für ASP.net Core und Azure.
ms.date: 06/30/2019
ms.openlocfilehash: 8d4ad982716a07613ebbef6668afab69d5a8b4f6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895537"
---
# <a name="introducing-eshoponcontainers-reference-app"></a>Einführung in die eshoponcontainers-Referenz-App

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In Zusammenarbeit mit führenden Community-Experten hat Microsoft in Zusammenarbeit mit einer voll funktionsfähigen Cloud-Native-Referenz Anwendung (eshoponcontainers) erstellt. Diese Anwendung ist für die Veranschaulichung der Verwendung von .net Core und docker und optional von Azure, Kubernetes und Visual Studio zum Erstellen einer Online Store Front konzipiert.

![Bildschirm Abbildung der eshoponcontainers-Beispiel-app.](./media/eshoponcontainers-sample-app-screenshot.png)

**Abbildung 2-1**. Bildschirm Abbildung der eshoponcontainers-Beispiel-app.

Bevor Sie mit diesem Kapitel beginnen, sollten Sie die [eshoponcontainers-Referenz Anwendung](https://github.com/dotnet-architecture/eShopOnContainers)herunterladen. Wenn Sie dies tun, sollten Sie die nachfolgenden Informationen leichter befolgen.

## <a name="features-and-requirements"></a>Features und Anforderungen

Beginnen wir mit einer Prüfung der Features und Anforderungen der Anwendung. Die eshoponcontainers-Anwendung stellt einen Online Shop dar, der verschiedene physische Produkte wie t-Shirts und Kaffee-Mugs verkauft. Wenn Sie zuvor etwas online gekauft haben, sollte die Erfahrung bei der Verwendung des Stores relativ vertraut sein. Im folgenden finden Sie einige der grundlegenden Features, die der Store implementiert:

- Auflisten von Katalogelementen
- Elemente nach Typ filtern
- Elemente nach Marke Filtern
- Elemente zum Warenkorb hinzufügen
- Bearbeiten oder Entfernen von Elementen aus dem Warenkorb
- Auschecken
- Konto registrieren
- Anmelden
- Abmelden
- Aufträge überprüfen

Die Anwendung verfügt auch über die folgenden nicht funktionalen Anforderungen:

- Der Dienst muss hoch verfügbar sein, und er muss automatisch skaliert werden, um mehr Datenverkehr zu erreichen (und die Skalierung nach dem Datenverkehr zu erhöhen).
- Es sollte eine einfach zu verwendende Überwachung der Integritäts-und Diagnoseprotokolle bieten, um Probleme bei der Problembehandlung zu beheben.
- Es sollte einen Agile Entwicklungsprozess unterstützen, einschließlich der Unterstützung für Continuous Integration und Bereitstellung (CI/CD).
- Zusätzlich zu den beiden Web-Front-Ends (herkömmliche und Single-Page-Anwendung) muss die Anwendung auch Mobile Client-apps unterstützen, die unterschiedliche Arten von Betriebssystemen ausführen.
- Es sollte plattformübergreifendes Hosting und plattformübergreifende Entwicklung unterstützen.

![eshoponcontainers Referenz zur Anwendungs Entwicklungs Architektur.](./media/eshoponcontainers-development-architecture.png)

**Abbildung 2-2**. eshoponcontainers Referenz zur Anwendungs Entwicklungs Architektur.

Der Zugriff auf die Anwendung eshoponcontainers ist über Web-oder Mobile Clients möglich, die über HTTPS auf die Anwendung zugreifen, die entweder auf die ASP.net Core MVC-Serveranwendung oder ein entsprechendes API-Gateway abzielt. API-Gateways bieten mehrere Vorteile, wie z. b. das Entkoppeln von Back-End-Diensten von einzelnen Front-End-Clients und die Bereitstellung einer Die Anwendung nutzt auch ein verknüpftes Muster, das als Backends-for-Frontend (BFF) bezeichnet wird, das die Erstellung separater API-Gateways für jeden Front-End-Client empfiehlt. Die Referenzarchitektur veranschaulicht das Aufteilen der API-Gateways, je nachdem, ob die Anforderung von einem Web-oder mobilen Client stammt.

Die Funktionalität der Anwendung wird in eine Reihe unterschiedlicher-Dienste aufgeteilt. Dienste sind für die Authentifizierung und Identität, das Auflisten von Elementen aus dem Produktkatalog, das Verwalten der Einkaufskörbe von Benutzern und das Platzieren von Aufträgen zuständig. Jeder dieser separaten Dienste verfügt über einen eigenen persistenten Speicher. Beachten Sie, dass es keinen einzelnen Master Datenspeicher gibt, mit dem alle Dienste interagieren. Stattdessen erfolgt die Koordination und Kommunikation zwischen den Diensten Bedarfs abhängig und durch die Verwendung eines Nachrichtenbus.

Alle unterschiedlichen-Dienste sind basierend auf Ihren individuellen Anforderungen anders konzipiert. Dies bedeutet, dass sich der technologische Stapel unterscheiden kann, obwohl alle mit .net Core erstellt und für die Cloud entwickelt wurden. Einfachere Dienste bieten einen einfachen CRUD-Zugriff (Create-Read-Update-Delete) auf die zugrunde liegenden Datenspeicher, während erweiterte Dienste Domänen gesteuerte Entwurfs Ansätze und-Muster verwenden, um die Geschäfts Komplexität zu verwalten.

![Verschiedene Arten von mikrodiensten](./media/different-kinds-of-microservices.png)

**Abbildung 2-3**. Verschiedene Arten von-Diensten.

## <a name="overview-of-the-code"></a>Übersicht über den Code

Da es sich um die Nutzung von mikrodiensten handelt, enthält die eshoponcontainers-App im GitHub-Repository einige separate Projekte und Lösungen. Zusätzlich zu separaten Lösungen und ausführbaren Dateien sind die verschiedenen Dienste so konzipiert, dass Sie sowohl während der lokalen Entwicklung als auch zur Laufzeit in der Produktion in ihren eigenen Containern ausgeführt werden. In Abbildung 2-4 wird die vollständige Visual Studio-Projekt Mappe gezeigt, in der die verschiedenen Projekte organisiert sind.

![Projekte in der Visual Studio-Projekt Mappe.](./media/projects-in-visual-studio-solution.png)

**Abbildung 2-4**. Projekte in der Visual Studio-Projekt Mappe.

Der Code ist für die Unterstützung der verschiedenen-mikrodienste organisiert, und innerhalb der einzelnen mikrodienste wird der Code in Domänen Logik, Infrastrukturprobleme sowie eine Benutzeroberfläche oder ein Dienst Endpunkt aufgeteilt. In vielen Fällen können die Abhängigkeiten jedes Diensts durch Azure-Dienste in der Produktionsumgebung und alternative Optionen für die lokale Entwicklung erfüllt werden. Sehen wir uns an, wie die Anforderungen der Anwendung den Azure-Diensten zugeordnet werden.

## <a name="understanding-microservices"></a>Grundlegendes zu Microservices

Dieses Buch konzentriert sich auf cloudbasierte Anwendungen, die mithilfe der Azure-Technologie erstellt wurden. Weitere Informationen zu bewährten Methoden für microservices und zum Entwerfen von auf microservices basierenden Anwendungen finden Sie im Begleitbuch [.net-microservices: Architektur für .NET-Container Anwendungen](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook).

>[!div class="step-by-step"]
>[Zurück](candidate-apps.md)
>[Weiter](map-eshoponcontainers-azure-services.md)
