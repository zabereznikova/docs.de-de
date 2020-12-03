---
title: 'Breaking Change: Blazor: Aktualisierte Validierungslogik für statische Webressourcen'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Blazor: Aktualisierte Validierungslogik für statische Webressourcen'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f201818c0130739e8da4f42e7b1f3a1987f70d1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759425"
---
# <a name="blazor-updated-validation-logic-for-static-web-assets"></a><span data-ttu-id="f898a-103">Blazor: Aktualisierte Validierungslogik für statische Webressourcen</span><span class="sxs-lookup"><span data-stu-id="f898a-103">Blazor: Updated validation logic for static web assets</span></span>

<span data-ttu-id="f898a-104">Bei der Konfliktvalidierung für statische Webressourcen in ASP.NET Core 3.1 und Blazor WebAssembly 3.2 ist ein Problem aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f898a-104">There was an issue in conflict validation for static web assets in ASP.NET Core 3.1 and Blazor WebAssembly 3.2.</span></span> <span data-ttu-id="f898a-105">Das Problem:</span><span class="sxs-lookup"><span data-stu-id="f898a-105">The issue:</span></span>

* <span data-ttu-id="f898a-106">hat eine ordnungsgemäße Konflikterkennung zwischen den Hostressourcen und den Ressourcen von Razor-Klassenbibliotheken (Razor Class Library, RCL) und Blazor WebAssembly-Apps verhindert</span><span class="sxs-lookup"><span data-stu-id="f898a-106">Prevented proper conflict detection between the host assets and assets from Razor Class Libraries (RCLs) and Blazor WebAssembly apps.</span></span>
* <span data-ttu-id="f898a-107">hatte in erster Linie Auswirkungen für Blazor WebAssembly-Apps, da statische Webressourcen in RCL standardmäßig unter dem Präfix `_content/$(PackageId)` bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="f898a-107">Mostly affects Blazor WebAssembly apps, since by default, static web assets in RCLs are served under the `_content/$(PackageId)` prefix.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f898a-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="f898a-108">Version introduced</span></span>

<span data-ttu-id="f898a-109">5.0</span><span class="sxs-lookup"><span data-stu-id="f898a-109">5.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="f898a-110">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="f898a-110">Old behavior</span></span>

<span data-ttu-id="f898a-111">Bei der Entwicklung konnten die statischen Webressourcen einer RCL ohne Warnung mit den Ressourcen des Hostprojekts auf demselben Hostpfad überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f898a-111">During development, an RCL's static web assets could be silently overridden with host project assets on the same host path.</span></span> <span data-ttu-id="f898a-112">Gehen Sie von einer RCL aus, die eine statische Webressource definiert hat, die unter */folder/file.txt* bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f898a-112">Consider an RCL that has defined a static web asset to be served at */folder/file.txt*.</span></span> <span data-ttu-id="f898a-113">Wenn der Host eine Datei in *wwwroot/folder/file.txt* platzierte, überschrieb die Datei auf dem Server ohne Warnung die Datei in der RCL oder in der Blazor WebAssembly-App.</span><span class="sxs-lookup"><span data-stu-id="f898a-113">If the host placed a file at *wwwroot/folder/file.txt*, the file on the server silently overrode the file on the RCL or Blazor WebAssembly app.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="f898a-114">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="f898a-114">New behavior</span></span>

<span data-ttu-id="f898a-115">ASP.NET Core erkennt dieses Problem und</span><span class="sxs-lookup"><span data-stu-id="f898a-115">ASP.NET Core correctly detects when this issue happens.</span></span> <span data-ttu-id="f898a-116">informiert den Benutzer über den Konflikt, damit er entsprechend reagieren kann.</span><span class="sxs-lookup"><span data-stu-id="f898a-116">It informs you, the user, of the conflict so that you can take the appropriate action.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f898a-117">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="f898a-117">Reason for change</span></span>

