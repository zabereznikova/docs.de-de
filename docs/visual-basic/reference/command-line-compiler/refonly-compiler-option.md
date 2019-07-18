---
title: -Refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 4093e98738cf6e41cd450229d82e3672fe9687ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788868"
---
# <a name="-refonly-visual-basic"></a>-Refonly (Visual Basic)

Die **- Refonly** Option gibt an, dass die primäre Ausgabe von der Kompilierung eine Verweisassembly statt einer implementierungsassembly werden soll. Der Parameter `-refonly` deaktiviert im Hintergrund die Ausgabe von PDBs, da Verweisassemblys nicht ausgeführt werden können.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Syntax

```console
-refonly
```

## <a name="remarks"></a>Hinweise

Visual Basic unterstützt die `-refout` ab Version 15.3 zu wechseln.

Verweisassemblys werden Metadaten beschränkten Assemblys, die Metadaten, aber keinen Code zur Implementierung enthalten. Sie enthalten Informationen von Typ- und Memberinformationen für alles außer anonymen Typen. Der Grund für die Verwendung von `throw null`-Texten (im Gegensatz zu keinen Texten) ist, dass PEVerify erfolgreich ausgeführt werden kann (und so wird die Vollständigkeit der Metadaten überprüft).

Verweisassemblys enthalten ein auf Assemblyebene [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) Attribut. Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen). Durch dieses Attribut wird Laufzeiten verweigert die Anforderung zum Laden der Verweisassemblys für die Ausführung (aber sie können immer noch in einem reflektionsbezogenen Kontext geladen werden). Tools, die Assemblys reflektieren müssen, um sicherzustellen, dass sie die Verweisassemblys nur geladen; Andernfalls löst die Laufzeit eine <xref:System.BadImageFormatException>.

Die Optionen `-refonly` und [`-refout`](refout-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch

- [/refout](refout-compiler-option.md)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
