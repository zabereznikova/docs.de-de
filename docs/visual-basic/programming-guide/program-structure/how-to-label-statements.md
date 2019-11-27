---
title: 'Gewusst wie: Bezeichnen von Anweisungen'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: be116ac8046c43e89e44c2d9127c6131e4dfaa52
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347382"
---
# <a name="how-to-label-statements-visual-basic"></a>Gewusst wie: Label-Anweisungen (Visual Basic)

Anweisungsblöcke bestehen aus Codezeilen, die durch Doppelpunkte getrennt sind. Codezeilen, denen eine identifizierende Zeichenfolge oder eine ganze Zahl vorangestellt ist, werden *als bezeichnet*. Mithilfe von Anweisungs Bezeichnungen wird eine Codezeile gekennzeichnet, um Sie für die Verwendung mit Anweisungen wie `On Error Goto`zu kennzeichnen.

Bezeichnungen können entweder gültige Visual Basic Bezeichner sein – z. b. diejenigen, die Programmier Elemente identifizieren – oder ganzzahlige Literale. Eine Bezeichnung muss am Anfang einer Zeile des Quellcodes vorhanden sein, und es muss ein Doppelpunkt folgen, unabhängig davon, ob auf Sie eine-Anweisung in derselben Zeile folgt.

Der Compiler identifiziert Bezeichnungen, indem er überprüft, ob der Anfang der Zeile mit einem bereits definierten Bezeichner übereinstimmt. Andernfalls geht der Compiler davon aus, dass es sich um eine Bezeichnung handelt.

Bezeichnungen verfügen über einen eigenen Deklarations Bereich und stören andere Bezeichner nicht. Der Gültigkeitsbereich einer Bezeichnung ist der Text der Methode. Die Bezeichnungs Deklaration hat in jeder mehrdeutigen Situation Vorrang.

> [!NOTE]
> Bezeichnungen können nur für ausführbare Anweisungen innerhalb von Methoden verwendet werden.

## <a name="to-label-a-line-of-code"></a>So bezeichnen Sie eine Codezeile

Platzieren Sie einen Bezeichner, gefolgt von einem Doppelpunkt, am Anfang der Zeile des Quellcodes.

Die folgenden Codezeilen werden z. b. mit `Jump` bzw. `120`bezeichnet:

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a>Siehe auch

- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
- [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
