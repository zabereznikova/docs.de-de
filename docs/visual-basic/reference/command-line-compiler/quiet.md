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
ms.openlocfilehash: 6e773c60469e8426956c92a5aa377741ba5af4d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005281"
---
# <a name="-quiet"></a>-quiet

Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.

## <a name="syntax"></a>Syntax

```console
-quiet
```

## <a name="remarks"></a>Hinweise

In der Standardeinstellung ist `-quiet` nicht aktiv. Wenn der Compiler einen syntaxbedingten Fehler oder eine entsprechende Warnung meldet, wird auch die Zeile aus dem Quellcode ausgegeben. Bei Anwendungen, die Compilerausgabe analysieren, ist es möglicherweise einfacher, wenn der Compiler nur den Text der Diagnose ausgibt.

Im folgenden Beispiel gibt `Module1` einen Fehler aus, der Quellcode einschließt, wenn ohne `-quiet` kompiliert wird.

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

Wenn mit `-quiet` kompiliert wird, gibt der Compiler Folgendes aus:

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> Diese Option `-quiet` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Der folgende Code kompiliert `T2.vb` und zeigt Code nicht für syntaxbedingte Compilerdiagnosen an:

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
