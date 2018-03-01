---
title: Initialisierer erwartet
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 46ff91ec240212571f7ec9f26e82d9d128263545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="initializer-expected"></a>Initialisierer erwartet
Sie haben versucht, eine Instanz einer Klasse mithilfe eines Objektinitialisierers, in dem eine die Initialisierungsliste leer ist, wie im folgenden Beispiel gezeigt, deklarieren.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 Mindestens ein Feld oder eine Eigenschaft muss in der Initialisiererliste initialisiert werden, wie im folgenden Beispiel gezeigt.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Fehler-ID:** BC30996  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Mindestens ein Feld oder eine Eigenschaft im Initialisierer zu initialisieren, oder einen Objektinitialisierer nicht verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
