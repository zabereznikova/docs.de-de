---
title: / optimize | Microsoft-Dokumentation
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
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization, enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
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
ms.openlocfilehash: bb89b94ab0d431ed79f94f22afd0bd077728b754
ms.lasthandoff: 03/13/2017

---
# <a name="optimize"></a>/optimize
Aktiviert oder deaktiviert die Compiler-Optimierungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Optional. Die `/optimize-` Option compileroptimierungen deaktiviert. Die `/optimize+` -Option aktiviert Optimierungen. Standardmäßig sind Optimierungen deaktiviert.|  
  
## <a name="remarks"></a>Hinweise  
 Compileroptimierungen stellen Ihre Ausgabedatei kleiner, schneller und effizienter. Jedoch, da Optimierungen führen zu neuanordnungen von Code in der Ausgabedatei `/optimize+` kann das Debuggen erschwert.  
  
 Alle Module mit generiert `/target:module` für eine Assembly, die die gleiche verwenden muss `/optimize` Einstellungen wie die Assembly. Weitere Informationen finden Sie unter [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Sie können Kombinieren der `/optimize` und `/debug` Optionen.  
  
|So legen Sie / optimieren, in der Visual Studio-IDE|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.<br />     Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die **Kompilieren** Registerkarte.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert** .<br />4.  Ändern der **Optimierungen aktivieren** das Kontrollkästchen.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und compileroptimierungen aktiviert.  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/ target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
