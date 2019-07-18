---
title: Arraygrenzen können nicht in Typbezeichnern stehen.
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 50e1cd0e41da467a9e816c8e5d64d09a36923d65
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665745"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>Arraygrenzen können nicht in Typbezeichnern stehen.
Array-Größe können nicht als Teil eines Datenspezifizierers Typ deklariert werden.  
  
 **Fehler-ID:** BC30638  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Geben Sie die Größe des Arrays unmittelbar nach dem Variablennamen, anstatt die Größe des Arrays nach dem Typ, wie im folgenden Beispiel gezeigt.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
- Definieren Sie ein Array, und initialisieren Sie es mit der gewünschten Anzahl von Elementen, wie im folgenden Beispiel gezeigt.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
