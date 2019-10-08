---
title: /debug (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: c2fbe5aa6f0b9ac8c99c9b9ec5cdf0a7d9764ab8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002408"
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
|`full` &#124; `pdbonly`|Optional. Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden. Wenn Sie `/debug:pdbonly` nicht angeben, ist der Standardwert `full`, sodass Sie einen Debugger an das laufende Programm anfügen können. Das Argument "`pdbonly`" ermöglicht das Debuggen von Quellcode, wenn das Programm im Debugger gestartet wird. es wird jedoch nur assemblysprachcode angezeigt, wenn das laufende Programm an den Debugger angefügt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, um Debugbuilds zu erstellen. Wenn Sie `/debug`, `/debug+` oder `/debug:full` nicht angeben, können Sie die Ausgabedatei Ihres Programms nicht debuggen.  
  
 Standardmäßig werden keine Debuginformationen ausgegeben (`/debug-`). Geben Sie `/debug` oder `/debug+` an, um Debuginformationen auszugeben.  
  
 Informationen zur Konfiguration der Leistung einer Anwendung beim Debuggen finden Sie unter [Erleichtern des Debuggens für ein Image](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
|So legen Sie-Debug in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|---|  
|1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **Erweiterte Kompilierungsoptionen**.<br />4.  Ändern Sie den Wert im Feld **Debuginformationen generieren** .|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Debuginformationen in der Ausgabedatei `App.exe` gespeichert.  
  
```console  
vbc -debug -out:app.exe test.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
