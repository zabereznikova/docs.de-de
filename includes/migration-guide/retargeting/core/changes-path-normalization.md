---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614463"
---
### <a name="changes-in-path-normalization"></a><span data-ttu-id="469d2-101">Änderungen an der Pfadnormalisierung</span><span class="sxs-lookup"><span data-stu-id="469d2-101">Changes in path normalization</span></span>

#### <a name="details"></a><span data-ttu-id="469d2-102">Details</span><span class="sxs-lookup"><span data-stu-id="469d2-102">Details</span></span>

<span data-ttu-id="469d2-103">Bei Apps, die die Zielplattform .NET Framework 4.6.2 und höher verwenden, wurde im Vergleich zu früheren Versionen die Art und Weise verändert, in der die Laufzeit Pfade normalisiert. Das Normalisieren eines Pfads umfasst das Verändern der Zeichenfolge, die einen Pfad oder eine Datei identifiziert, sodass sie einem gültigen Pfad auf dem Zielbetriebssystem entspricht.</span><span class="sxs-lookup"><span data-stu-id="469d2-103">Starting with apps that target the .NET Framework 4.6.2, the way in which the runtime normalizes paths has changed.Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="469d2-104">Normalisierung umfasst ist in der Regel:</span><span class="sxs-lookup"><span data-stu-id="469d2-104">Normalization typically involves:</span></span>

- <span data-ttu-id="469d2-105">Die Kanonisierung von Komponenten- und Verzeichnistrennzeichen.</span><span class="sxs-lookup"><span data-stu-id="469d2-105">Canonicalizing component and directory separators.</span></span>
- <span data-ttu-id="469d2-106">Die Anwendung des aktuellen Verzeichnisses auf einen relativen Pfad.</span><span class="sxs-lookup"><span data-stu-id="469d2-106">Applying the current directory to a relative path.</span></span>
- <span data-ttu-id="469d2-107">Die Auswertung des relativen Verzeichnisses (.) oder des übergeordneten Verzeichnisses (..) in einem Pfad.</span><span class="sxs-lookup"><span data-stu-id="469d2-107">Evaluating the relative directory (.) or the parent directory (..) in a path.</span></span>
- <span data-ttu-id="469d2-108">Das Verkürzen um angegebene Zeichen.</span><span class="sxs-lookup"><span data-stu-id="469d2-108">Trimming specified characters.</span></span>
<span data-ttu-id="469d2-109">Für Apps, die die Zielplattform .NET Framework 4.6.2 und höher verwenden, sind die folgenden Änderungen an der Pfadnormalisierung standardmäßig aktiviert:</span><span class="sxs-lookup"><span data-stu-id="469d2-109">Starting with apps that target the .NET Framework 4.6.2, the following changes in path normalization are enabled by default:</span></span>
  - <span data-ttu-id="469d2-110">Die Runtime greift auf die Funktion [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) des Betriebssystems zurück, um Pfade zu normalisieren.</span><span class="sxs-lookup"><span data-stu-id="469d2-110">The runtime defers to the operating system's [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) function to normalize paths.</span></span>
- <span data-ttu-id="469d2-111">Die Normalisierung beinhaltet nicht mehr das Verkürzen des Endes von Verzeichnissegmenten (etwa im Fall eines Leerzeichens am Ende eines Verzeichnisnamens).</span><span class="sxs-lookup"><span data-stu-id="469d2-111">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>
- <span data-ttu-id="469d2-112">Unterstützung für Gerätepfadsyntax mit vollem Vertrauen, einschließlich `\\.\` und `\\?\` für Datei-E/A-APIs in mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="469d2-112">Support for device path syntax in full trust, including `\\.\` and, for file I/O APIs in mscorlib.dll, `\\?\`.</span></span>
- <span data-ttu-id="469d2-113">Die Runtime überprüft Gerätesyntaxpfade nicht.</span><span class="sxs-lookup"><span data-stu-id="469d2-113">The runtime does not validate device syntax paths.</span></span>
- <span data-ttu-id="469d2-114">Die Verwendung von Gerätesyntax für den Zugriff auf alternative Datenströme wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="469d2-114">The use of device syntax to access alternate data streams is supported.</span></span>
<span data-ttu-id="469d2-115">Diese Änderungen verbessern die Leistung und ermöglichen zugleich Methoden den Zugriff auf zuvor nicht zugängliche Pfade.</span><span class="sxs-lookup"><span data-stu-id="469d2-115">These changes improve performance while allowing methods to access previously inaccessible paths.</span></span> <span data-ttu-id="469d2-116">Apps mit der Zielplattform .NET Framework 4.6.1 und früheren Versionen, die unter .NET Framework 4.6.2 oder höher ausgeführt werden, sind von dieser Änderung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="469d2-116">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="469d2-117">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="469d2-117">Suggestion</span></span>

<span data-ttu-id="469d2-118">Apps mit der Zielplattform .NET Framework 4.6.2 oder höher können die Änderung deaktivieren und die Legacynormalisierung verwenden, indem dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei Folgendes hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="469d2-118">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

<span data-ttu-id="469d2-119">Für Apps mit der Zielplattform .NET Framework 4.6.1 oder niedriger, die unter .NET Framework 4.6.2 oder höher ausgeführt werden, können die Änderungen an der Pfadnormalisierung aktiviert werden, indem dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei die folgende Zeile hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="469d2-119">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| <span data-ttu-id="469d2-120">name</span><span class="sxs-lookup"><span data-stu-id="469d2-120">Name</span></span>    | <span data-ttu-id="469d2-121">Wert</span><span class="sxs-lookup"><span data-stu-id="469d2-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="469d2-122">Bereich</span><span class="sxs-lookup"><span data-stu-id="469d2-122">Scope</span></span>   | <span data-ttu-id="469d2-123">Gering</span><span class="sxs-lookup"><span data-stu-id="469d2-123">Minor</span></span>       |
| <span data-ttu-id="469d2-124">Version</span><span class="sxs-lookup"><span data-stu-id="469d2-124">Version</span></span> | <span data-ttu-id="469d2-125">4.6.2</span><span class="sxs-lookup"><span data-stu-id="469d2-125">4.6.2</span></span>       |
| <span data-ttu-id="469d2-126">Typ</span><span class="sxs-lookup"><span data-stu-id="469d2-126">Type</span></span>    | <span data-ttu-id="469d2-127">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="469d2-127">Retargeting</span></span> |
