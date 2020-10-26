---
title: Breaking Changes in MSBuild
description: Listet die Breaking Changes in MSBuild für .NET Core auf.
ms.date: 02/10/2020
ms.openlocfilehash: 9b0fba30c8955a6099bde0dc95b4df65a151d9e6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159486"
---
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="65e6e-103">Breaking Changes in MSBuild</span><span class="sxs-lookup"><span data-stu-id="65e6e-103">MSBuild breaking changes</span></span>

<span data-ttu-id="65e6e-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="65e6e-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="65e6e-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="65e6e-105">Breaking change</span></span> | <span data-ttu-id="65e6e-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="65e6e-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="65e6e-107">TargetFramework-Änderung von „netcoreapp“ in „net“</span><span class="sxs-lookup"><span data-stu-id="65e6e-107">TargetFramework change from netcoreapp to net</span></span>](#targetframework-change-from-netcoreapp-to-net) | <span data-ttu-id="65e6e-108">5.0</span><span class="sxs-lookup"><span data-stu-id="65e6e-108">5.0</span></span> |
| [<span data-ttu-id="65e6e-109">Das NETCOREAPP3_1-Präprozessorsymbol ist nicht definiert, wenn .NET 5 als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="65e6e-109">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | <span data-ttu-id="65e6e-110">5.0</span><span class="sxs-lookup"><span data-stu-id="65e6e-110">5.0</span></span> |
| [<span data-ttu-id="65e6e-111">Behavior Change von PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="65e6e-111">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="65e6e-112">5.0</span><span class="sxs-lookup"><span data-stu-id="65e6e-112">5.0</span></span> |
| [<span data-ttu-id="65e6e-113">Directory.Packages.props-Dateien werden standardmäßig importiert.</span><span class="sxs-lookup"><span data-stu-id="65e6e-113">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="65e6e-114">5.0</span><span class="sxs-lookup"><span data-stu-id="65e6e-114">5.0</span></span> |
| [<span data-ttu-id="65e6e-115">Änderung des Manifestdateinamens der Ressource</span><span class="sxs-lookup"><span data-stu-id="65e6e-115">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="65e6e-116">3.0</span><span class="sxs-lookup"><span data-stu-id="65e6e-116">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="65e6e-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="65e6e-117">.NET 5.0</span></span>

[!INCLUDE [targetframework-name-change](../../../includes/core-changes/msbuild/5.0/targetframework-name-change.md)]

***

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="65e6e-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="65e6e-118">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
