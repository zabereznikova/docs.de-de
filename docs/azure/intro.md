---
title: Erste Schritte mit Azure und .NET
description: Lernen Sie die erforderlichen Grundlagen von Azure und .NET kennen.
ms.date: 06/20/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: b5766012b77da88ae9a696939b6e498ebc421522
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025041"
---
# <a name="introduction-to-azure-and-net"></a>Einführung in Azure und .NET

## <a name="what-is-azure"></a>Was ist Azure?

Azure ist eine Cloudplattform, die entwickelt wurde, um das Entwickeln moderner Anwendungen zu vereinfachen.  Ob Sie Ihre Anwendungen vollständig in Azure hosten oder Ihre lokalen Anwendungen mit Azure-Diensten erweitern möchten, Azure unterstützt Sie beim Erstellen skalierbarer, zuverlässiger und verwaltbarer Anwendungen.  Dank der umfassenden Unterstützung in Tools, die Sie bereits verwenden, wie Visual Studio und Visual Studio Code, und einer umfassenden SDK-Bibliothek sorgt Azure von Anfang an für eine gesteigerte Produktivität bei der .NET-Entwicklung.

## <a name="application-development-scenarios-on-azure"></a>Szenarios für die Anwendungsentwicklung in Azure

Abhängig von Ihren Anforderungen können Sie Azure auf unterschiedliche Weise in Ihre Anwendung integrieren.

- **Anwendungshosting in Azure:** Azure kann Ihren gesamten Anwendungsstapel hosten, von Webanwendungen und APIs über Datenbanken bis hin zu Speicherdiensten. Azure unterstützt eine Vielzahl von Hostingmodellen, von vollständig verwalteten Diensten über Container bis hin zu virtuellen Computern. Bei der Verwendung vollständig verwalteter Azure-Dienste können Ihre Anwendungen von der in Azure integrierten Skalierbarkeit, Hochverfügbarkeit und Sicherheit profitieren.

- **Nutzen von Clouddiensten für Anwendungen:** Vorhandene Apps können Azure-Dienste integrieren, um ihren Funktionsumfang zu erweitern.  Dies kann das Hinzufügen von Funktionen für die Volltextsuche mit [Azure Cognitive Search](/azure/search/search-what-is-azure-search) beinhalten, das sichere Speichern von Anwendungsgeheimnissen in [Azure Key Vault](/azure/key-vault/) oder das Hinzufügen von Funktionen für maschinelles Sehen, Spracherkennung, Language Understanding mit [Azure Cognitive Services](/azure/cognitive-services/).  Diese Dienste werden vollständig von Azure verwaltet und können problemlos zu Ihrer Anwendung hinzugefügt werden, ohne die aktuelle Anwendungsarchitektur oder das Bereitstellungsmodell zu ändern.

- **Moderne serverlose Architekturen:** Azure Functions vereinfacht das Entwickeln von Lösungen für ereignisgesteuerte Workflows, ob beim Antworten auf HTTP-Anforderungen, Ausführen von Dateiuploads in Blob Storage oder Verarbeiten von Ereignissen in einer Warteschlange.  Sie schreiben nur den Code, der für die Verarbeitung des Ereignisses erforderlich ist, und müssen sich keine Gedanken um Server oder Framework-Code zu machen.  Außerdem können Sie über 250 Connectors für andere Azure-und Drittanbieterdienste nutzen, um selbst sehr komplexe Integrationsprobleme zu lösen.

## <a name="access-azure-services-from-net-applications"></a>Zugreifen auf Azure-Dienste über .NET-Anwendungen

Unabhängig davon, ob Ihre App in Azure oder lokal gehostet wird, erfolgt der Zugriff auf die meisten Azure-Dienste über das **Azure SDK für .NET**.  Das Azure SDK für .NET wird als Reihe von NuGet-Paketen bereitgestellt, die in .NET Core-Anwendungen (2.1 und höher) und .NET Framework (4.6.1 und höher) verwendet werden können. Mit dem Azure SDK für .NET ist das Einbinden von Azure-Diensten in Ihre Anwendung so einfach wie das Installieren des richtigen NuGet-Pakets, das Instanziieren eines Clientobjekts und das Aufrufen der entsprechenden Methoden. Weitere Informationen zum Azure SDK für .NET finden Sie in der [Übersicht über das Azure SDK für .NET](./sdk/azure-sdk-for-dotnet.md).

![Diagramm, das zeigt, wie .NET-Anwendungen mit dem Azure SDK auf Azure-Dienste zugreifen](./media/azure-sdk-for-dotnet-overview.png)

## <a name="next-steps"></a>Nächste Schritte

Lernen Sie als Nächstes die am [häufigsten verwendeten Azure-Dienste](./key-azure-services.md) für die .NET-Entwicklung kennen.
