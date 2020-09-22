---
title: Ungültiger Ordinalwert.
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 64f56b2ecace0ceafb310a175ea605e6959b7256
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871391"
---
# <a name="ordinal-is-not-valid"></a>Ungültiger Ordinalwert.

Durch den Aufrufe einer Dynamic Link Library (dll) wird angegeben, dass eine Zahl anstelle eines Prozedur namens verwendet werden soll. verwenden Sie dazu die `#num` Syntax. Dieser Fehler kann folgende Ursachen haben:  
  
- Fehler beim Konvertieren des `#num` Ausdrucks in eine Ordinalzahl.  
  
- Der `#num` angegebene gibt keine Funktion in der dll an.  
  
- Eine Typbibliothek hat eine ungültige Deklaration, die zur internen Verwendung einer ungültigen Ordinalzahl führt.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass der Ausdruck eine gültige Zahl darstellt, oder nennen Sie die Prozedur mit dem Namen.  
  
2. Stellen Sie sicher, dass `#num` eine gültige Funktion in der DLL identifiziert.  
  
3. Isolieren Sie den Prozedur Aufrufe, der das Problem verursacht, indem Sie den Code auskommentieren. Schreiben `Declare` Sie eine-Anweisung für die Prozedur, und melden Sie das Problem dem Hersteller der Typbibliothek.  
  
## <a name="see-also"></a>Weitere Informationen

- [Declare Statement](../statements/declare-statement.md)
