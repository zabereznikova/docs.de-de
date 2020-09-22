---
title: Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: d5d756f1772b9519613e163119b88a3057d36cf3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870621"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.

Die-Anweisung ist in einer-,-,-oder-Eigenschaften `Sub` `Function` Prozedur ungültig `Get` `Set` . Einige-Anweisungen können auf Modul-oder Klassenebene platziert werden. Andere, wie z `Option Strict` . b., müssen sich auf der Namespace Ebene befinden und vor allen anderen Deklarationen stehen.  
  
 **Fehler-ID:** BC30024  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie die-Anweisung aus der Prozedur.  
  
## <a name="see-also"></a>Weitere Informationen

- [Sub-Anweisung](../statements/sub-statement.md)
- [Function-Anweisung](../statements/function-statement.md)
- [Get-Anweisung](../statements/get-statement.md)
- [Set-Anweisung](../statements/set-statement.md)
