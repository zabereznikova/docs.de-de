---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: a22773e2e37eb60ab6f1e88305266f41764311e7
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612588"
---
# <a name="-quiet"></a>-quiet

Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.

## <a name="syntax"></a>Syntax

```
-quiet
```

## <a name="remarks"></a>Hinweise

In der Standardeinstellung ist `-quiet` nicht aktiv. Wenn der Compiler ein syntaxbezogene Fehler oder eine Warnung gemeldet, auch die Zeile aus dem Quellcode ausgegeben. Für Anwendungen, die Compiler-Ausgabe zu analysieren, kann es einfacher für den Compiler an, nur den Text der Diagnose ausgegeben sein.

Im folgenden Beispiel `Module1` gibt einen Fehler aus, die bei der Kompilierung ohne Quellcode enthält `-quiet`.

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

Ausgabe:

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

Mit kompiliert `-quiet`, der Compiler gibt nur die folgenden:

```
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> Die `-quiet` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Der folgende code kompiliert `T2.vb` und Code für syntaxbezogene Compilerdiagnose nicht angezeigt:

```
vbc -quiet t2.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
