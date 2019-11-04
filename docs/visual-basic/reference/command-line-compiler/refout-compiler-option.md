---
title: -reout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 552e611f222bfcc3ce12520ecdb891fd7b8b21de
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775551"
---
# <a name="-refout-visual-basic"></a>-reout (Visual Basic)

Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Syntax

```console
-refout:filepath
```

## <a name="arguments"></a>Argumente

`filepath`  
Der Pfad und der Dateiname der Verweisassembly. Er sollte sich in der Regel in einem Unterordner der primären Assembly befinden. Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist. Alle Ordner in `filepath` müssen vorhanden sein. der Compiler erstellt diese nicht.

## <a name="remarks"></a>Hinweise

Visual Basic unterstützt den `-refout` Switch ab Version 15,3.

Verweisassemblys sind eine besondere Art von Assembly, die nur die Mindestanzahl von Metadaten enthält, die zur Darstellung der öffentlichen API-Oberfläche der Bibliothek erforderlich sind. Sie enthalten Deklarationen für alle Member, die beim Verweis auf eine Assembly in Buildtools signifikant sind, aber alle Member-Implementierungen und-Deklarationen von privaten Membern ausschließen, die keine Observable-Auswirkung auf Ihren API-Vertrag haben. Weitere Informationen finden Sie im [Leitfaden zu Verweisassemblys in .net](../../../standard/assembly/reference-assemblies.md).

Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch

- [/refonly](refonly-compiler-option.md)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
