---
title: Initialisierer erwartet
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 0795fdc1c4b177e13979d7555cd7588217b8cb4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334964"
---
# <a name="initializer-expected"></a>Initialisierer erwartet
Sie haben versucht, eine Instanz einer Klasse deklarieren, indem Sie mit einem Objektinitialisierer, in dem eine die Initialisierungsliste leer ist, wie im folgenden Beispiel gezeigt.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 Mindestens ein Feld oder eine Eigenschaft muss in der Initialisiererliste initialisiert werden, wie im folgenden Beispiel gezeigt.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Fehler-ID:** BC30996  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Initialisieren Sie mindestens ein Feld oder eine Eigenschaft im Initialisierer zu, oder verwenden Sie einen Objektinitialisierer nicht.  
  
## <a name="see-also"></a>Siehe auch

- [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
