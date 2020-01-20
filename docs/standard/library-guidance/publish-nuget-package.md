---
title: Veröffentlichen eines NuGet-Pakets
description: Best Practices für die Veröffentlichung von .NET-Bibliotheken in NuGet.
ms.date: 10/02/2018
ms.openlocfilehash: e567fe3f7e00bf322cdd50786e50128961107469
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706464"
---
# <a name="publishing-a-nuget-package"></a>Veröffentlichen eines NuGet-Pakets

NuGet-Pakete werden über Paketrepositorys veröffentlicht und verwendet. NuGet.org ist zwar das bekannteste und am weitesten verbreitete Repository, es gibt jedoch viele Stellen für die Veröffentlichung von NuGet-Paketen:

* **[NuGet.org](https://www.nuget.org/)** ist das primäre Onlinerepository für NuGet-Pakete. Alle Pakete auf NuGet.org sind für jeden öffentlich verfügbar. Visual Studio verwendet NuGet.org standardmäßig als Paketquelle, und für viele Entwickler ist NuGet.org das einzige Paketrepository, mit dem sie interagieren. NuGet.org ist der beste Ort zum Veröffentlichen stabiler Pakete und Vorabversionen von Paketen, zu denen Sie Communityfeedback erhalten möchten.

* **[MyGet](https://myget.org/)** ist ein Repositorydienst, der benutzerdefinierte Paketfeeds für Open Source-Projekte unterstützt. Ein öffentlicher benutzerdefinierter MyGet-Feed ist ein idealer Ort zum Veröffentlichen von Vorabversionen von Paketen, die von Ihrem CI-Dienst erstellt wurden. MyGet bietet auch private Feeds kommerziell an.

* Mit einem **[lokalen Feed](/nuget/hosting-packages/local-feeds)** können Sie einen Ordner wie ein Paketrepository behandeln. Zudem macht er die `*.nupkg`-Dateien im Ordner für NuGet zugänglich. Ein lokaler Feed eignet sich zum Testen eines NuGet-Pakets, bevor Sie es bei NuGet.org veröffentlichen.

> [!NOTE]
> In NuGet.org [kann ein Paket nicht mehr gelöscht werden](/nuget/policies/deleting-packages), nachdem es hochgeladen wurde. Ein Paket kann von der Liste entfernt werden, sodass es in der Benutzeroberfläche nicht mehr öffentlich sichtbar ist. Die Datei `*.nupkg` kann jedoch bei Wiederherstellung weiterhin heruntergeladen werden. Darüber hinaus lässt nuget.org keine doppelten Paketversionen zu. Um ein NuGet-Paket mit einem Fehler zu korrigieren, müssen Sie das fehlerhafte Paket aus der Liste entfernen, die Versionsnummer erhöhen und eine neue Version des Pakets veröffentlichen.

**✔️ VERÖFFENTLICHEN** [Sie stabile Pakete und Vorabversionen von Paketen](/nuget/create-packages/publish-a-package), zu denen Sie Communityfeedback erhalten möchten, in NuGet.org.

**✔️ ERWÄGEN** Sie die Veröffentlichung von Vorabversionen von Paketen aus einem Continuous Integration-Build in einen MyGet-Feed.

**✔️ ERWÄGEN** Sie das Testen von Paketen in Ihrer Entwicklungsumgebung mit einem lokalen Feed oder MyGet. Überprüfen Sie, ob das Paket funktioniert, und veröffentlichen Sie es dann in NuGet.org.

## <a name="nugetorg-security"></a>NuGet.org-Sicherheit

Es ist wichtig, dass keine Angreifer Zugriff auf Ihr NuGet-Konto erhalten und eine schädliche Version Ihrer Bibliothek hochladen. NuGet.org bietet zweistufige Authentifizierung und E-Mail-Benachrichtigungen, wenn ein Paket veröffentlicht wird. Aktivieren Sie diese Features nach der Anmeldung bei NuGet.org auf der Seite **Kontoeinstellungen**.

![Alternativer Text](./media/publish-nuget-package/nuget-2fa.png "NuGet-Kontosicherheit")

**✔️ VERWENDEN️** Sie ein Microsoft-Konto zur Anmeldung bei NuGet.

**✔️ AKTIVIEREN** Sie die zweistufige Authentifizierung für den Zugriff auf NuGet.

**✔️ AKTIVIEREN️** Sie die E-Mail-Benachrichtigung bei Veröffentlichung eines Pakets.

>[!div class="step-by-step"]
>[Zurück](sourcelink.md)
>[Weiter](versioning.md)
