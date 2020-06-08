---
title: '@ (Antwortdatei festlegen)'
ms.date: 03/13/2018
helpviewer_keywords:
- '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
ms.openlocfilehash: 91cf1b5a55d16ab47a83fbd259dd1d83d8e9c31a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403095"
---
# <a name="-specify-response-file-visual-basic"></a>@ (Antwortdatei festlegen) (Visual Basic)

Mit dieser Option wird eine Datei angegeben, die Compileroptionen und zu kompilierende Quellcodedateien enthält.

## <a name="syntax"></a>Syntax

```console
@response_file
```

## <a name="arguments"></a>Argumente

`response_file`  
Erforderlich. Hierbei handelt es sich um eine Datei, die Compileroptionen oder zu kompilierende Quellcodedateien auflistet. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.

## <a name="remarks"></a>Hinweise

Die in einer Antwortdatei angegebenen Compileroptionen und Quellcodedateien werden vom Compiler so verarbeitet, als wären sie in der Befehlszeile angegeben.

Wenn Sie mehr als eine Antwortdatei in einer Kompilierung angeben möchten, geben Sie mehrere Antwortdateioptionen an, z. B. die folgenden:

```console
@file1.rsp @file2.rsp
```

In einer Antwortdatei können mehrere Compileroptionen und Quellcodedateien in einer Zeile angegeben werden. Eine einzelne Compileroption muss in einer Zeile angegeben werden (und darf nicht mehrere Zeilen umfassen). Antwortdateien können Kommentare aufweisen, die mit einem `#`-Symbol beginnen.

Sie können in der Befehlszeile angegebene Optionen mit Optionen kombinieren, die in einer oder mehreren Antwortdateien angegeben sind. Der Compiler verarbeitet die Befehlsoptionen in der Reihenfolge, in der sie auftreten. Daher können Befehlszeilenargumente zuvor aufgeführte Optionen in Antwortdateien außer Kraft setzen. Umgekehrt setzen Optionen in einer Antwortdatei zuvor in der Befehlszeile oder in anderen Antwortdateien aufgeführte Optionen außer Kraft.

Visual Basic stellt die Datei „Vbc.rsp“ bereit, die sich im selben Verzeichnis wie die Datei „Vbc.exe“ befindet. Die Datei „Vbc.rsp“ ist standardmäßig enthalten, es sei denn, die Option `-noconfig` wird verwendet. Weitere Informationen finden Sie unter [-noconfig](noconfig.md).

> [!NOTE]
> Die Option `@` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.

## <a name="example"></a>Beispiel

Die folgenden Zeilen stammen aus einer Beispielantwortdatei.

```console
# build the first output file
-target:exe
-out:MyExe.exe
source1.vb
source2.vb
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung der Option `@` mit der Antwortdatei mit dem Namen `File1.rsp` veranschaulicht.

```console
vbc @file1.rsp
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [-noconfig](noconfig.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
