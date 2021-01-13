---
title: Konfigurieren von Visual Studio für die Azure-Entwicklung mit .NET
description: Dieser Artikel unterstützt Sie beim Konfigurieren von Visual Studio für die Azure-Entwicklung, einschließlich der Installation der richtigen Workloads und des Herstellens einer Verbindung zwischen Visual Studio und Ihrem Azure-Konto.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 986469bd07657d968045465803047dc21d76dd62
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700940"
---
# <a name="configure-visual-studio-for-azure-development-with-net"></a>Konfigurieren von Visual Studio für die Azure-Entwicklung mit .NET

Visual Studio enthält Tools, die Sie bei der Entwicklung und Bereitstellung von Anwendungen in Azure unterstützen.  Dieser Leitfaden hilft Ihnen dabei, sicherzustellen, dass Sie Visual Studio ordnungsgemäß für die Azure-Entwicklung konfiguriert haben.

### <a name="download-visual-studio-2019"></a>Herunterladen von Visual Studio 2019

Wenn Visual Studio 2019 bereits installiert ist, können Sie diesen Schritt überspringen.

> [!div class="nextstepaction"]
> [Herunterladen von Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="install-azure-workloads"></a>Installieren von Azure-Workloads

Starten Sie den **Visual Studio-Installer**, und stellen Sie sicher, dass die Workloads **Azure-Entwicklung** und **ASP.NET und Webentwicklung** installiert sind.  Wenn eine dieser Workloads nicht installiert ist, klicken Sie auf diese, um sie zu installieren.

![Screenshot: Der Visual Studio-Installer mit den ausgewählten Workloads „Azure-Entwicklung“ und „ASP.NET und Webentwicklung“](./media/visual-studio-installer-azure-development.png)

### <a name="authenticate-visual-studio-with-azure"></a>Authentifizieren von Visual Studio mit Azure

Beim Debuggen von Apps über Visual Studio kann sich Visual Studio mit Ihrem Azure-Konto bei Azure-Ressourcen authentifizieren und auf diese Ressourcen zugreifen.  Dieses Konto wird auch verwendet, wenn Sie Apps direkt aus Visual Studio in Azure veröffentlichen.

Klicken Sie auf **Extras** > **Optionen**, um das Dialogfeld **Optionen** zu öffnen und Ihr Azure-Konto über Visual Studio zu authentifizieren. Navigieren Sie zu den `Azure Service Authentication`-Optionen (Azure-Dienstauthentifizierung), und melden Sie sich mit Ihrem Azure-Konto an.

![Screenshot: Visual Studio-Dialogfeld „Optionen“ mit Azure-Anmeldung](./media/visual-studio-azure-login-dialog.png)

### <a name="next-steps"></a>Nächste Schritte

Wenn Sie auch [Visual Studio Code](https://code.visualstudio.com/) für die Entwicklung in .NET oder einer anderen Sprache verwenden, sollten Sie außerdem [Visual Studio Code für die Azure-Entwicklung](./configure-vs-code.md) konfigurieren. Fahren Sie andernfalls mit dem [Installieren der Azure CLI](./install-azure-cli.md) fort.
