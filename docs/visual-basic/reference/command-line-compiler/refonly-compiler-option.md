---
title: -Ref only (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775563"
---
# <a name="-refonly-visual-basic"></a>-Ref only (Visual Basic)

Die Option **-rebonly** gibt an, dass die primäre Ausgabe der Kompilierung eine Verweisassembly anstelle einer Implementierungsassembly sein sollte. Der Parameter `-refonly` deaktiviert im Hintergrund die Ausgabe von PDBs, da Verweisassemblys nicht ausgeführt werden können.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Syntax

```console
-refonly
```

## <a name="remarks"></a>Hinweise

Visual Basic unterstützt den `-refonly` Switch ab Version 15,3.

Verweisassemblys sind eine besondere Art von Assembly, die nur die Mindestanzahl von Metadaten enthält, die zur Darstellung der öffentlichen API-Oberfläche der Bibliothek erforderlich sind. Sie enthalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools signifikant sind, aber alle Member-Implementierungen und-Deklarationen von privaten Membern ausschließen, die keine Observable-Auswirkung auf Ihren API-Vertrag haben. Weitere Informationen finden Sie im [Leitfaden zu Verweisassemblys in .net](../../../standard/assembly/reference-assemblies.md).

Die Optionen `-refonly` und [`-refout`](refout-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch

- [/refout](refout-compiler-option.md)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
