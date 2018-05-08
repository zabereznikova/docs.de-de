---
title: -Refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8f6c15084ac9b1a07aef8a0311edfcc4a93337c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-refonly-visual-basic"></a>-Refonly (Visual Basic)

Die **- Refonly** Option gibt an, dass die primäre Ausgabe von der Kompilierung anstelle einer Implementierung Assembly eine Verweisassembly werden soll. Der Parameter `-refonly` deaktiviert im Hintergrund die Ausgabe von PDBs, da Verweisassemblys nicht ausgeführt werden können.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Syntax

```console
-refonly
```

## <a name="remarks"></a>Hinweise

Visual Basic unterstützt die `-refout` ab Version 15.3 wechseln.

Verweisassemblys sind reine Assemblys, die Metadaten, aber keinen Implementierungscode enthalten. Typ- und Memberdaten Angaben für alles mit Ausnahme von anonymen Typen enthalten. Der Grund für die Verwendung von `throw null`-Texten (im Gegensatz zu keinen Texten) ist, dass PEVerify erfolgreich ausgeführt werden kann (und so wird die Vollständigkeit der Metadaten überprüft).

Verweisassemblys enthalten eine Assemblyebene [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) Attribut. Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen). Aufgrund dieses Attribut Laufzeiten lehnt Verweisassemblys für Ausführung geladen (aber dennoch können Sie in einem reflektionsbezogenen Kontext geladen werden). Tools, mit die Assemblys entsprechen müssen sicherstellen, dass sie Verweisassemblys als reflektionsbezogenen geladen; Andernfalls löst die Laufzeit eine <xref:System.BadImageFormatException>.

Die Optionen `-refonly` und [`-refout`](refout-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch
[-refout](refout-compiler-option.md)   
[Visual Basic-Befehlszeilencompiler](index.md)  
[Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)   
