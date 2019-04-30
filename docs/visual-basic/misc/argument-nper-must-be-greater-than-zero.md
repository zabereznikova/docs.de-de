---
title: Das Argument „Zzr“ muss größer als 0 (null) sein.
ms.date: 07/20/2015
f1_keywords:
- vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
ms.openlocfilehash: 6f54a2da0eb0c1cc31a4aa536fdcb59026240a25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977144"
---
# <a name="argument-nper-must-be-greater-than-zero"></a>Das Argument „Zzr“ muss größer als 0 (null) sein.
Die `NPer` -Funktion, die als Anzahl der Zeiträume für eine Annuität basierend auf regelmäßigen, festen Zahlungen und einem festen Zinssatz `Double` zurückgibt, erfordert ein Argument, das größer als 0 (null) ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Überprüfen Sie die Schreibweise der Argumente im Ausdruck. Ein falsch geschriebener Variablenname kann implizit eine numerische Variable erstellen, die mit Null initialisiert wird.  
  
- Überprüfen Sie vorherige Vorgänge für Variablen im Ausdruck, insbesondere solche, die als Argumente aus anderen Prozeduren an die Prozedur übergeben werden.  
  
## <a name="see-also"></a>Siehe auch

- [Übergeben von Argumenten als Wert und als Verweis](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
