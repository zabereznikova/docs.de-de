---
title: /debug (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18d74b8f0a7b319e08780a8db9175c7be16d932e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654147"
---
# <a name="-debug-visual-basic"></a>-Debug (Visual Basic)
Bewirkt, dass der Compiler Debuginformationen zu generieren und in den Ausgabedateien zu speichern.  
  
## <a name="syntax"></a>Syntax  
  
```  
-debug[+ | -]  
' -or-  
-debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Angeben von `+` oder `/debug` bewirkt, dass der Compiler Debuginformationen generiert und in einer PDB-Datei zu speichern. Angeben von `-` hat dieselbe Wirkung wie das Angeben von nicht `/debug`.|  
|`full` &#124; `pdbonly`|Dies ist optional. Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden. Wenn Sie keinen angeben `/debug:pdbonly`, der Standardwert ist `full`, können Sie einen Debugger an die ausgeführte Anwendung anfügen. Die `pdbonly` Argument ermöglicht das Debuggen von Quellcode, wenn das Programm im Debugger gestartet wird, aber es zeigt Assemblersprache Code nur, wenn die ausgeführte Anwendung an den Debugger angefügt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, um Debugbuilds zu erstellen. Wenn Sie keinen angeben `/debug`, `/debug+`, oder `/debug:full`, kann die Ausgabedatei des Programms zu debuggen.  
  
 Standardmäßig Debuginformationen wird nicht ausgegeben (`/debug-`). Geben Sie das Ausgeben von Debuginformationen, `/debug` oder `/debug+`.  
  
 Informationen zur Konfiguration der Leistung einer Anwendung beim Debuggen finden Sie unter [Erleichtern des Debuggens für ein Image](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
|Zum Festlegen von - debug, in der integrierten Entwicklungsumgebung von Visual Studio|  
|---|  
|1.  Klicken Sie bei ausgewähltem Projekt im **Projektmappen-Explorer**im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **Erweiterte Kompilierungsoptionen**.<br />4.  Ändern Sie den Wert in der **Debuginfo generieren** Feld.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel fügt Debuginformationen in Ausgabedatei `App.exe`.  
  
```  
vbc -debug -out:app.exe test.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
