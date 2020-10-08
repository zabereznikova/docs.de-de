---
title: Breaking Changes in MSBuild
description: Listet die Breaking Changes in MSBuild für .NET Core auf.
ms.date: 02/10/2020
ms.openlocfilehash: b57c70d21e061c59f26b11a025d4d05ce3b8ca99
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654735"
---
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="40005-103">Breaking Changes in MSBuild</span><span class="sxs-lookup"><span data-stu-id="40005-103">MSBuild breaking changes</span></span>

<span data-ttu-id="40005-104">Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:</span><span class="sxs-lookup"><span data-stu-id="40005-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="40005-105">Unterbrechende Änderung</span><span class="sxs-lookup"><span data-stu-id="40005-105">Breaking change</span></span> | <span data-ttu-id="40005-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="40005-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="40005-107">Das NETCOREAPP3_1-Präprozessorsymbol ist nicht definiert, wenn .NET 5 als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="40005-107">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | <span data-ttu-id="40005-108">5.0</span><span class="sxs-lookup"><span data-stu-id="40005-108">5.0</span></span> |
| [<span data-ttu-id="40005-109">Behavior Change von PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="40005-109">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="40005-110">5.0</span><span class="sxs-lookup"><span data-stu-id="40005-110">5.0</span></span> |
| [<span data-ttu-id="40005-111">Directory.Packages.props-Dateien werden standardmäßig importiert.</span><span class="sxs-lookup"><span data-stu-id="40005-111">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="40005-112">5.0</span><span class="sxs-lookup"><span data-stu-id="40005-112">5.0</span></span> |
| [<span data-ttu-id="40005-113">Änderung des Manifestdateinamens der Ressource</span><span class="sxs-lookup"><span data-stu-id="40005-113">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="40005-114">3.0</span><span class="sxs-lookup"><span data-stu-id="40005-114">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="40005-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="40005-115">.NET 5.0</span></span>

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="40005-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="40005-116">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
