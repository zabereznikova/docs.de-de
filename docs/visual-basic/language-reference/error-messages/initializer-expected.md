---
title: Initialisierer erwartet
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 2c5a65443dc16a600e25fcf6dfd11c4597b3a086
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873957"
---
# <a name="initializer-expected"></a>Initialisierer erwartet

Sie haben versucht, eine Instanz einer Klasse zu deklarieren, indem Sie einen Objektinitialisierer verwenden, in dem die Initialisierungs Liste leer ist, wie im folgenden Beispiel gezeigt.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 Mindestens ein Feld oder eine Eigenschaft muss in der Initialisiererliste initialisiert werden, wie im folgenden Beispiel gezeigt.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Fehler-ID:** BC30996  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Initialisieren Sie mindestens ein Feld oder eine Eigenschaft im Initialisierer, oder verwenden Sie keinen Objektinitialisierer.  
  
## <a name="see-also"></a>Weitere Informationen

- [Objektinitialisierer: benannte und anonyme Typen](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
