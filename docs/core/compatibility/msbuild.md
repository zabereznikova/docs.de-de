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
# <a name="msbuild-breaking-changes"></a>Breaking Changes in MSBuild

Auf dieser Seite sind die folgenden Breaking Changes dokumentiert:

| Unterbrechende Änderung | Eingeführt in Version |
| - | - |
| [TargetFramework-Änderung von „netcoreapp“ in „net“](#targetframework-change-from-netcoreapp-to-net) | 5.0 |
| [Das NETCOREAPP3_1-Präprozessorsymbol ist nicht definiert, wenn .NET 5 als Ziel verwendet wird.](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | 5.0 |
| [Behavior Change von PublishDepsFilePath](#publishdepsfilepath-behavior-change) | 5.0 |
| [Directory.Packages.props-Dateien werden standardmäßig importiert.](#directorypackagesprops-files-is-imported-by-default) | 5.0 |
| [Änderung des Manifestdateinamens der Ressource](#resource-manifest-file-name-change) | 3.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [targetframework-name-change](../../../includes/core-changes/msbuild/5.0/targetframework-name-change.md)]

***

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
