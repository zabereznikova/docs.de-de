---
title: Assemblyinhalte
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework]
- assemblies [.NET Core]
- single-file assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
ms.openlocfilehash: bee9d5422ec3101b2486f233ae0816ae3643f4e7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75345573"
---
# <a name="assembly-contents"></a>Assemblyinhalte

Im Allgemeinen kann eine statische Assembly vier Elemente enthalten:

- Das [Assemblymanifest](manifest.md), das die Assemblymetadaten enthält.

- Die Typmetadaten.  

- MSIL-Code (Microsoft Intermediate Language), der die Typen implementiert. Er wird vom Compiler aus mindestens einer Quellcodedatei generiert.

- Eine Gruppe von [Ressourcen](../../framework/resources/index.md).  

Von diesen ist nur das Assemblymanifest erforderlich. Um der Assembly jedoch eine sinnvolle Funktion zu geben, sind entweder Typen oder Ressourcen erforderlich.

Die folgende Abbildung zeigt, wie diese Elemente in einer einzelnen physischen Datei gruppiert werden:

![Eine Einzeldateiassembly namens „MyAssembly.dll“](./media/contents/single-file-assembly.gif)

Wenn Sie Quellcode schreiben, treffen Sie explizite Entscheidungen darüber, wie die Funktionen einer Anwendung auf eine oder mehrere Dateien aufgeteilt werden. Beim Entwerfen von .NET-Code treffen Sie ähnliche Entscheidungen darüber, wie Sie Funktionen auf eine oder mehrere Assemblys aufteilen.

## <a name="see-also"></a>Weitere Informationen

- [Assemblys in .NET](index.md)
- [Assemblymanifest](manifest.md)
- [Überlegungen zur Assemblysicherheit](security-considerations.md)
