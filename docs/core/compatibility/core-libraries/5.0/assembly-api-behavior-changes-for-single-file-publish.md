---
title: 'Breaking Change: Assemblybezogene Behavior Changes für Veröffentlichungsformat mit einzelner Datei'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den mehrere auf den Speicherort der Assemblydatei bezogene APIs Behavior Changes aufweisen, wenn sie in einem Veröffentlichungsformat mit einzelner Datei aufgerufen werden.
ms.date: 11/01/2020
ms.openlocfilehash: d77e30318040c8298065073a41caab56f2ca3875
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759470"
---
# <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a><span data-ttu-id="2a157-103">Assemblybezogene Behavior Changes für Veröffentlichungsformat mit einzelner Datei</span><span class="sxs-lookup"><span data-stu-id="2a157-103">Assembly-related API behavior changes for single-file publishing format</span></span>

<span data-ttu-id="2a157-104">Mehrere auf den Speicherort der Assemblydatei bezogene APIs weisen Behavior Changes auf, wenn sie in einem Veröffentlichungsformat mit einzelner Datei aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2a157-104">Multiple APIs related to an assembly's file location have behavior changes when they're invoked in a single-file publishing format.</span></span>

## <a name="change-description"></a><span data-ttu-id="2a157-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="2a157-105">Change description</span></span>

<span data-ttu-id="2a157-106">Bei einer Veröffentlichung mit einzelner Datei für .NET 5.0 und höhere Versionen werden Assemblybundles aus dem Arbeitsspeicher geladen anstatt auf den Datenträger extrahiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="2a157-106">In single-file publishing for .NET 5.0 and later versions, bundled assemblies are loaded from memory instead of extracted to disk.</span></span> <span data-ttu-id="2a157-107">Für Apps, die als einzelne Datei veröffentlicht werden, bedeutet dies, dass bestimmte auf den Speicherort bezogene APIs verschiedene Werte für .NET 5.0 und höhere Versionen zurückgeben als ältere Versionen von .NET.</span><span class="sxs-lookup"><span data-stu-id="2a157-107">For single-file published apps, this means that certain location-related APIs return different values on .NET 5.0 and later than on previous versions of .NET.</span></span> <span data-ttu-id="2a157-108">Es gibt folgenden Änderungen:</span><span class="sxs-lookup"><span data-stu-id="2a157-108">The changes are as follows:</span></span>

| <span data-ttu-id="2a157-109">API</span><span class="sxs-lookup"><span data-stu-id="2a157-109">API</span></span> | <span data-ttu-id="2a157-110">Vorgängerversionen</span><span class="sxs-lookup"><span data-stu-id="2a157-110">Previous versions</span></span> | <span data-ttu-id="2a157-111">.NET 5.0 und höher</span><span class="sxs-lookup"><span data-stu-id="2a157-111">.NET 5.0 and later</span></span> |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | <span data-ttu-id="2a157-112">Gibt extrahierten DLL-Dateipfad zurück</span><span class="sxs-lookup"><span data-stu-id="2a157-112">Returns extracted DLL file path</span></span> | <span data-ttu-id="2a157-113">Gibt leere Zeichenfolge für Assemblybundles zurück</span><span class="sxs-lookup"><span data-stu-id="2a157-113">Returns empty string for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | <span data-ttu-id="2a157-114">Gibt extrahierten DLL-Dateipfad zurück</span><span class="sxs-lookup"><span data-stu-id="2a157-114">Returns extracted DLL file path</span></span> | <span data-ttu-id="2a157-115">Löst eine Ausnahme für Assemblybundles aus</span><span class="sxs-lookup"><span data-stu-id="2a157-115">Throws exception for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | <span data-ttu-id="2a157-116">Gibt `null` für Assemblybundles zurück</span><span class="sxs-lookup"><span data-stu-id="2a157-116">Returns `null` for bundled assemblies</span></span> | <span data-ttu-id="2a157-117">Löst eine Ausnahme für Assemblybundles aus</span><span class="sxs-lookup"><span data-stu-id="2a157-117">Throws exception for bundled assemblies</span></span> |
| `Environment.GetCommandLineArgs()[0]` | <span data-ttu-id="2a157-118">Der Wert ist der Name der Einstiegspunkt-DLL.</span><span class="sxs-lookup"><span data-stu-id="2a157-118">Value is the name of the entry point DLL</span></span> | <span data-ttu-id="2a157-119">Der Wert ist der Name der ausführbaren Hostdatei.</span><span class="sxs-lookup"><span data-stu-id="2a157-119">Value is the name of the host executable</span></span> |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | <span data-ttu-id="2a157-120">Der Wert ist das temporäre Extraktionsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2a157-120">Value is the temporary extraction directory</span></span> | <span data-ttu-id="2a157-121">Der Wert ist das Verzeichnis, das die ausführbare Hostdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="2a157-121">Value is the containing directory of the host executable</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="2a157-122">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="2a157-122">Version introduced</span></span>

<span data-ttu-id="2a157-123">5.0</span><span class="sxs-lookup"><span data-stu-id="2a157-123">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2a157-124">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="2a157-124">Recommended action</span></span>

<span data-ttu-id="2a157-125">Vermeiden Sie Abhängigkeiten vom Speicherort der Assemblydatei, wenn die Veröffentlichung als einzelne Datei erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2a157-125">Avoid dependencies on the file location of assemblies when publishing as a single file.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2a157-126">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2a157-126">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
