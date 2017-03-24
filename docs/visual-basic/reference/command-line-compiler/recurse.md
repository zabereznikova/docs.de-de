---
title: / recurse | Microsoft-Dokumentation
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
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: fbf7d67c7f70345e62ddbb03c8626b688b5c593b
ms.lasthandoff: 03/13/2017

---
# <a name="recurse"></a>/recurse
Kompiliert Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses oder des Projektverzeichnisses.  
  
## <a name="syntax"></a>Syntax  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumente  
 `dir`  
 Optional. Das Verzeichnis, in dem Sie die Suche beginnen soll. Wenn nicht angegeben, beginnt die Suche im Projektverzeichnis.  
  
 `file`  
 Erforderlich. Die zu suchenden Dateien. Platzhalterzeichen sind zulässig.  
  
## <a name="remarks"></a>Hinweise  
 Sie können Platzhalter in einem Dateinamen verwenden, kompilieren Sie alle entsprechende Dateien im Projektverzeichnis ohne `/recurse`. Wenn kein Ausgabedateiname angegeben wird, basiert der Compiler den Namen der Ausgabedatei der ersten Eingabedatei verarbeitet. Dies ist normalerweise die erste Datei in der Liste der Dateien, die kompiliert, wenn alphabetisch angezeigt. Aus diesem Grund empfiehlt sich, geben Sie eine Ausgabe mit den `/out` Option.  
  
> [!NOTE]
>  Die `/recurse` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert werden alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien im aktuellen Verzeichnis.  
  
```  
vbc *.vb  
```  
  
 Der folgende Code kompiliert alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien in der `Test\ABC` Verzeichnis und in allen Verzeichnissen unter, und generiert dann `Test.ABC.dll`.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
