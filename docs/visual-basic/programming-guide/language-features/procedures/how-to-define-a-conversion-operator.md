---
title: 'Vorgehensweise: Definieren eines Konvertierungsoperators'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 53b0211c6304625edd7ac24fa52ff0c051d8f0a0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388088"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Gewusst wie: Definieren eines Konvertierungsoperators (Visual Basic)
Wenn Sie eine Klasse oder Struktur definiert haben, können Sie einen Typkonvertierungs Operator zwischen dem Typ der Klasse oder Struktur und einem anderen Datentyp (z `Integer` . b `Double` ., oder `String` ) definieren.  
  
 Definieren Sie die Typkonvertierung als [CType-Funktions](../../../language-reference/functions/ctype-function.md) Prozedur innerhalb der Klasse oder Struktur. Alle Konvertierungs Prozeduren müssen sein `Public Shared` , und jeder muss entweder eine [Erweiterung](../../../language-reference/modifiers/widening.md) oder eine [Einschränkung](../../../language-reference/modifiers/narrowing.md)angeben.  
  
 Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Konvertierungs Operatoren zwischen einer Struktur mit `digit` dem Namen und einer definiert `Byte` .  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 Sie können die Struktur `digit` mit dem folgenden Code testen.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Operators](./how-to-define-an-operator.md)
- [Vorgehensweise: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Vorgehensweise: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Structure Statement](../../../language-reference/statements/structure-statement.md)
- [Vorgehensweise: Deklarieren einer Struktur](../data-types/how-to-declare-a-structure.md)
- [Implizite und explizite Konvertierungen](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
