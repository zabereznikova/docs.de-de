---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005433"
---
# <a name="-noconfig"></a>-noconfig
Gibt an, dass der Compiler nicht automatisch auf die häufig verwendeten .NET Framework Assemblys verweisen oder die Namespaces "`System`" und "`Microsoft.VisualBasic`" importieren soll.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Option "`-noconfig`" weist den Compiler an, nicht mit der Datei "Vbc. rsp" zu kompilieren, die sich im selben Verzeichnis wie die Datei "Vbc. exe" befindet. Die Datei "Vbc. rsp" verweist auf die häufig verwendeten .NET Framework Assemblys und importiert die Namespaces "`System`" und "`Microsoft.VisualBasic`". Der Compiler verweist implizit auf die System. dll-Assembly, es sei denn, die Option `-nostdlib` ist angegeben. Die Option `-nostdlib` weist den Compiler an, nicht mit der Datei "Vbc. rsp" zu kompilieren oder automatisch auf die System. dll-Assembly zu verweisen.  
  
> [!NOTE]
> Auf die Assemblys "mscorlib. dll" und "Microsoft. VisualBasic. dll" wird immer verwiesen.  
  
 Sie können die Datei Vbc. rsp ändern, um zusätzliche Compileroptionen anzugeben, die in jede Vbc. exe-Kompilierung eingeschlossen werden sollen (außer beim Angeben der Option `-noconfig`). Weitere Informationen finden Sie unter [@ (C# Compiler Options)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) (@ [C#-Compileroptionen]).  
  
 Der Compiler verarbeitet die Optionen, die an den Befehl "`vbc`" zuletzt übermittelt wurden. Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung der gleichen Option in der Datei "Vbc. rsp".  
  
> [!NOTE]
> Die Option "`-noconfig`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (Antwortdatei festlegen)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-Verweis (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
