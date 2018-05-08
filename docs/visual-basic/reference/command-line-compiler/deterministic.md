---
title: -deterministisch
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffb1d27f614afc3b07f9d663831fc2071535236f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-deterministic"></a>-deterministisch

Bewirkt, dass der Compiler eine Assembly zu erzeugen, deren Ausgabe Byte für Byte über Kompilierungen für identische Eingaben identisch ist. 

## <a name="syntax"></a>Syntax

```
-deterministic
```

## <a name="remarks"></a>Hinweise

Standardmäßig ist Compilerausgabe aus einem vorhandenen Satz von Eingaben eindeutig, da der Compiler Fügt einen Zeitstempel und eine GUID, die Zufallszahlen generiert wird. Verwenden Sie die `-deterministic` Option zum Erzeugen einer *deterministisch Assembly*, ein, deren Inhalt im Binärformat über Kompilierungen identisch ist, solange die Eingabe identisch ist.

Der Compiler berücksichtigt die folgenden Eingaben zum Determinismus:

- Die Reihenfolge der Befehlszeilenparameter.
- Der Inhalt des Compilers rsp-Antwortdatei.
- Die genaue Version des verwendeten Compilers und Assemblys, auf die verwiesen wird.
- Der aktuelle Verzeichnispfad.
- Der binäre Inhalt aller Dateien explizit an den Compiler übergeben entweder direkt oder indirekt, einschließlich: 
    - Quelldateien
    - Assemblys verwiesen wird
    - Module verwiesen wird
    - Ressourcen
    - Die Schlüsseldatei mit starkem Namen
    - @ Antwortdateien
    - Analyzer
    - Regelsätze
    - Zusätzliche Dateien, die möglicherweise vom Analyzer verwendet werden
- Die aktuelle Kultur (für die Sprache, in der Diagnose, die und die Ausnahme Nachrichten erstellt werden).
- Die standardcodierung (oder der aktuellen Codepage) Wenn die Codierung nicht angegeben ist.
- Das Vorhandensein, Nichtvorhandensein und Inhalt der Dateien auf den Compiler Suchpfade (angegeben, z. B. durch `/lib` oder `/recurse`).
- Die CLR-Plattform, auf der der Compiler ausgeführt wird.
- Der Wert des `%LIBPATH%`, kann der Analyzer Abhängigkeit laden beeinträchtigen.

Wenn Quellen öffentlich verfügbar sind, kann deterministisch Kompilierung verwendet werden, zur Feststellung, ob eine Binärdatei aus einer vertrauenswürdigen Quelle kompiliert wird. Sie können auch nützlich sein in einem fortlaufenden Buildsystem zu bestimmen, ob Buildschritte, die abhängig von den Änderungen in einen binären sind ausgeführt werden müssen. 

## <a name="see-also"></a>Siehe auch
[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
[Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
