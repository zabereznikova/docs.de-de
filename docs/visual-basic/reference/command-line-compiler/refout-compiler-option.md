---
title: -reout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582870"
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

Verweisassemblys sind reine Metadatenassemblys, die Metadaten, aber keinen Implementierungs Code enthalten. Sie enthalten Informationen über den Typ und den Member für alles außer anonyme Typen. Ihre Methoden Texte werden durch eine einzelne `throw null`-Anweisung ersetzt. Der Grund für die Verwendung `throw null` Methoden Texts (im Gegensatz zu keinem Text) ist, dass "Peer verify" ausgeführt und bestanden werden kann (wodurch die Vollständigkeit der Metadaten überprüft wird).

Verweisassemblys enthalten ein [referenceassembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) -Attribut auf Assemblyebene. Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen). Aufgrund dieses Attributs verweigern Laufzeiten das Laden von Verweisassemblys für die Ausführung (Sie können jedoch dennoch in einen reflektionsbasierten Kontext geladen werden). Tools, die Assemblys reflektieren, müssen sicherstellen, dass Sie Verweisassemblys als Reflektion laden. Andernfalls löst die Laufzeit eine <xref:System.BadImageFormatException> aus.

Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch

- [/refonly](refonly-compiler-option.md)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
