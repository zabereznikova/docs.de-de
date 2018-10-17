---
title: Veröffentlichen eines NuGet-Pakets
description: Empfehlungen für bewährte Methoden für die Veröffentlichung von .NET Bibliotheken in NuGet.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 0602712311411ef3d59825bec8c5e550bc8d8265
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370051"
---
# <a name="publishing-a-nuget-package"></a>Veröffentlichen eines NuGet-Pakets

NuGet-Pakete sind veröffentlicht und von Package-Repositorys verwendet. Während "NuGet.org" die am häufigsten bekannten und verwendeten Repository ist, gibt es viele Stellen, um NuGet-Pakete zu veröffentlichen:

* **["NuGet.org"](https://www.nuget.org/)**  ist das primäre online-Repository für NuGet-Pakete. Alle Pakete auf NuGet.org sind für alle öffentlich verfügbar. Standardmäßig Visual Studio verfügt über "NuGet.org" als Paketquelle und für viele Entwickler "NuGet.org" das einzige paketrepository die Interaktion wird. "NuGet.org" ist der beste Ort zum Veröffentlichen von stabilen Pakete und Vorabversionen von Paketen, denen Sie auf die Community-Feedback möchten.

* **[MyGet](https://myget.org/)**  Repository unterstützt [kostenlose anpassungspaket-feeds für Open Source-Projekte](https://www.myget.org/opensource). Ein öffentlicher benutzerdefinierter MyGet-Feed ist ein idealer Ort zum Veröffentlichen von Vorabversionen von Paketen durch den CI-Dienst erstellt. MyGet bietet auch die private Feeds im Handel.

* Ein **[lokalen Feed](/nuget/hosting-packages/local-feeds)** können Sie einen Ordner, z. B. einem paketrepository behandeln und macht die `*.nupkg` Dateien in den Ordner, die von NuGet zugegriffen werden kann. Ein lokales Feeds eignet sich für ein NuGet-Paket testen, bevor Sie ihn auf NuGet.org veröffentlichen.

> [!NOTE]
> "NuGet.org" [lässt sich nicht auf ein Paket zu löschenden](/nuget/policies/deleting-packages) sobald es hochgeladen wurde. Ein Paket kann nicht aufgeführte sein, so, dass sie nicht öffentlich sichtbar, in der Benutzeroberfläche ist jedoch `*.nupkg` kann bei der Wiederherstellung weiterhin heruntergeladen werden. Darüber hinaus lässt nuget.org keine doppelten Paketversionen. Erhöht die Versionsnummer, und veröffentlichen Sie eine neue Version des Pakets, um ein NuGet-Paket mit einem Fehler zu beheben, Sie das falsche Paket aus der Liste entfernen müssen.

**✔️ FÜHREN** [veröffentlichen stabile Pakete und Vorabversionen von Paketen](/nuget/create-packages/publish-a-package) Communityfeedback auf NuGet.org angezeigt werden sollen.

**✔️ GGF.** Veröffentlichen von Vorabversionen von Paketen in einen MyGet-feed von einen fortlaufenden Integrationsbuild.

**✔️ GGF.** Testen in Ihrer Entwicklungsumgebung unter Verwendung einer lokalen Feed oder myget handelt. Überprüfen Sie das Paket funktioniert, und klicken Sie dann auf NuGet.org veröffentlichen.

## <a name="nugetorg-security"></a>NuGet.org-Sicherheit

Es ist wichtig, dass Angreifer nicht Zugriff auf Ihr NuGet-Konto und eine böswillige Version Ihrer Bibliothek hochladen. "NuGet.org" bietet zwei-Faktor-Authentifizierung und e-Mail-Benachrichtigungen, wenn ein Paket veröffentlicht wird. Aktivieren Sie diese Features nach der Anmeldung bei NuGet.org auf die **Kontoeinstellungen** Seite.

![Alternativtext](./media/publish-nuget-package/nuget-2fa.png "Kontosicherheit NuGet")

**Führen Sie ✔️** verwenden Sie ein Microsoft-Konto zur Anmeldung beim NuGet.

**Führen Sie ✔️** zweistufige Authentifizierung für den Zugriff auf NuGet aktivieren.

**Führen Sie ✔️** e-Mail-Benachrichtigungen aktivieren, wenn ein Paket veröffentlicht wird.

>[!div class="step-by-step"]
[Zurück](./sourcelink.md)
[Weiter](./versioning.md)
