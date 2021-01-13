---
title: Konfigurieren von Visual Studio Code für die Azure-Entwicklung mit .NET
description: Dieser Artikel unterstützt Sie beim Konfigurieren von Visual Studio Code für die Azure-Entwicklung, einschließlich der Installation und Konfiguration der richtigen Plug-Ins in VS Code.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 65ced99befe12d137062b4ea6a59a1ccd3099e0b
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700937"
---
# <a name="configure-visual-studio-code-for-azure-development"></a>Konfigurieren von Visual Studio Code für die Azure-Entwicklung

Wenn Sie Visual Studio Code verwenden (ob nun für die .NET-Entwicklung, zum Erstellen von Single-Page-Webanwendungen mit Frameworks wie Angular, React oder Vue oder zum Programmieren von Anwendungen in einer anderen Sprache, z. B. Python), sollten Sie Visual Studio Code für die Azure-Entwicklung konfigurieren.

### <a name="download-visual-studio-code"></a>Visual Studio Code herunterladen

Wenn Visual Studio Code bereits installiert ist, können Sie diesen Schritt überspringen.

> [!div class="nextstepaction"]
> [Visual Studio Code herunterladen](https://code.visualstudio.com/download)

### <a name="install-the-azure-tools-extension-pack"></a>Installieren des Azure-Tools-Erweiterungspakets

Mit dem [Azure-Tools-Erweiterungspaket](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) erhalten Sie Erweiterungen für die Arbeit mit Azure App Service, Azure Functions, Azure Storage, Cosmos DB und Azure Virtual Machines in einem einzigen praktischen Paket.

So installieren Sie die Erweiterung über Visual Studio Code:

1. Drücken Sie <kbd>STRG+UMSCHALT+X</kbd>, um das Fenster **Erweiterungen** zu öffnen.
1. Suchen Sie nach der Erweiterung *Azure-Tools*.
1. Wählen Sie die Schaltfläche **Installieren** aus.

![Screenshot: Visual Studio Code mit Panel „Erweiterungen“ mit Suche nach dem Azure-Tools-Erweiterungspaket](./media/visual-studio-code-azure-tools.png)

Weitere Informationen zur Installation von Erweiterungen in Visual Studio Code finden Sie im Dokument zum [Marketplace für Erweiterungen](https://code.visualstudio.com/docs/editor/extension-gallery) auf der Visual Studio Code-Website.

### <a name="sign-in-to-your-azure-account-with-azure-tools"></a>Anmelden bei Ihrem Azure-Konto mit den Azure-Tools

Im linken Panel wird ein Azure-Symbol angezeigt. Klicken Sie auf dieses Symbol, um Einstellungen für Azure-Dienste anzuzeigen. Klicken Sie unter einem beliebigen Dienst auf **Sign in to Azure...** (Bei Azure anmelden...), um den Authentifizierungsprozess für die Azure-Tools in Visual Studio Code abzuschließen.

![Screenshot: Anmeldung bei Azure für die Azure-Tools in Visual Studio Code](./media/visual-studio-code-azure-login.png)

### <a name="next-steps"></a>Nächste Schritte

Als Nächstes sollten Sie die Azure CLI auf Ihrer Arbeitsstation installieren.

> [!div class="nextstepaction"]
> [Installieren der Azure-Befehlszeilenschnittstelle](./install-azure-cli.md)
