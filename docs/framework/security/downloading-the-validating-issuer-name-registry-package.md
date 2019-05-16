---
title: Herunterladen des Pakets zur Validierung der Ausstellernamenregistration
ms.date: 10/10/2018
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 5684844f1db33b075df099b3026d9d0c1061199f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631848"
---
# <a name="download-the-validating-issuer-name-registry-package"></a>Der Aussteller Pakets zur Validierung der herunterladen

In diesem Thema wird erläutert, wie "Überprüfen der Ausstellernamensregistrierung" (VINR) im Projekt heruntergeladen und verwendet wird.

Die VINR ist als NuGet-Paket verfügbar, das die erforderlichen Assemblys und Verweise im Projekt hinzufügt. Wenn Sie NuGet noch nicht installiert haben, wechseln Sie zu [nuget.org](https://nuget.org), um es zu installieren. Sie können den Versionsverlauf für die Erweiterung anzeigen, indem Sie auf der Seite auf NuGet: [Überprüfen der Ausstellernamensregistrierung auf NuGet Microsoft](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)

## <a name="use-the-package-manager-gui"></a>Verwenden Sie die Paket-Manager-GUI

1. Klicken Sie mit der rechten Maustaste in Visual Studio im **Projektmappen-Explorer** auf Ihr Projekt, und wählen Sie dann **NuGet-Pakete verwalten** aus.

2. Klicken Sie im Fenster **NuGet-Pakete verwalten** auf das Suchfeld, geben Sie `ValidatingIssuerNameRegistry` ein, und drücken Sie die **EINGABETASTE**.

3. Klicken Sie im Ergebnisbereich auf die Schaltfläche **Installieren** für das erste Ergebnis.

4. Das Paket wird heruntergeladen. Bevor es dem Projekt hinzugefügt wird, erscheint das Dialogfeld zum Akzeptieren der Lizenz. Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Ich stimme zu**.

5. Die neuesten VINR-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.

## <a name="use-the-package-manager-console"></a>Verwenden Sie die Paket-Manager-Konsole

1. Klicken Sie in Visual Studio auf **Tools** > **NuGet Package Manager** > **-Paket-Manager-Konsole**.

2. Die **Paket-Manager-Konsole** wird angezeigt. Geben Sie folgenden Text ein, und drücken Sie die **EINGABETASTE**:

    ```powershell
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry
    ```

3. Die neuesten VINR-Assemblys werden heruntergeladen und dem Projekt hinzugefügt.
