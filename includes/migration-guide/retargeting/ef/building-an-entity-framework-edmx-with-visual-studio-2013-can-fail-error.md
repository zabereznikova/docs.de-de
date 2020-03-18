---
ms.openlocfilehash: ffafb0c9e3982dd168f907d32a8f59f96e6040d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804607"
---
### <a name="building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>Beim Erstellen einer Entity Framework-EDMX-Datei mit Visual Studio 2013 kann der Fehler MSB4062 auftreten, wenn die Aufgabe „EntityDeploySplit“ oder „EntityClean“ verwendet wird

|   |   |
|---|---|
|Details|MSBuild 12.0-Tools (enthalten in Visual Studio 2013) haben die MSBuild-Dateispeicherorte geändert, wodurch ältere Entity Framework-Zieldateien ungültig geworden sind. Das führt dazu, dass <code>EntityDeploySplit</code>- und <code>EntityClean</code>-Aufgaben fehlschlagen, da sie <code>Microsoft.Data.Entity.Build.Tasks.dll</code> nicht finden können. Beachten Sie, dass dieses Problem aufgrund einer Änderung des Toolsets (MSBuild/VS) und nicht aufgrund einer Änderung an .NET Framework auftritt. Es tritt nur beim Upgrade von Entwicklertools und nicht beim Aktualisieren von .NET Framework auf.|
|Vorschlag|Die Entity Framework-Zieldateien wurden so korrigiert, dass sie mit dem neuen MSBuild-Layout genutzt werden können, das ab .NET Framework 4.6 verwendet wird. Ein Upgrade auf diese Version von .NET Framework wird dieses Problem beheben. Alternativ können Sie [diese Problemumgehung](https://stackoverflow.com/a/24249247/131944) verwenden, um die Zieldateien direkt zu patchen.|
|`Scope`|Major|
|Version|4.5.1|
|Geben Sie Folgendes ein:|Neuzuweisung|
