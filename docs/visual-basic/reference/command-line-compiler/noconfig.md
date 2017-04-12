---
title: / noconfig | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 304d0e7fc787adb1d7776a2c047090ffc230fcc1
ms.lasthandoff: 03/13/2017

---
# <a name="noconfig"></a>/noconfig
Gibt an, dass der Compiler nicht automatisch der häufig verwendeten verweisen sollten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys oder Importieren der `System` und `Microsoft.VisualBasic` Namespaces.  
  
## <a name="syntax"></a>Syntax  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `/noconfig` Option weist den Compiler an, nicht mit der Datei Vbc.rsp kompilieren, die sich im gleichen Verzeichnis wie die Datei Vbc.exe befindet. Die Datei Vbc.rsp verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces. Der Compiler verweist implizit auf die Assembly System.dll, es sei denn, die `/nostdlib` angegeben wird. Die `/nostdlib` Option weist den Compiler nicht mit Vbc.rsp kompiliert oder automatisch auf die Assembly System.dll.  
  
> [!NOTE]
>  Die "mscorlib.dll" und "Microsoft.VisualBasic.dll" wird immer verwiesen.  
  
 Sie können die Datei Vbc.rsp bearbeiten zusätzliche Compileroptionen angibt, die in jeder Vbc.exe-Kompilierung enthalten sein soll (außer bei Angabe der `/noconfig` Option). Weitere Informationen finden Sie unter [@ (C# Compiler Options)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) (@ [C#-Compileroptionen]).  
  
 Der Compiler verarbeitet die Optionen zum Übergeben der `vbc` den letzten Befehl. Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung derselben Option in der Vbc.rsp-Datei.  
  
> [!NOTE]
>  Die `/noconfig` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="see-also"></a>Siehe auch  
 [/ nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)   
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [@ (Antwortdatei festlegen)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
