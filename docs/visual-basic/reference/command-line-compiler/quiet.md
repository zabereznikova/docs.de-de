---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: e67fe05507c8cb3edd7f46cad19211ba11e3b054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-quiet"></a>-quiet
Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
-quiet  
```  
  
## <a name="remarks"></a>Hinweise  
 In der Standardeinstellung ist `-quiet` nicht aktiv. Wenn der Compiler ein syntaxbezogene Fehler oder eine Warnung gemeldet wird, können sie auch die Zeile aus Quellcode ausgegeben. Für Anwendungen, die Compilerausgabe zu analysieren, kann es praktischer für den Compiler an, nur den Text der Diagnose ausgegeben sein.  
  
 Im folgenden Beispiel `Module1` gibt einen Fehler, der Quellcode bei der Kompilierung ohne enthält `-quiet`.  
  
```vb  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 Ausgabe:  
 
```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
``` 
 Kompilierte mit `-quiet`, der Compiler gibt nur die folgenden:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  Die `-quiet` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und Code für syntaxbezogene Compilerdiagnose nicht angezeigt wird:  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
