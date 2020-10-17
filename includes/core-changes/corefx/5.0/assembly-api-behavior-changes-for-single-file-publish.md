---
ms.openlocfilehash: 0d6847b7a937094f36efae70ae450cc37824221d
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955555"
---
### <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a><span data-ttu-id="1c13f-101">Assemblybezogene Behavior Changes für Veröffentlichungsformat mit einzelner Datei</span><span class="sxs-lookup"><span data-stu-id="1c13f-101">Assembly-related API behavior changes for single-file publishing format</span></span>

<span data-ttu-id="1c13f-102">Mehrere auf den Speicherort der Assemblydatei bezogene APIs weisen Behavior Changes auf, wenn sie in einem Veröffentlichungsformat mit einzelner Datei aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1c13f-102">Multiple APIs related to an assembly's file location have behavior changes when they're invoked in a single-file publishing format.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1c13f-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="1c13f-103">Change description</span></span>

<span data-ttu-id="1c13f-104">Bei einer Veröffentlichung mit einzelner Datei für .NET 5.0 und höhere Versionen werden Assemblybundles aus dem Arbeitsspeicher geladen anstatt auf den Datenträger extrahiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="1c13f-104">In single-file publishing for .NET 5.0 and later versions, bundled assemblies are loaded from memory instead of extracted to disk.</span></span> <span data-ttu-id="1c13f-105">Für Apps, die als einzelne Datei veröffentlicht werden, bedeutet dies, dass bestimmte auf den Speicherort bezogene APIs verschiedene Werte für .NET 5.0 und höhere Versionen zurückgeben als ältere Versionen von .NET.</span><span class="sxs-lookup"><span data-stu-id="1c13f-105">For single-file published apps, this means that certain location-related APIs return different values on .NET 5.0 and later than on previous versions of .NET.</span></span> <span data-ttu-id="1c13f-106">Es gibt folgenden Änderungen:</span><span class="sxs-lookup"><span data-stu-id="1c13f-106">The changes are as follows:</span></span>

| <span data-ttu-id="1c13f-107">API</span><span class="sxs-lookup"><span data-stu-id="1c13f-107">API</span></span> | <span data-ttu-id="1c13f-108">Vorgängerversionen</span><span class="sxs-lookup"><span data-stu-id="1c13f-108">Previous versions</span></span> | <span data-ttu-id="1c13f-109">.NET 5.0 und höher</span><span class="sxs-lookup"><span data-stu-id="1c13f-109">.NET 5.0 and later</span></span> |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | <span data-ttu-id="1c13f-110">Gibt extrahierten DLL-Dateipfad zurück</span><span class="sxs-lookup"><span data-stu-id="1c13f-110">Returns extracted DLL file path</span></span> | <span data-ttu-id="1c13f-111">Gibt leere Zeichenfolge für Assemblybundles zurück</span><span class="sxs-lookup"><span data-stu-id="1c13f-111">Returns empty string for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | <span data-ttu-id="1c13f-112">Gibt extrahierten DLL-Dateipfad zurück</span><span class="sxs-lookup"><span data-stu-id="1c13f-112">Returns extracted DLL file path</span></span> | <span data-ttu-id="1c13f-113">Löst eine Ausnahme für Assemblybundles aus</span><span class="sxs-lookup"><span data-stu-id="1c13f-113">Throws exception for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | <span data-ttu-id="1c13f-114">Gibt `null` für Assemblybundles zurück</span><span class="sxs-lookup"><span data-stu-id="1c13f-114">Returns `null` for bundled assemblies</span></span> | <span data-ttu-id="1c13f-115">Löst eine Ausnahme für Assemblybundles aus</span><span class="sxs-lookup"><span data-stu-id="1c13f-115">Throws exception for bundled assemblies</span></span> |
| `Environment.GetCommandLineArgs()[0]` | <span data-ttu-id="1c13f-116">Der Wert ist der Name der Einstiegspunkt-DLL.</span><span class="sxs-lookup"><span data-stu-id="1c13f-116">Value is the name of the entry point DLL</span></span> | <span data-ttu-id="1c13f-117">Der Wert ist der Name der ausführbaren Hostdatei.</span><span class="sxs-lookup"><span data-stu-id="1c13f-117">Value is the name of the host executable</span></span> |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | <span data-ttu-id="1c13f-118">Der Wert ist das temporäre Extraktionsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1c13f-118">Value is the temporary extraction directory</span></span> | <span data-ttu-id="1c13f-119">Der Wert ist das Verzeichnis, das die ausführbare Hostdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="1c13f-119">Value is the containing directory of the host executable</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="1c13f-120">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="1c13f-120">Version introduced</span></span>

<span data-ttu-id="1c13f-121">5.0</span><span class="sxs-lookup"><span data-stu-id="1c13f-121">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1c13f-122">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="1c13f-122">Recommended action</span></span>

<span data-ttu-id="1c13f-123">Vermeiden Sie Abhängigkeiten vom Speicherort der Assemblydatei, wenn die Veröffentlichung als einzelne Datei erfolgt.</span><span class="sxs-lookup"><span data-stu-id="1c13f-123">Avoid dependencies on the file location of assemblies when publishing as a single file.</span></span>

#### <a name="category"></a><span data-ttu-id="1c13f-124">Kategorie</span><span class="sxs-lookup"><span data-stu-id="1c13f-124">Category</span></span>

- <span data-ttu-id="1c13f-125">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="1c13f-125">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1c13f-126">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1c13f-126">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
