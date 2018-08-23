---
title: -Refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21cea76f31bdf2ac5fcf434ee759f874f917617b
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754052"
---
# <a name="-refout-visual-basic"></a>-Refout (Visual Basic)

Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Syntax

```console
-refout:filepath
```

## <a name="arguments"></a>Argumente

 `filepath` Der Pfad und Dateiname der Verweisassembly. Es sollte in der Regel in einem Unterordner der primären Assembly sein. Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist. Alle Ordner im `filepath` muss vorhanden sein; der Compiler nicht erstellen. 

## <a name="remarks"></a>Hinweise

Visual Basic unterstützt die `-refout` ab Version 15.3 zu wechseln.

Verweisassemblys werden Metadaten beschränkten Assemblys, die Metadaten, aber keinen Code zur Implementierung enthalten. Sie enthalten Informationen von Typ- und Memberinformationen für alles außer anonymen Typen. Ihre Methodentext ersetzt werden, mit einem einzelnen `throw null` Anweisung. Der Grund für die Verwendung von `throw null` Methodentexten (im Gegensatz zu keinen Texten) ist, damit PEVerify ausführen kann, und übergeben (daher wird die Vollständigkeit der Metadaten überprüft).

Verweisassemblys enthalten ein auf Assemblyebene [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) Attribut. Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen). Durch dieses Attribut wird Laufzeiten verweigern, beim Laden der Verweisassemblys für die Ausführung (aber immer noch können Sie in einem reflektionsbezogenen Kontext geladen werden). Tools, die Assemblys reflektieren müssen, um sicherzustellen, dass sie die Verweisassemblys nur geladen; Andernfalls löst die Laufzeit eine <xref:System.BadImageFormatException>.

Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch
[-refonly](refonly-compiler-option.md)   
[Visual Basic-Befehlszeilencompiler](index.md)  
[Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)  

