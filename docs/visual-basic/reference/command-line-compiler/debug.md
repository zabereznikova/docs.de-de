---
title: /debug
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 3beb9ad3829c2f55120a9136e6e54185551bd20b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344778"
---
# <a name="-debug-visual-basic"></a>-Debug (Visual Basic)

Bewirkt, dass der Compiler Debuginformationen generiert und Sie in der Ausgabedatei (en) platziert.

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
|`+` &#124; `-`|Optional. Wenn Sie `+` oder `/debug` angeben, generiert der Compiler Debuginformationen und platziert Sie in einer PDB-Datei. Das Angeben von `-` hat denselben Effekt wie das Angeben von `/debug`.|
|`full` &#124; `pdbonly`|Optional. Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden. Wenn Sie `/debug:pdbonly`nicht angeben, wird der Standardwert `full`, sodass Sie einen Debugger an das laufende Programm anfügen können. Das `pdbonly`-Argument ermöglicht das Debuggen von Quellcode, wenn das Programm im Debugger gestartet wird. es wird jedoch nur assemblysprachcode angezeigt, wenn das laufende Programm an den Debugger angefügt wird.|

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Option, um Debugbuilds zu erstellen. Wenn Sie `/debug`, `/debug+`oder `/debug:full`nicht angeben, können Sie die Ausgabedatei Ihres Programms nicht debuggen.

Standardmäßig werden keine Debuginformationen ausgegeben (`/debug-`). Um Debuginformationen auszugeben, geben Sie `/debug` oder `/debug+`an.

Informationen zur Konfiguration der Leistung einer Anwendung beim Debuggen finden Sie unter [Erleichtern des Debuggens für ein Image](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).

|So legen Sie-Debug in der integrierten Entwicklungsumgebung von Visual Studio fest|
|---|
|1. Wenn ein Projekt in **Projektmappen-Explorer**ausgewählt ist, klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2. Klicken Sie auf die Registerkarte **Kompilieren** .<br />3. Klicken Sie auf **Erweiterte Kompilierungsoptionen**.<br />4. ändern Sie den Wert im Feld **Debuginformationen generieren** .|

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden Debuginformationen in die Ausgabedatei `App.exe`.

```console
vbc -debug -out:app.exe test.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
