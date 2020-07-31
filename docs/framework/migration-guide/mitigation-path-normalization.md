---
title: 'Entschärfung: Pfadnormalisierung'
description: In diesem Artikel erfahren Sie, welche Veränderungen sich bei der Pfadnormalisierung in Apps ergeben, die auf .NET Framework 4.6.2 oder höher ausgerichtet sind.
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 89dcc46d9f266ffd3635dc0cc02b634720356eda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475215"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="8023b-103">Entschärfung: Pfadnormalisierung</span><span class="sxs-lookup"><span data-stu-id="8023b-103">Mitigation: Path Normalization</span></span>
<span data-ttu-id="8023b-104">Bei Apps, die für .NET Framework 4.6.2 oder höher entwickelt wurden, ergeben sich Änderungen bei der Pfadnormalisierung im .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8023b-104">Starting with apps that target .NET Framework 4.6.2, path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="8023b-105">Was ist Pfadnormalisierung?</span><span class="sxs-lookup"><span data-stu-id="8023b-105">What is path normalization?</span></span>  
 <span data-ttu-id="8023b-106">Das Normalisieren eines Pfads beinhaltet das Verändern der Zeichenfolge, die einen Pfad oder eine Datei kennzeichnet, in einer Weise, dass sie einem gültigen Pfad im Zielbetriebssystem entspricht.</span><span class="sxs-lookup"><span data-stu-id="8023b-106">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="8023b-107">Normalisierung umfasst ist in der Regel:</span><span class="sxs-lookup"><span data-stu-id="8023b-107">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="8023b-108">Die Kanonisierung von Komponenten- und Verzeichnistrennzeichen.</span><span class="sxs-lookup"><span data-stu-id="8023b-108">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="8023b-109">Die Anwendung des aktuellen Verzeichnisses auf einen relativen Pfad.</span><span class="sxs-lookup"><span data-stu-id="8023b-109">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="8023b-110">Die Auswertung des relativen Verzeichnisses (`.`) oder des übergeordneten Verzeichnisses (`..`) in einem Pfad.</span><span class="sxs-lookup"><span data-stu-id="8023b-110">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="8023b-111">Das Verkürzen um angegebene Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8023b-111">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="8023b-112">Die Änderungen</span><span class="sxs-lookup"><span data-stu-id="8023b-112">The changes</span></span>  
 <span data-ttu-id="8023b-113">Ab Apps, die gezielt .NET Framework 4.6.2 verwenden, ändert sich die Pfadnormalisierung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8023b-113">Starting with apps that target the .NET Framework 4.6.2, path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="8023b-114">Die Runtime greift auf die Funktion [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) des Betriebssystems zurück, um Pfade zu normalisieren.</span><span class="sxs-lookup"><span data-stu-id="8023b-114">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="8023b-115">Die Normalisierung beinhaltet nicht mehr das Verkürzen des Endes von Verzeichnissegmenten (etwa im Fall eines Leerzeichens am Ende eines Verzeichnisnamens).</span><span class="sxs-lookup"><span data-stu-id="8023b-115">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="8023b-116">Unterstützung für Gerätepfadsyntax mit vollem Vertrauen, einschließlich `\\.\` und `\\?\` für Datei-E/A-APIs in mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="8023b-116">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="8023b-117">Die Runtime überprüft Gerätesyntaxpfade nicht.</span><span class="sxs-lookup"><span data-stu-id="8023b-117">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="8023b-118">Die Verwendung von Gerätesyntax für den Zugriff auf alternative Datenströme wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8023b-118">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="8023b-119">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="8023b-119">Impact</span></span>  

<span data-ttu-id="8023b-120">Für Apps, die gezielt .NET Framework 4.6.2 oder eine höhere Version verwenden, sind diese Änderungen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8023b-120">For apps that target the .NET Framework 4.6.2 or later, these changes are on  by default.</span></span> <span data-ttu-id="8023b-121">Sie sollten die Leistung verbessern und Methoden zugleich den Zugriff auf zuvor nicht zugängliche Pfade ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8023b-121">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
<span data-ttu-id="8023b-122">Apps mit der Zielplattform .NET Framework 4.6.1 und früheren Versionen, die unter .NET Framework 4.6.2 oder höher ausgeführt werden, sind von dieser Änderung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="8023b-122">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="8023b-123">Minderung</span><span class="sxs-lookup"><span data-stu-id="8023b-123">Mitigation</span></span>  
 <span data-ttu-id="8023b-124">In Apps, die für .NET Framework 4.6.2 oder höher entwickelt wurden, kann diese Änderung deaktiviert und die Legacynormalisierung verwendet werden. Dazu muss dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei Folgendes hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="8023b-124">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>  
```  
  
<span data-ttu-id="8023b-125">In Apps, die auf .NET Framework 4.6.1 oder niedriger ausgerichtet sind, aber unter .NET Framework 4.6.2 oder höher ausgeführt werden, können die Änderungen an der Pfadnormalisierung aktiviert werden, indem dem Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) der Anwendungskonfigurationsdatei die folgende Zeile hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="8023b-125">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8023b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8023b-126">See also</span></span>

- [<span data-ttu-id="8023b-127">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="8023b-127">Application compatibility</span></span>](application-compatibility.md)
