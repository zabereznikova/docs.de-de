---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: 44bc619c489fdff36f0b595f7d8934689b859adb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819436"
---
# <a name="-noconfig"></a>-noconfig
Gibt an, dass der Compiler nicht automatisch die häufig verwendeten verweisen sollten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys oder Import der `System` und `Microsoft.VisualBasic` Namespaces.  
  
## <a name="syntax"></a>Syntax  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `-noconfig` -Option weist den Compiler an, nicht mit der Datei "vbc.rsp" zu kompilieren, die im selben Verzeichnis wie die Datei Vbc.exe befindet. Die Datei "vbc.rsp" verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces. Der Compiler verweist implizit auf die Assembly "System.dll", es sei denn, die `-nostdlib` angegeben wird. Die `-nostdlib` -Option weist den Compiler nicht mit Vbc.rsp durch oder automatisch auf die System.dll-Assembly verweisen.  
  
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
