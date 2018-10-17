---
title: Bibliotheken SourceLink und .NET
description: Empfehlungen für bewährte Methoden mit, dass die SourceLink verbessertes debugging für .NET-Bibliotheken.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49370045"
---
# <a name="sourcelink"></a>SourceLink

SourceLink ist eine Technologie, die es ermöglicht, Debuggen von Quellcode von .NET-Assemblys aus NuGet von Entwicklern. SourceLink ausgeführt wird, wenn das NuGet-Paket zu erstellen und Datenquellen-Steuerelement-Metadaten in Assemblys und das Paket eingebettet. Entwickler, die das Paket herunterladen und SourceLink in Visual Studio aktiviert haben, können deren Quellcode schrittweise. SourceLink enthält Datenquellen-Steuerelement-Metadaten um eine gute Debugleistung zu erstellen.

## <a name="sourcelink-demo"></a>SourceLink-demo

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a>Verwenden die SourceLink

Anweisungen zur Verwendung von SourceLink finden Sie auf die [Dotnet/SourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub-Repository.

Sie können [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) zu bestätigen, dass die SourceLink-Metadaten in das Paket erfolgreich eingebettet wurde. Überprüfen Sie die `Repository` Metadaten mit einem Kommentar Bezeichner vorhanden ist und dass PDB-Dateien sich auf die DLL-Datei des Ziels.

![SourceLink im NuGet-Paket-Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink im NuGet-Paket-Explorer")

**✔️ GGF.** mit SourceLink Quell-Steuerelement-Metadaten für Ihre Assemblys und NuGet-Paket hinzu.

**✔️ GGF.** PDB-Dateien in das NuGet-Paket einschließen.

>[!div class="step-by-step"]
[Zurück](./dependencies.md)
[Weiter](./publish-nuget-package.md)
