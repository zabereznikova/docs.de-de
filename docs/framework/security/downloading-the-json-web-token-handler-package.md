---
title: Herunterladen des JSON-Webtokenhandler-Pakets
ms.date: 10/10/2018
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: a8685a71d46778d932595965f32c0041b176bd83
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633527"
---
# <a name="download-the-json-web-token-handler-package"></a>Herunterladen des JSON-Webtokenhandler-Pakets

In diesem Thema wird erläutert, wie der JSON-Webtokenhandler im Projekt heruntergeladen und verwendet wird.

Die JSON-Webtokenhandler-Erweiterung ist als NuGet-Paket verfügbar, das die erforderlichen Assemblys und Verweise im Projekt hinzufügt. Wenn Sie NuGet noch nicht installiert haben, wechseln Sie zu [nuget.org](https://nuget.org), um es zu installieren. Sie können den Versionsverlauf für die Erweiterung anzeigen, indem Sie auf der Seite auf NuGet: [JSON-Webtokenhandler für NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)

## <a name="use-the-package-manager-gui"></a>Verwenden Sie die Paket-Manager-GUI

1. Klicken Sie mit der rechten Maustaste in Visual Studio im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie dann **NuGet-Pakete verwalten** aus.

2. Klicken Sie im Fenster **NuGet-Pakete verwalten** auf das Suchfeld, geben Sie `JWT Token Handler` ein, und drücken Sie die **EINGABETASTE**.

3. Klicken Sie im Ergebnisbereich auf die Schaltfläche **Installieren** für das erste Ergebnis.

4. Das Paket wird heruntergeladen. Bevor es dem Projekt hinzugefügt wird, erscheint das Dialogfeld zum Akzeptieren der Lizenz. Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Ich stimme zu**.

5. Die neueste JSON-Webtokenhandler-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.

## <a name="use-the-package-manager-console"></a>Verwenden Sie die Paket-Manager-Konsole

1. Klicken Sie in Visual Studio auf **Tools** > **NuGet Package Manager** > **-Paket-Manager-Konsole**.

2. Die **Paket-Manager-Konsole** wird angezeigt. Geben Sie folgenden Text ein, und drücken Sie die **EINGABETASTE**:

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. Die neueste JSON-Webtokenhandler-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.
