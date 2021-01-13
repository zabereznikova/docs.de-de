---
title: Übersicht über das Azure SDK für .NET
description: Bietet eine Übersicht über das Azure SDK für .NET und beschreibt die grundlegenden Schritte zur Verwendung des SDK in einer .NET-Anwendung
ms.date: 11/30/2020
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 3ec1ee9e8da3a6e03581ce2a29a655ec0d68fe54
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700902"
---
# <a name="azure-sdk-for-net-overview"></a>Übersicht über das Azure SDK für .NET

## <a name="what-is-the-azure-sdk-for-net"></a>Was ist das Azure SDK für .NET?

Das **Azure SDK für .NET** wurde entwickelt, um die Verwendung von Azure-Diensten aus Ihren .NET-Anwendungen zu vereinfachen.  Das Azure SDK für .NET bietet eine konsistente und vertraute Oberfläche für den Zugriff auf Azure-Dienste, unabhängig davon, ob Dateien in Blob Storage hochgeladen und heruntergeladen, Anwendungsgeheimnisse aus Azure Key Vault abgerufen oder Benachrichtigungen von Azure Event Hubs verarbeitet werden.  

Das Azure SDK für .NET ist als Reihe von NuGet-Paketen verfügbar, die in .NET Core-Anwendungen (2.1 und höher) und .NET Framework (4.6.1 und höher) verwendet werden können.

![Diagramm, das zeigt, wie .NET-Anwendungen mit dem Azure SDK auf Azure-Dienste zugreifen](./media/azure-sdk-for-dotnet-overview.png)

## <a name="use-the-azure-sdk-for-net-in-your-applications"></a>Verwenden des Azure SDK für .NET in Ihren Anwendungen

Wenn Sie ein Azure SDK-Paket in einer Ihrer .NET-Anwendungen verwenden möchten, führen Sie die folgenden Schritte aus.

1. **Suchen des entsprechenden SDK-Pakets:** Verwenden Sie die [Paketliste](../packages.md), um das entsprechende Paket für den verwendeten Azure-Dienst zu suchen.  Beachten Sie, dass die meisten Dienste über ein Clientpaket zum Arbeiten mit dem Dienst und ein Verwaltungspaket zum Erstellen und Verwalten von Instanzen des Diensts verfügen.  In den meisten Fällen benötigen Sie das Clientpaket.  Installieren Sie dieses Paket in Ihrer Anwendung mithilfe von NuGet.

2. **Einrichten der Authentifizierung für Ihre Anwendung:** Für den Zugriff auf Azure-Ressourcen muss Ihre Anwendung über die erforderlichen Anmeldeinformationen und die entsprechenden in Azure zugewiesenen Zugriffsrechte verfügen.  Informationen zum Konfigurieren der Authentifizierung finden Sie unter [Authentifizieren von .NET-Anwendungen in Azure](../authentication.md).

3. **Schreiben von Code mithilfe des SDK in Ihrer Anwendung:** Beim Arbeiten mit Azure-Diensten erstellt der Code zunächst ein Clientobjekt zum Arbeiten mit dem Dienst und ruft dann Methoden für dieses Clientobjekt zum Interagieren mit dem Dienst auf.  Es werden sowohl synchrone als auch asynchrone Methoden bereitgestellt.  Beispiele für die Verwendung der einzelnen SDK-Pakete finden Sie in der Azure-Dokumentation.

4. **Konfigurieren der Protokollierung für das SDK (optional):** Wenn Sie Probleme zwischen Ihrer Anwendung und Azure diagnostizieren müssen, können Sie die [Protokollierung im Azure SDK für .NET aktivieren](./logging.md).
