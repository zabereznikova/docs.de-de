---
title: -deterministic
ms.date: 04/11/2018
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
ms.openlocfilehash: 9b611a72656bdd570eccec8a0585bf5ce6fa55f6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716791"
---
# <a name="-deterministic"></a>-deterministic

Bewirkt, dass der Compiler eine Assembly erstellt, deren Byte-für-Byte-Ausgabe über Kompilierungen identisch ist, wenn die Eingaben identisch sind.

## <a name="syntax"></a>Syntax

```console
-deterministic
```

## <a name="remarks"></a>Hinweise

Standardmäßig ist die Compilerausgabe aus einem vorhandenen Satz von Eingaben eindeutig, da der Compiler einen Zeitstempel und eine GUID hinzufügt, die aus Zufallszahlen generiert wird. Verwenden Sie die `-deterministic`-Option zum Erzeugen einer *deterministischen Assembly*. Deren Inhalt im Binärformat muss über Kompilierungen identisch sein, solange die Eingabe identisch ist.

Der Compiler berücksichtigt die folgenden Eingaben für den Determinismus:

- Die Sequenz der Befehlszeilenparameter.
- Der Inhalt der rsp-Antwortdatei des Compilers.
- Die genaue Version des verwendeten Compilers und seiner verwiesenen Assemblys.
- Der aktuelle Verzeichnispfad.
- Die binären Inhalte aller Dateien, die explizit und entweder direkt oder indirekt an den Compiler übergeben werden, einschließlich:
  - Quelldateien
  - Assemblys, auf die verwiesen wird
  - Module, auf die verwiesen wird
  - Ressourcen
  - Die Schlüsseldatei mit starkem Namen
  - @ Antwortdateien
  - Analyzer
  - RuleSets
  - Zusätzliche Dateien, die möglicherweise von Analyzern verwendet werden
- Die aktuelle Kultur (für die Sprache, in der die Diagnose und die Ausnahmenachrichten erstellt werden).
- Die Standardcodierung (oder die aktuelle Codeseite), wenn die Codierung nicht angegeben ist.
- Das Vorhandensein, Nichtvorhandensein und die Inhalte der Dateien auf den Suchpfaden des Compilers (z.B. von `-lib` oder `-recurse` angegeben).
- Die CLR-Plattform, auf der der Compiler ausgeführt wird.
- Der Wert von `%LIBPATH%`, der das Abhängigkeitsladen des Analyzers beeinträchtigen kann.

Wenn Quellen öffentlich verfügbar sind, kann die deterministische Kompilierung verwendet werden, um festzustellen, ob eine Binärdatei aus einer vertrauenswürdigen Quelle kompiliert wird. Sie kann auch in einem fortlaufenden Buildsystem verwendet werden, um zu bestimmen, ob Buildschritte, die von den Änderungen einer Binärdatei abhängig sind, ausgeführt werden müssen.

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
