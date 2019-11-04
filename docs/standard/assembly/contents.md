---
title: Assemblyinhalte
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- assemblies [.NET Core]
- single-file assemblies
- multifile assemblies [.NET Framework]
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: 9ca12ee4bd993db3dd200a3b340c220ce5188796
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122538"
---
# <a name="assembly-contents"></a>Assemblyinhalte
Im Allgemeinen kann eine statische Assembly vier Elemente enthalten:

- Das [Assemblymanifest](manifest.md), das die Assemblymetadaten enthält.

- Die Typmetadaten.  

- MSIL-Code (Microsoft Intermediate Language), der die Typen implementiert. Er wird vom Compiler aus mindestens einer Quellcodedatei generiert.

- Eine Gruppe von Ressourcen.  

Von diesen ist nur das Assemblymanifest erforderlich. Um der Assembly jedoch eine sinnvolle Funktion zu geben, sind entweder Typen oder Ressourcen erforderlich.

Die folgende Abbildung zeigt, wie diese Elemente in einer einzelnen physischen Datei gruppiert sind.

![Diagramm einer Einzeldateiassembly namens „MyAssembly.dll“](./media/contents/single-file-assembly.gif)

In dieser Abbildung gehören alle drei Dateien zu einer Assembly, wie im Assemblymanifest in MyAssembly.dll beschrieben. Das Dateisystem betrachtet diese als drei getrennte Dateien. Beachten Sie, dass die Datei "Util.netmodule" als Modul kompiliert wurde, da sie keine Assemblyinformationen enthält. Beim Erstellen der Assembly wurde das Assemblymanifest "MyAssembly.dll" hinzugefügt, um die Beziehungen zwischen den Dateien "Util.netmodule" und "Graphic.bmp" anzuzeigen.

Wenn Sie gegenwärtig Quellcode schreiben, treffen Sie explizite Entscheidungen darüber, wie die Funktionen einer Anwendung in eine oder mehrere Dateien aufgeteilt werden. Beim Entwerfen von .NET Framework-Code werden Sie in Zukunft ähnliche Entscheidungen darüber treffen, wie Sie Funktionen in eine oder mehrere Assemblys aufteilen.

## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](index.md)
- [Assemblymanifest](manifest.md)
- [Überlegungen zur Assemblysicherheit](security-considerations.md)