<span data-ttu-id="f898a-118">Statische Webressourcen sollten nicht durch Dateien auf dem Host *wwwroot* des Projekts überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="f898a-118">Static web assets weren't intended to be overridable by files on the *wwwroot* host of the project.</span></span> <span data-ttu-id="f898a-119">Das Überschreiben dieser Dateien kann zu Fehlern führen, die schwierig zu diagnostizieren sind.</span><span class="sxs-lookup"><span data-stu-id="f898a-119">Allowing for the overriding of those files could lead to errors that are difficult to diagnose.</span></span> <span data-ttu-id="f898a-120">Dadurch können nicht definierte Behavior Changes in veröffentlichten Apps auftreten.</span><span class="sxs-lookup"><span data-stu-id="f898a-120">The result could be undefined behavior changes in published apps.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f898a-121">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="f898a-121">Recommended action</span></span>

<span data-ttu-id="f898a-122">Standardmäßig gibt es keinen Grund für einen Konflikt zwischen einer RCL-Datei und einer Datei auf dem Host.</span><span class="sxs-lookup"><span data-stu-id="f898a-122">By default, there's no reason for an RCL file to conflict with a file on the host.</span></span> <span data-ttu-id="f898a-123">RCL-Dateien haben das Präfix `_content/${PackageId}`.</span><span class="sxs-lookup"><span data-stu-id="f898a-123">RCL files are prefixed with `_content/${PackageId}`.</span></span> <span data-ttu-id="f898a-124">Blazor WebAssembly-Dateien werden im Stammverzeichnis der Host-URL gespeichert. Dadurch können schneller Konflikte entstehen.</span><span class="sxs-lookup"><span data-stu-id="f898a-124">Blazor WebAssembly files are placed at the root of the host URL space, which makes conflicts easier.</span></span> <span data-ttu-id="f898a-125">Blazor Webassembly-Apps enthalten beispielsweise eine *favicon.ico*-Datei, die der Host möglicherweise auch in seinem *wwwroot*-Stammordner platziert.</span><span class="sxs-lookup"><span data-stu-id="f898a-125">For example, Blazor WebAssembly apps contain a *favicon.ico* file that the host might also include in its *wwwroot* folder.</span></span>

<span data-ttu-id="f898a-126">Wenn die Konfliktquelle eine RCL-Datei ist, bedeutet dies häufig, dass Code Ressourcen aus der Bibliothek in den Ordner *wwwroot* des Projekts kopiert.</span><span class="sxs-lookup"><span data-stu-id="f898a-126">If the conflict's source is an RCL file, it often means code is copying assets from the library into the project's *wwwroot* folder.</span></span> <span data-ttu-id="f898a-127">Das Schreiben von Code zum Kopieren von Dateien widerspricht einem der Hauptziele von statischen Webressourcen.</span><span class="sxs-lookup"><span data-stu-id="f898a-127">Writing code to copy files defeats a primary goal of static web assets.</span></span> <span data-ttu-id="f898a-128">Dieses Ziel muss erfüllt sein, damit Sie Updates für den Browser erhalten, wenn die Inhalte aktualisiert werden, ohne eine neue Kompilierung auslösen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="f898a-128">This goal is fundamental to get updates on the browser when the contents are updated without having to trigger a new compilation.</span></span>

<span data-ttu-id="f898a-129">Sie können dieses Verhalten beibehalten und die Datei auf dem Host verwalten.</span><span class="sxs-lookup"><span data-stu-id="f898a-129">You may choose to preserve this behavior and maintain the file on the host.</span></span> <span data-ttu-id="f898a-130">Entfernen Sie hierzu die Datei aus der Liste der statischen Webressourcen mithilfe eines benutzerdefinierten MSBuild-Ziels.</span><span class="sxs-lookup"><span data-stu-id="f898a-130">To do so, remove the file from the list of static web assets with a custom MSBuild target.</span></span>

<span data-ttu-id="f898a-131">Wenn Sie die RCL-Datei oder die Datei der Blazor WebAssembly-App anstelle der Datei des Hostprojekts verwenden möchten, entfernen Sie die Datei aus dem Hostprojekt.</span><span class="sxs-lookup"><span data-stu-id="f898a-131">To use the RCL's file or the Blazor WebAssembly app's file instead of the host project's file, remove the file from the host project.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f898a-132">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f898a-132">Affected APIs</span></span>

<span data-ttu-id="f898a-133">Keine</span><span class="sxs-lookup"><span data-stu-id="f898a-133">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
