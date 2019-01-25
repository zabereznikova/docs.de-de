---
title: Initialisierer erwartet
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 1fa66a3c50b5c1eadd4c63b92c57ab60e1a11076
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595993"
---
# <a name="initializer-expected"></a>Initialisierer erwartet
Sie haben versucht, eine Instanz einer Klasse deklarieren, indem Sie mit einem Objektinitialisierer, in dem eine die Initialisierungsliste leer ist, wie im folgenden Beispiel gezeigt.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 Mindestens ein Feld oder eine Eigenschaft muss in der Initialisiererliste initialisiert werden, wie im folgenden Beispiel gezeigt.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Fehler-ID:** BC30996  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Initialisieren Sie mindestens ein Feld oder eine Eigenschaft im Initialisierer zu, oder verwenden Sie einen Objektinitialisierer nicht.  
  
## <a name="see-also"></a>Siehe auch
- [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
