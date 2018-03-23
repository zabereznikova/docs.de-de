---
title: -noconfig
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2cebc617aea9ebbb16197f27841794b2e6ad46ea
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-noconfig"></a>-noconfig
Gibt an, dass der Compiler nicht automatisch die häufig verwendeten verweisen soll [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys oder Importieren der `System` und `Microsoft.VisualBasic` Namespaces.  
  
## <a name="syntax"></a>Syntax  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `-noconfig` Option weist den Compiler nicht, um mit der Datei "vbc.rsp" zu kompilieren, der sich im gleichen Verzeichnis wie die Datei Vbc.exe befindet. Die Datei "vbc.rsp" verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces. Der Compiler verweist implizit auf die Assembly "System.dll", es sei denn, die `-nostdlib` angegeben wird. Die `-nostdlib` Option weist den Compiler nicht mit Vbc.rsp kompiliert oder automatisch auf die "System.dll"-Assembly verweisen.  
  
> [!NOTE]
>  Die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" Assemblys werden immer auf die verwiesen wird.  
  
 Sie können die Datei "vbc.rsp", um zusätzliche Compileroptionen anzugeben, die in jeder Vbc.exe-Kompilierung enthalten sein sollen (außer bei Angabe der `-noconfig` Option). Weitere Informationen finden Sie unter [@ (C# Compiler Options)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md) (@ [C#-Compileroptionen]).  
  
 Der Compiler verarbeitet die Optionen zum Übergeben der `vbc` den letzten Befehl. Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung der gleichen-Option in der Datei "vbc.rsp".  
  
> [!NOTE]
>  Die `-noconfig` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="see-also"></a>Siehe auch  
 [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [@ (Antwortdatei festlegen)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [-Verweis (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
