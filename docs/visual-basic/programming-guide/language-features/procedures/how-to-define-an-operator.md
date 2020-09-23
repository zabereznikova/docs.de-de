---
title: 'Vorgehensweise: Definieren eines Operators'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: 5acbd0439ddbb956b80d56e23d11cd5e152f37ff
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087400"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Gewusst wie: Definieren eines Operators (Visual Basic)

Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten eines Standard Operators (z. b. `*` , `<>` oder) definieren, `And` Wenn mindestens einer der Operanden vom Typ der Klasse oder Struktur ist.  
  
 Definieren Sie den Standard Operator als Operator Prozedur innerhalb der Klasse oder Struktur. Alle Operator Prozeduren müssen sein `Public` `Shared` .  
  
 Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird der- `+` Operator für eine Struktur mit dem Namen definiert `height` . Die Struktur verwendet Höhen, gemessen in Höhe und Zoll. Ein *Zoll* beträgt 2,54 Zentimeter und ein *Fuß* ist 12 Zoll. Um normalisierte Werte (Zoll < 12,0) sicherzustellen, führt der Konstruktor *Modulo* 12-Arithmetik aus. Der- `+` Operator verwendet den-Konstruktor, um normalisierte Werte zu generieren.  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 Sie können die Struktur `height` mit dem folgenden Code testen.  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)
- [Vorgehensweise: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Vorgehensweise: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Structure Statement](../../../language-reference/statements/structure-statement.md)
- [Vorgehensweise: Deklarieren einer Struktur](../data-types/how-to-declare-a-structure.md)
- [Operator Mod](../../../language-reference/operators/mod-operator.md)
