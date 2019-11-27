---
title: '@ (Antwortdatei festlegen)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: c578495bbba0efee79f02da284c7feffb8c12fab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348550"
---
# <a name="-specify-response-file-visual-basic"></a>@ (Antwortdatei festlegen) (Visual Basic)

Gibt eine Datei an, die Compileroptionen und Quell Code Dateien enthält, die kompiliert werden sollen.

## <a name="syntax"></a>Syntax

```console
@response_file
```

## <a name="arguments"></a>Argumente

`response_file`  
Erforderlich Eine Datei, die Compileroptionen oder Quell Code Dateien auflistet, die kompiliert werden sollen. Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.

## <a name="remarks"></a>Hinweise

Der Compiler verarbeitet die Compileroptionen und Quell Code Dateien, die in einer Antwortdatei angegeben sind, so, als wären Sie in der Befehlszeile angegeben worden.

Wenn Sie mehr als eine Antwortdatei in einer Kompilierung angeben möchten, geben Sie mehrere Optionen für die Antwortdatei an, wie z. b. die folgenden.

```console
@file1.rsp @file2.rsp
```

In einer Antwortdatei können mehrere Compileroptionen und Quell Code Dateien in einer Zeile angezeigt werden. Eine einzelne compileroptionsspezifikation muss in einer Zeile angezeigt werden (darf sich nicht über mehrere Zeilen erstrecken). Antwort Dateien können Kommentare enthalten, die mit dem `#` Symbol beginnen.

Sie können die in der Befehlszeile angegebenen Optionen mit den Optionen kombinieren, die in einer oder mehreren Antwort Dateien angegeben sind. Der Compiler verarbeitet die Befehlsoptionen, während Sie gefunden werden. Daher können Befehlszeilenargumente zuvor aufgelistete Optionen in Antwort Dateien überschreiben. Umgekehrt überschreiben Optionen in einer Antwortdatei die zuvor in der Befehlszeile oder in anderen Antwort Dateien aufgeführten Optionen.

Visual Basic stellt die Datei "Vbc. rsp" bereit, die sich im gleichen Verzeichnis wie die Datei "Vbc. exe" befindet. Die Datei Vbc. rsp ist standardmäßig enthalten, es sei denn, die Option `-noconfig` wird verwendet. Weitere Informationen finden Sie unter [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).

> [!NOTE]
> Die `@`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Die folgenden Zeilen stammen aus einer Beispiel Antwortdatei.

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `@`-Option mit der Antwortdatei mit dem Namen `File1.rsp`verwendet wird.

```console
vbc @file1.rsp
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
