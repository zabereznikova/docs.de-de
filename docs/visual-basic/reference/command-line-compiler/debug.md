---
title: -Debug
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: df65d1c095f5a22d562d78e15baf750a20ec2556
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716775"
---
# <a name="-debug-visual-basic"></a>-debug (Visual Basic)

Führt dazu, dass der Compiler Debuginformationen generiert und sie in der Ausgabedatei bzw. in Ausgabedateien platziert.

## <a name="syntax"></a>Syntax

```console
-debug[+ | -]
```

oder

```console
-debug:[full | pdbonly]
```

## <a name="arguments"></a>Argumente

|Begriff|Definition|
|---|---|
|`+` &#124; `-`|Dies ist optional. Wenn `+` oder `-debug` angegeben wird, generiert der Compiler Debuginformationen und speichert sie in einer PDB-Datei. Wenn `-` angegeben wird, hat dies dieselben Auswirkungen, wie wenn `-debug` nicht angegeben wird.|
|`full` &#124; `pdbonly`|Dies ist optional. Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden. Wenn Sie `-debug:pdbonly` angeben, lautet der Standardwert `full`. Dadurch können Sie einen Debugger an das Programm anfügen, das ausgeführt wird. Das Argument `pdbonly` macht das Debuggen von Quellcode möglich, wenn das Programm im Debugger gestartet wird. Code in der Sprache der Assembly wird aber nur angezeigt, wenn das aktive Programm an den Debugger angefügt ist.|

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Option, um Debugbuilds zu erstellen. Wenn Sie `-debug`, `-debug+` oder `-debug:full` nicht angeben, können Sie die Ausgabedatei Ihres Programms nicht debuggen.

Standardmäßig werden keine Debuginformationen ausgegeben (`-debug-`). Wenn Debuginformationen ausgeben werden sollen, geben Sie `-debug` oder `-debug+` an.

Informationen zur Konfiguration der Leistung einer Anwendung beim Debuggen finden Sie unter [Erleichtern des Debuggens für ein Image](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).

|So legen Sie -debug in der integrierten Visual Studio-Entwicklungsumgebung fest|
|---|
|1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **Erweiterte Kompilierungsoptionen**.<br />4.  Ändern Sie den Wert im Feld **Debuginfo generieren** entsprechend.|

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden Debuginformationen in der Ausgabedatei `App.exe` platziert.

```console
vbc -debug -out:app.exe test.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
