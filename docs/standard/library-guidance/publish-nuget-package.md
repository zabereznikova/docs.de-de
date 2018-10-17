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
# <a name="publishing-a-nuget-package"></a><span data-ttu-id="f7371-103">Veröffentlichen eines NuGet-Pakets</span><span class="sxs-lookup"><span data-stu-id="f7371-103">Publishing a NuGet package</span></span>

<span data-ttu-id="f7371-104">NuGet-Pakete sind veröffentlicht und von Package-Repositorys verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7371-104">NuGet packages are published and consumed from package repositories.</span></span> <span data-ttu-id="f7371-105">Während "NuGet.org" die am häufigsten bekannten und verwendeten Repository ist, gibt es viele Stellen, um NuGet-Pakete zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="f7371-105">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages:</span></span>

* <span data-ttu-id="f7371-106">**["NuGet.org"](https://www.nuget.org/)**  ist das primäre online-Repository für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="f7371-106">**[NuGet.org](https://www.nuget.org/)** is the primary online repository for NuGet packages.</span></span> <span data-ttu-id="f7371-107">Alle Pakete auf NuGet.org sind für alle öffentlich verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7371-107">All packages on NuGet.org are publicly available to everyone.</span></span> <span data-ttu-id="f7371-108">Standardmäßig Visual Studio verfügt über "NuGet.org" als Paketquelle und für viele Entwickler "NuGet.org" das einzige paketrepository die Interaktion wird.</span><span class="sxs-lookup"><span data-stu-id="f7371-108">By default, Visual Studio has NuGet.org as a package source and for many developers NuGet.org is the only package repository they'll interact with.</span></span> <span data-ttu-id="f7371-109">"NuGet.org" ist der beste Ort zum Veröffentlichen von stabilen Pakete und Vorabversionen von Paketen, denen Sie auf die Community-Feedback möchten.</span><span class="sxs-lookup"><span data-stu-id="f7371-109">NuGet.org is the best place to publish stable packages and pre-release packages that you want community feedback on.</span></span>

* <span data-ttu-id="f7371-110">**[MyGet](https://myget.org/)**  Repository unterstützt [kostenlose anpassungspaket-feeds für Open Source-Projekte](https://www.myget.org/opensource).</span><span class="sxs-lookup"><span data-stu-id="f7371-110">**[MyGet](https://myget.org/)** repository service supports [free custom package feeds for open-source projects](https://www.myget.org/opensource).</span></span> <span data-ttu-id="f7371-111">Ein öffentlicher benutzerdefinierter MyGet-Feed ist ein idealer Ort zum Veröffentlichen von Vorabversionen von Paketen durch den CI-Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="f7371-111">A MyGet public custom feed is an ideal place to publish pre-release packages created by your CI service.</span></span> <span data-ttu-id="f7371-112">MyGet bietet auch die private Feeds im Handel.</span><span class="sxs-lookup"><span data-stu-id="f7371-112">MyGet also provides private feeds commercially.</span></span>

* <span data-ttu-id="f7371-113">Ein **[lokalen Feed](/nuget/hosting-packages/local-feeds)** können Sie einen Ordner, z. B. einem paketrepository behandeln und macht die `*.nupkg` Dateien in den Ordner, die von NuGet zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f7371-113">A **[local feed](/nuget/hosting-packages/local-feeds)** allows you to treat a folder like a package repository and makes the `*.nupkg` files in the folder accessible by NuGet.</span></span> <span data-ttu-id="f7371-114">Ein lokales Feeds eignet sich für ein NuGet-Paket testen, bevor Sie ihn auf NuGet.org veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f7371-114">A local feed is useful for testing a NuGet package before publishing it to NuGet.org.</span></span>

> [!NOTE]
> <span data-ttu-id="f7371-115">"NuGet.org" [lässt sich nicht auf ein Paket zu löschenden](/nuget/policies/deleting-packages) sobald es hochgeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="f7371-115">NuGet.org [does not allow a package to be deleted](/nuget/policies/deleting-packages) once it is uploaded.</span></span> <span data-ttu-id="f7371-116">Ein Paket kann nicht aufgeführte sein, so, dass sie nicht öffentlich sichtbar, in der Benutzeroberfläche ist jedoch `*.nupkg` kann bei der Wiederherstellung weiterhin heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f7371-116">A package can be unlisted so that it is not publicly visible in the UI but the `*.nupkg` can still be downloaded on restore.</span></span> <span data-ttu-id="f7371-117">Darüber hinaus lässt nuget.org keine doppelten Paketversionen.</span><span class="sxs-lookup"><span data-stu-id="f7371-117">Also, nuget.org does not allow duplicate package versions.</span></span> <span data-ttu-id="f7371-118">Erhöht die Versionsnummer, und veröffentlichen Sie eine neue Version des Pakets, um ein NuGet-Paket mit einem Fehler zu beheben, Sie das falsche Paket aus der Liste entfernen müssen.</span><span class="sxs-lookup"><span data-stu-id="f7371-118">To correct a NuGet package with an error you have to unlist the incorrect package, increment the version number and publish a new version of the package.</span></span>

<span data-ttu-id="f7371-119">**✔️ FÜHREN** [veröffentlichen stabile Pakete und Vorabversionen von Paketen](/nuget/create-packages/publish-a-package) Communityfeedback auf NuGet.org angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7371-119">**✔️ DO** [publish stable packages and pre-release packages](/nuget/create-packages/publish-a-package) you want community feedback on to NuGet.org.</span></span>

<span data-ttu-id="f7371-120">**✔️ GGF.** Veröffentlichen von Vorabversionen von Paketen in einen MyGet-feed von einen fortlaufenden Integrationsbuild.</span><span class="sxs-lookup"><span data-stu-id="f7371-120">**✔️ CONSIDER** publishing pre-release packages to a MyGet feed from a continuous integration build.</span></span>

<span data-ttu-id="f7371-121">**✔️ GGF.** Testen in Ihrer Entwicklungsumgebung unter Verwendung einer lokalen Feed oder myget handelt.</span><span class="sxs-lookup"><span data-stu-id="f7371-121">**✔️ CONSIDER** testing packages in your development environment using a local feed or MyGet.</span></span> <span data-ttu-id="f7371-122">Überprüfen Sie das Paket funktioniert, und klicken Sie dann auf NuGet.org veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f7371-122">Check the package works then publish it to NuGet.org.</span></span>

## <a name="nugetorg-security"></a><span data-ttu-id="f7371-123">NuGet.org-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f7371-123">NuGet.org security</span></span>

<span data-ttu-id="f7371-124">Es ist wichtig, dass Angreifer nicht Zugriff auf Ihr NuGet-Konto und eine böswillige Version Ihrer Bibliothek hochladen.</span><span class="sxs-lookup"><span data-stu-id="f7371-124">It's important that bad actors can't access your NuGet account and upload a malicious version of your library.</span></span> <span data-ttu-id="f7371-125">"NuGet.org" bietet zwei-Faktor-Authentifizierung und e-Mail-Benachrichtigungen, wenn ein Paket veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="f7371-125">NuGet.org offers two-factor authentication and email notifications when a package is published.</span></span> <span data-ttu-id="f7371-126">Aktivieren Sie diese Features nach der Anmeldung bei NuGet.org auf die **Kontoeinstellungen** Seite.</span><span class="sxs-lookup"><span data-stu-id="f7371-126">Enable these features after logging into NuGet.org on the **Account settings** page.</span></span>

<span data-ttu-id="f7371-127">![Alternativtext](./media/publish-nuget-package/nuget-2fa.png "Kontosicherheit NuGet")</span><span class="sxs-lookup"><span data-stu-id="f7371-127">![alt text](./media/publish-nuget-package/nuget-2fa.png "NuGet Account Security")</span></span>

<span data-ttu-id="f7371-128">**Führen Sie ✔️** verwenden Sie ein Microsoft-Konto zur Anmeldung beim NuGet.</span><span class="sxs-lookup"><span data-stu-id="f7371-128">**✔️ DO** use a Microsoft account to sign in to NuGet.</span></span>

<span data-ttu-id="f7371-129">**Führen Sie ✔️** zweistufige Authentifizierung für den Zugriff auf NuGet aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f7371-129">**✔️ DO** enable two-factor authentication for accessing NuGet.</span></span>

<span data-ttu-id="f7371-130">**Führen Sie ✔️** e-Mail-Benachrichtigungen aktivieren, wenn ein Paket veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="f7371-130">**✔️ DO** enable email notification when a package is published.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="f7371-131">[Zurück](./sourcelink.md)
[Weiter](./versioning.md)</span><span class="sxs-lookup"><span data-stu-id="f7371-131">[Previous](./sourcelink.md)
[Next](./versioning.md)</span></span>
