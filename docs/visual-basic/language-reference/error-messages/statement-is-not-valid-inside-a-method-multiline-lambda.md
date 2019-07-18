---
title: Die Anweisung ist innerhalb einer Methode-mehrzeiligen Lambda-Ausdrucks ungültig
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: 9e6c8ddd7851aee6d9fa1928a6854f7337b867b0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593225"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Die Anweisung ist innerhalb einer Methode oder eines mehrzeiligen Lambda-Ausdrucks nicht gültig.
Die Anweisung gilt nicht innerhalb einer `Sub`, `Function`, Eigenschaft `Get`, oder die Eigenschaft `Set` Verfahren. Einige Anweisungen können auf der Ebene Projektmoduls oder der Klasse platziert werden. Andere, z. B. `Option Strict`, muss auf Namespaceebene und allen anderen Deklarationen voranstehen.  
  
 **Fehler-ID:** BC30024  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Entfernen Sie die Anweisung von der Prozedur.  
  
## <a name="see-also"></a>Siehe auch

- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
