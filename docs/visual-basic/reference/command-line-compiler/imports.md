---
title: /imports (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e8e9cd761263b3b61a4e6d3e33c5f7f875be7a1d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imports-visual-basic"></a>/imports (Visual Basic)
Importiert Namespaces aus der angegebenen Assembly.  
  
## <a name="syntax"></a>Syntax  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`namespaceList`|Erforderlich. Durch Trennzeichen getrennte Liste der Namespaces importiert werden sollen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `/imports` Option importiert alle Namespaces in die aktuelle Gruppe, der Quelldateien oder einer referenzierten Assembly definiert.  
  
 Die Elemente in einem Namespace mit angegebenen `/imports` stehen für alle Quellcodedateien in der Kompilierung. Verwenden Sie die [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) auf einen Namespace in einer einzelnen Quellcodedatei verwenden.  
  
|Festlegen/importiert Sie in der integrierten Entwicklungsumgebung von Visual Studio|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Verweise**.<br />3.  Geben Sie den Namespacenamen in das Feld neben dem **Benutzerimport** Schaltfläche.<br />4.  Klicken Sie auf die **Benutzerimport** Schaltfläche.|  
  
## <a name="example"></a>Beispiel  
 Im folgende Code wird kompiliert, wenn `/imports:system` angegeben ist.  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
