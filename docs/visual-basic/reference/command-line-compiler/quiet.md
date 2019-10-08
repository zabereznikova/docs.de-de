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
ms.translationtype: MT
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

In der Standardeinstellung ist `-quiet` nicht aktiv. Wenn der Compiler einen Syntax bezogenen Fehler oder eine Warnung meldet, gibt er auch die Zeile aus dem Quellcode aus. Bei Anwendungen, die die Compilerausgabe analysieren, ist es möglicherweise bequemer, dass der Compiler nur den Text der Diagnose ausgibt.

Im folgenden Beispiel gibt `Module1` einen Fehler aus, der Quellcode enthält, wenn er ohne `-quiet` kompiliert wird.

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

Kompiliert mit `-quiet`: der Compiler gibt nur Folgendes aus:

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> Die Option "`-quiet`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Mit dem folgenden Code wird `T2.vb` kompiliert, und es wird kein Code für die Syntax bezogene Compilerdiagnose angezeigt:

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
