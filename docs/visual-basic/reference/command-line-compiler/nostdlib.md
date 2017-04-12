---
title: / nostdlib (Visual Basic) | Microsoft-Dokumentation
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
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
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
ms.openlocfilehash: 3bacd7d51d12ec6c48dc11ff4b83d842a9e78a30
ms.lasthandoff: 03/13/2017

---
# <a name="nostdlib-visual-basic"></a>/nostdlib (Visual Basic)
Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a>Hinweise  
 Die `/nostdlib` Option entfernt den automatischen Verweis auf die Assembly System.dll und verhindert, dass den Compiler die Datei Vbc.rsp liest. Die Datei Vbc.rsp – befindet sich im gleichen Verzeichnis wie die Datei Vbc.exe – verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys und importiert die `System` und `Microsoft.VisualBasic` Namespaces.  
  
> [!NOTE]
>  Die "mscorlib.dll" und "Microsoft.VisualBasic.dll" wird immer verwiesen.  
  
> [!NOTE]
>  Die `/nostdlib` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` ohne die Standardbibliotheken zu verweisen. Müssen Sie festlegen, die `_MYTYPE` Konstante für die bedingte Kompilierung auf die Zeichenfolge "Empty" So entfernen Sie die `My` Objekt.  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
