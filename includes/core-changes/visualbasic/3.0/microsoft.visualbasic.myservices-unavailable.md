---
ms.openlocfilehash: d207a937917da78f6b902ad8ca4f02fa9a46c2e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116369"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a><span data-ttu-id="ba667-101">Typen im Microsoft.VisualBasic.MyServices-Namespace nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="ba667-101">Types in Microsoft.VisualBasic.MyServices namespace not available</span></span>

<span data-ttu-id="ba667-102">Die Typen im <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>-Namespace sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ba667-102">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace are not available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ba667-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ba667-103">Version introduced</span></span>

<span data-ttu-id="ba667-104">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="ba667-104">.NET Core 3.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="ba667-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="ba667-105">Change description</span></span>

<span data-ttu-id="ba667-106">Die Typen im <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>-Namespace waren in einigen Releases von .NET Core 3.0 Preview verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ba667-106">The types in the <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName> namespace were available in some .NET Core 3.0 Preview releases.</span></span> <span data-ttu-id="ba667-107">Ab .NET Core 3.0 Preview 9 sind sie nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ba667-107">They are no longer available starting with .NET Core 3.0 Preview 9.</span></span>

<span data-ttu-id="ba667-108">Die Typen wurden entfernt, um unnötige Assemblyabhängigkeiten oder Breaking Changes in nachfolgenden Releases zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="ba667-108">The types were removed to avoid unnecessary assembly dependencies or breaking changes in subsequent releases.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ba667-109">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="ba667-109">Recommended action</span></span>

<span data-ttu-id="ba667-110">Wenn Sie für Ihren Code **Microsoft.VisualBasic.MyServices**-Typen und deren Member benötigen, finden Sie entsprechende Typen und Member in der .NET-Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ba667-110">If your code depends on the use of **Microsoft.VisualBasic.MyServices** types and their members, there are corresponding types and members in the .NET class library.</span></span> <span data-ttu-id="ba667-111">Im Folgenden ist eine Zuordnung von **Microsoft.VisualBasic.MyServices**-Typen zu den entsprechenden .NET-Klassenbibliothekstypen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="ba667-111">The following is a mapping of  **Microsoft.VisualBasic.MyServices** types to their equivalent .NET class library types:</span></span>

|<span data-ttu-id="ba667-112">Microsoft.VisualBasic.MyServices-Typ</span><span class="sxs-lookup"><span data-stu-id="ba667-112">Microsoft.VisualBasic.MyServices type</span></span>|<span data-ttu-id="ba667-113">.NET-Klassenbibliothekstyp</span><span class="sxs-lookup"><span data-stu-id="ba667-113">.NET class library type</span></span>|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<span data-ttu-id="ba667-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> für WPF-Anwendungen, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> für Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ba667-114"><xref:System.Windows.Clipboard?displayProperty=nameWithType> for WPF applications, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> for Windows Forms applications</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|<span data-ttu-id="ba667-115">Typen im <xref:System.IO>-Namespace</span><span class="sxs-lookup"><span data-stu-id="ba667-115">Types in the <xref:System.IO> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|<span data-ttu-id="ba667-116">Registrierungsbezogene Typen im <xref:Microsoft.Win32>-Namespace</span><span class="sxs-lookup"><span data-stu-id="ba667-116">Registry-related types in the <xref:Microsoft.Win32> namespace</span></span>|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a><span data-ttu-id="ba667-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ba667-117">Category</span></span>

<span data-ttu-id="ba667-118">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba667-118">Visual Basic</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ba667-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ba667-119">Affected APIs</span></span>

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-->
