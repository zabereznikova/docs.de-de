---
title: Typerweiterung (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: 104fa906fecc5a5bb8704fe3ab839f9f200cf73b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="type-promotion-visual-basic"></a>Typerweiterung (Visual Basic)
Wenn Sie ein Programmierelement in einem Modul deklarieren, stuft Visual Basic den Gültigkeitsbereich auf den Namespace, die das Modul enthält. Dies bezeichnet man *heraufstufung geben*.  
  
 Das folgende Beispiel zeigt eine rumpfdefinition eines Moduls und zwei Member des Moduls.  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 In `projModule`Programmierelemente auf Modulebene deklarierten Elemente zu hochgestuft `projNamespace`. Im vorherigen Beispiel `basicEnum` und `innerClass` höher gestuft werden, aber `numberSub` ist nicht der Fall, da er nicht auf Modulebene deklariert ist.  
  
## <a name="effect-of-type-promotion"></a>Auswirkungen der Typerweiterung  
 Die Auswirkung der typerweiterung ist Qualifizierungspfad müssen nicht den Namen des Moduls enthalten. Das folgende Beispiel enthält zwei Aufrufe an die Prozedur im vorherigen Beispiel.  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 Im vorherigen Beispiel verwendet der erste Aufruf vollständige Qualifizierung-Zeichenfolgen. Allerdings ist dies nicht erforderlich aufgrund typerweiterung. Der zweite Aufruf auch greift auf die Member des Moduls ohne `projModule` in die Qualifizierung-Zeichenfolgen.  
  
## <a name="defeat-of-type-promotion"></a>Entschärfen der Typerweiterung  
 Wenn der Namespace bereits ein Element mit dem gleichen Namen wie ein Modul Element verfügt, ist typerweiterung wird für dieses Modul Element außer Kraft gesetzt. Im folgenden Beispiel wird die rumpfdefinition einer Enumeration und ein Modul innerhalb des gleichen Namespace.  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 Im vorherigen Beispiel Visual Basic keine Klasse hochstufen `abc` auf `thisNameSpace` weil bereits eine Enumeration mit dem gleichen Namen auf Namespaceebene vorhanden ist. Für den Zugriff auf `abcSub`, müssen Sie den vollständigen Qualifizierungspfad verwenden `thisNamespace.thisModule.abc.abcSub`. Allerdings-Klasse `xyz` noch höher gestuft, und Sie können den `xyzSub` mit den kürzeren Qualifizierungspfad `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Entschärfen der Typerweiterung für partielle Typen  
 Wenn eine Klasse oder Struktur innerhalb eines Moduls verwendet die [partielle](../../../../visual-basic/language-reference/modifiers/partial.md) Schlüsselwort typerweiterung ist für diese Klasse oder Struktur automatisch wird außer Kraft gesetzt, und zwar unabhängig davon, ob der Namespace ein Element mit dem gleichen Namen hat. Andere Elemente im Modul sind weiterhin für typerweiterung geeignet.  
  
 **Folgen.** Entschärfen von datentyphöherstufung der eine partielle Definition kann unerwartete Ergebnisse und sogar zu Compilerfehlern führen. Das folgende Beispiel zeigt das Gerüst eines partielle Definitionen einer Klasse, von denen innerhalb eines Moduls ist.  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 Im vorherigen Beispiel der Entwickler den Compiler an, die beiden partiellen Definitionen von merge erwarten kann `sampleClass`. Der Compiler berücksichtigt jedoch nicht Heraufstufen der partiellen Definition in `sampleModule`. Daher versucht er, zwei separate Klassen zu kompilieren, die beiden benannten `sampleClass` jedoch mit anderen Qualifizierung Pfade.  
  
 Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.  
  
## <a name="recommendations"></a>Empfehlungen  
 Die folgenden Empfehlungen darstellen gebräuchliche programmiergrundlagen.  
  
-   **Eindeutige Namen.** Wenn Sie vollständige Kontrolle über die Benennung von Programmierelementen haben, ist es immer ratsam, eindeutige Namen verwenden. Identische Namen erfordern zusätzliche Qualifizierung und können Ihr Code schwieriger zu lesen. Sie können auch geringfügige Fehler zu unerwarteten Ergebnissen führen.  
  
-   **Vollständige Qualifizierung.** Bei der Arbeit mit Modulen und andere Elemente im selben Namespace ist am sichersten, immer vollständige Qualifizierung für alle Programmierelemente verwendet wird. Wenn typhöherstufung für ein Modul-Element erfolgt, und Sie dieses Element nicht vollständig qualifiziert, konnte die ein anderes Programmierelements versehentlich zugegriffen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Module-Anweisung](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
