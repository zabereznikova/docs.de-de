---
title: Das Argument „Zzr“ muss größer als 0 (null) sein.
ms.date: 07/20/2015
f1_keywords:
- vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
ms.openlocfilehash: f0185e30cb711472105955f5febf8d7702b29c72
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087140"
---
# <a name="argument-nper-must-be-greater-than-zero"></a>Das Argument „Zzr“ muss größer als 0 (null) sein.

Die `NPer` -Funktion, die als Anzahl der Zeiträume für eine Annuität basierend auf regelmäßigen, festen Zahlungen und einem festen Zinssatz `Double` zurückgibt, erfordert ein Argument, das größer als 0 (null) ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Überprüfen Sie die Schreibweise der Argumente im Ausdruck. Ein falsch geschriebener Variablenname kann implizit eine numerische Variable erstellen, die mit 0 (null) initialisiert wird.  
  
- Überprüfen Sie vorherige Vorgänge für Variablen im Ausdruck, insbesondere solche, die als Argumente aus anderen Prozeduren an die Prozedur übergeben werden.  
  
## <a name="see-also"></a>Siehe auch

- [Übergeben von Argumenten als Wert und als Verweis](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
