---
title: "Arraygrenzen können nicht in Typbezeichnern stehen."
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords: BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770f86ca960110965b6917a22d284678ff8b6f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>Arraygrenzen können nicht in Typbezeichnern stehen.
Array-Größe können nicht als Teil von einem Datentyp Datenspezifizierer deklariert werden.  
  
 **Fehler-ID:** BC30638  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Geben Sie die Größe des Arrays unmittelbar nach dem Variablennamen, statt die Array-Größe nach dem Typ, wie im folgenden Beispiel gezeigt.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   Definieren Sie ein Array, und initialisieren Sie es mit der gewünschten Anzahl von Elementen, wie im folgenden Beispiel gezeigt.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
