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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653532"
---
# <a name="-refout-visual-basic"></a>-Refout (Visual Basic)

Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll.

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a>Syntax

```console
-refout:filepath
```

## <a name="arguments"></a>Argumente

 `filepath` Der Pfad und Dateiname der Verweisassembly. Dies sollte in der Regel in einem projektspezifischen Unterordner der primären Assembly sein. Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist. Alle Ordner in `filepath` muss vorhanden sein; der Compiler nicht erstellt. 

## <a name="remarks"></a>Hinweise

Visual Basic unterstützt die `-refout` ab Version 15.3 wechseln.

Verweisassemblys sind reine Assemblys, die Metadaten, aber keinen Implementierungscode enthalten. Typ- und Memberdaten Angaben für alles mit Ausnahme von anonymen Typen enthalten. Ihre Methodentexte werden mit einem einzelnen ersetzt `throw null` Anweisung. Der Grund für die Verwendung von `throw null` Methodentexte (im Gegensatz zu keine Nachrichtentexte) ist, damit PEVerify übergeben (Überprüfen daher die Vollständigkeit der Metadaten) und ausführen kann.

Verweisassemblys enthalten eine Assemblyebene [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) Attribut. Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen). Aufgrund dieses Attribut Laufzeiten verweigern Verweisassemblys für Ausführung geladen (aber dennoch können Sie in einem reflektionsbezogenen Kontext geladen werden). Tools, mit die Assemblys entsprechen müssen sicherstellen, dass sie Verweisassemblys als reflektionsbezogenen geladen; Andernfalls löst die Laufzeit eine <xref:System.BadImageFormatException>.

Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch
[-refonly](refonly-compiler-option.md)   
[Visual Basic-Befehlszeilencompiler](index.md)  
[Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)  

