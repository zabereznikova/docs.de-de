---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: b707899c845b6b08e008fe229497f682c930044a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588848"
---
# <a name="-noconfig"></a>-noconfig
Gibt an, dass der Compiler sollte nicht automatisch auf die häufig verwendete .NET Framework-Assemblys verweisen, oder Importieren der `System` und `Microsoft.VisualBasic` Namespaces.  
  
## <a name="syntax"></a>Syntax  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `-noconfig` -Option weist den Compiler an, nicht mit der Datei "vbc.rsp" zu kompilieren, die im selben Verzeichnis wie die Datei Vbc.exe befindet. Die Datei "vbc.rsp" verweist auf die häufig verwendete .NET Framework-Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces. Der Compiler verweist implizit auf die Assembly "System.dll", es sei denn, die `-nostdlib` angegeben wird. Die `-nostdlib` -Option weist den Compiler nicht mit Vbc.rsp durch oder automatisch auf die System.dll-Assembly verweisen.  
  
> [!NOTE]
>  Die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll"-Assemblys werden immer auf die verwiesen wird.  
  
 Sie können die Datei "vbc.rsp", um zusätzliche Compileroptionen angeben, die in jeder Kompilierung Vbc.exe enthalten sein sollen (außer bei Angabe der `-noconfig` Option). Weitere Informationen finden Sie unter [@ (C# Compiler Options)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) (@ [C#-Compileroptionen]).  
  
 Der Compiler verarbeitet die Optionen, die an die `vbc` den letzten Befehl. Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung für die gleiche Option in der Datei "vbc.rsp".  
  
> [!NOTE]
>  Die `-noconfig` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (Antwortdatei festlegen)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-Referenz (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
