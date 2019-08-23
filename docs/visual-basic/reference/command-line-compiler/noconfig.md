---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964392"
---
# <a name="-noconfig"></a>-noconfig
Gibt an, dass der Compiler nicht automatisch auf die häufig verwendeten .NET Framework Assemblys `System` verweisen `Microsoft.VisualBasic` oder die-und-Namespaces importieren soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `-noconfig` -Option weist den Compiler an, nicht mit der Datei "Vbc. rsp" zu kompilieren, die sich im selben Verzeichnis wie die Datei "Vbc. exe" befindet. Die Datei "Vbc. rsp" verweist auf die häufig verwendeten .NET Framework Assemblys und importiert die `System` Namespaces und. `Microsoft.VisualBasic` Der Compiler verweist implizit auf die System. dll-Assembly `-nostdlib` , es sei denn, die Option wird angegeben. Die `-nostdlib` -Option weist den Compiler an, nicht mit Vbc. rsp zu kompilieren oder automatisch auf die System. dll-Assembly zu verweisen.  
  
> [!NOTE]
> Auf die Assemblys "mscorlib. dll" und "Microsoft. VisualBasic. dll" wird immer verwiesen.  
  
 Sie können die Datei Vbc. rsp ändern, um zusätzliche Compileroptionen anzugeben, die in jede Vbc. exe-Kompilierung eingeschlossen werden sollen `-noconfig` (außer bei Angabe der-Option). Weitere Informationen finden Sie unter [@ (C# Compiler Options)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) (@ [C#-Compileroptionen]).  
  
 Der Compiler verarbeitet die Optionen, die an `vbc` den Befehl zuletzt übermittelt wurden. Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung der gleichen Option in der Datei "Vbc. rsp".  
  
> [!NOTE]
> Die `-noconfig` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (Antwortdatei festlegen)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-Verweis (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
