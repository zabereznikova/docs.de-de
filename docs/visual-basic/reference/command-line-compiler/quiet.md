---
title: /quiet
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b816cadb9d805d57a14e9b5df553654dd8167af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="quiet"></a>/quiet
Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/quiet  
```  
  
## <a name="remarks"></a>Hinweise  
 In der Standardeinstellung ist `/quiet` nicht aktiv. Wenn der Compiler ein syntaxbezogene Fehler oder eine Warnung gemeldet wird, können sie auch die Zeile aus Quellcode ausgegeben. Für Anwendungen, die Compilerausgabe zu analysieren, kann es praktischer für den Compiler an, nur den Text der Diagnose ausgegeben sein.  
  
 Im folgenden Beispiel `Module1` gibt einen Fehler, der Quellcode bei der Kompilierung ohne enthält `/quiet`.  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 Ausgabe:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 Kompilierte mit `/quiet`, der Compiler gibt nur die folgenden:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  Die `/quiet` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und Code für syntaxbezogene Compilerdiagnose nicht angezeigt wird:  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
