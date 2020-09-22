---
title: Die Indexanzahl ist größer als die Anzahl der Dimensionen des indizierten Arrays.
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 3fc2744bb471eabd9345994b28fbef3ebc76f00d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873664"
---
# <a name="number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a>Die Indexanzahl ist größer als die Anzahl der Dimensionen des indizierten Arrays.

Die Indexanzahl, die für den Zugriff auf ein Arrayelement verwendet wird, muss mit dem Rang des Arrays identisch sein, d. h. die Anzahl der für das Array deklarierten Dimensionen.  
  
 **Fehler-ID:** BC30106  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie die Indizes aus dem Array Verweis, bis die Gesamtzahl der abonniert dem Rang des Arrays gleicht. Beispiel:  
  
    ```vb  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Arrays](../../programming-guide/language-features/arrays/index.md)
