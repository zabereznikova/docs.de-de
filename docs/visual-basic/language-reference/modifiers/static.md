---
title: Static
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f020756466888f51298abb423997906ddc7caff7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350758"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte lokale Variablen weiterhin vorhanden sein müssen, und behält ihre aktuellen Werte nach der Beendigung der Prozedur bei, in der Sie deklariert wurden.  
  
## <a name="remarks"></a>Hinweise  
 Normalerweise ist eine lokale Variable in einer Prozedur nicht mehr vorhanden, sobald die Prozedur beendet wird. Eine statische Variable ist weiterhin vorhanden und behält ihren letzten Wert bei. Wenn der Code das nächste Mal die Prozedur aufruft, wird die Variable nicht erneut initialisiert, und Sie enthält weiterhin den neuesten Wert, den Sie zugewiesen haben. Eine statische Variable ist für die Lebensdauer der Klasse oder des Moduls, in der Sie definiert ist, weiterhin vorhanden.  
  
## <a name="rules"></a>Regeln  
  
- **Deklarations Kontext.** Sie können `Static` nur für lokale Variablen verwenden. Dies bedeutet, dass der Deklarations Kontext für eine `Static` Variable eine Prozedur oder ein Block in einer Prozedur sein muss. es kann sich dabei nicht um eine Quelldatei, einen Namespace, eine Klasse, eine Struktur oder ein Modul handeln.  
  
     Sie können `Static` nicht innerhalb einer Struktur Prozedur verwenden.  
  
- Die Datentypen von `Static` lokalen Variablen können nicht abgeleitet werden. Weitere Informationen finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
- **Kombinierte modifiziererer.** Sie können `Static` nicht mit `ReadOnly`, `Shadows`oder `Shared` in derselben Deklaration angeben.  
  
## <a name="behavior"></a>Verhalten  
 Wenn Sie in einer `Shared` Prozedur eine statische Variable deklarieren, ist nur eine Kopie der statischen Variablen für die gesamte Anwendung verfügbar. Sie können eine `Shared` Prozedur mit dem Klassennamen, nicht mit einer Variablen, die auf eine Instanz der-Klasse verweist, abrufen.  
  
 Wenn Sie in einer Prozedur, die nicht `Shared`ist, eine statische Variable deklarieren, ist nur eine Kopie der Variablen für jede Instanz der Klasse verfügbar. Sie können eine nicht freigegebene Prozedur mit einer Variablen aufzurufen, die auf eine bestimmte Instanz der-Klasse verweist.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung von `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 Die `Static` Variable `totalSales` wird nur einmal auf 0 initialisiert. Jedes Mal, wenn Sie `updateSales`eingeben, verfügt `totalSales` immer noch über den neuesten Wert, den Sie für ihn berechnet haben.  
  
 Der `Static` Modifizierer kann in diesem Kontext verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Lebensdauer in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
