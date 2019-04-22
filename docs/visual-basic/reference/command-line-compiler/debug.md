---
title: /debug (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
ms.openlocfilehash: 9bf7170cee31f92481b15fb1227f21895cd3734d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827977"
---
# <a name="-debug-visual-basic"></a>-Debug (Visual Basic)
Bewirkt, dass der Compiler Debuginformationen generiert, und fügen Sie ihn in den Ausgabedateien.  
  
## <a name="syntax"></a>Syntax  
  
```  
-debug[+ | -]  
' -or-  
-debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Angeben von `+` oder `/debug` bewirkt, dass der Compiler Debuginformationen und platziert diese in eine PDB-Datei. Angeben von `-` hat dieselbe Wirkung wie beim Angeben von nicht `/debug`.|  
|`full` &#124; `pdbonly`|Dies ist optional. Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden. Wenn Sie keinen angeben `/debug:pdbonly`, der Standardwert ist `full`, dem Sie einen Debugger an ein ausgeführtes Programm anfügen können. Die `pdbonly` Argument ermöglicht das Debuggen von Quellcode, wenn das Programm im Debugger gestartet wird, es wird jedoch der Assemblersprachcode – nur, wenn das aktive Programm an den Debugger angefügt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, um Debugbuilds zu erstellen. Wenn Sie keinen angeben `/debug`, `/debug+`, oder `/debug:full`, Sie werden die Ausgabedatei Ihres Programms nicht debuggen.  
  
 In der Standardeinstellung Debuginformationen wird nicht ausgegeben (`/debug-`). Geben Sie Informationen zum Debuggen auszugeben, `/debug` oder `/debug+`.  
  
 Informationen zur Konfiguration der Leistung einer Anwendung beim Debuggen finden Sie unter [Erleichtern des Debuggens für ein Image](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
|Um die set - Debuggen Sie in der integrierten Entwicklungsumgebung von Visual Studio|  
|---|  
|1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **Erweiterte Kompilierungsoptionen**.<br />4.  Ändern Sie den Wert in der **Debuginfo generieren** Feld.|  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden Informationen zum Debuggen in Ausgabedatei `App.exe`.  
  
```  
vbc -debug -out:app.exe test.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
