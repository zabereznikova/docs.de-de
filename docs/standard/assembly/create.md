---
title: Erstellen von Assemblys
description: Erfahren Sie, wie Sie Einfach- oder Mehrfachdateiassemblys mit einer IDE wie Visual Studio oder mit den vom Windows SDK bereitgestellten Compilern und Tools entwickeln.
ms.date: 08/19/2019
helpviewer_keywords:
- assemblies [.NET], multifile
- single-file assemblies
- assemblies [.NET], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
ms.openlocfilehash: e1b08e40ae3b4c377cec52cb1ebf6db643af6429
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160580"
---
# <a name="create-assemblies"></a>Erstellen von Assemblys

Sie können Einfach- oder Mehrfachdateiassemblys mit einer IDE wie Visual Studio oder mit den vom Windows SDK bereitgestellten Compilern und Tools entwickeln. Die einfachste Assembly ist eine einzelne Datei mit einem einfachen Namen. Diese wird in eine einzige Anwendungsdomäne geladen. Auf diese Assembly kann nicht von anderen Assemblys außerhalb des Anwendungsverzeichnisses verwiesen werden. Außerdem wird sie keiner Versionsüberprüfung unterzogen. Um die Anwendung, die aus der Assembly besteht, zu deinstallieren, müssen Sie nur das Verzeichnis löschen, in dem sie sich befindet. Viele Entwickler benötigen nur eine Assembly mit diesen Funktionen, um eine Anwendung bereitzustellen.

Sie können eine Mehrfachdateiassembly aus mehreren Codemodulen und Ressourcendateien erstellen. Außerdem können Sie eine Assembly erstellen, die von mehrere Anwendungen verwendet werden kann. Eine freigegebene Assembly muss einen starken Namen haben. Sie kann im globalen Assemblycache bereitgestellt werden.

Beim Gruppieren von Codemodulen und Ressourcen in Assemblys stehen Ihnen mehrere Optionen zur Verfügung. Diese hängen von folgenden Faktoren ab:

- Versionskontrolle

     Gruppieren von Modulen, die die gleichen Versionsinformationen haben sollten

- Bereitstellung

     Gruppieren von Modulen und Ressourcen, die Ihr Bereitstellungsmodell unterstützen

- Wiederverwendung

     Gruppieren von Modulen, wenn diese logisch für bestimmte Zwecke zusammen verwendet werden können. Beispielsweise eine Assembly, die aus Typen und Klassen besteht, die unregelmäßig zur Wartung eines Programms verwendet werden, kann in die gleiche Assembly platziert werden. Zusätzlich sollten Typen, die Sie für mehrere Anwendungen freigeben möchten, in einer Assembly gruppiert sein. Diese Assembly sollte mit einem starken Namen signiert werden.

- Sicherheit

     Gruppieren von Modulen, die Typen enthalten, die die gleichen Sicherheitsberechtigungen erfordern

- Bewerten

     Gruppieren von Modulen, die Typen enthalten, deren Sichtbarkeit auf die gleiche Assembly eingeschränkt sein soll

Wenn Sie Assemblys der Common Language Runtime für nicht verwaltete COM-Anwendungen verfügbar machen, müssen Sie auf Besonderheiten achten. Weitere Informationen zum Arbeiten mit nicht verwaltetem Code finden Sie unter [Verfügbarmachen von .NET Framework-Komponenten in COM](../../framework/interop/exposing-dotnet-components-to-com.md).

## <a name="see-also"></a>Siehe auch

- [Assemblyversionsverwaltung](versioning.md)
- [How to: Erstellen einer Einzeldateiassembly](../../framework/app-domains/build-single-file-assembly.md)
- [How to: Erstellen einer Mehrfachdateiassembly](../../framework/app-domains/build-multifile-assembly.md)
- [So sucht Common Language Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [Mehrfachdateiassemblys](../../framework/app-domains/multifile-assemblies.md)
