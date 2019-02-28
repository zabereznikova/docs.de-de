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
ms.openlocfilehash: b00fdd563a6599b3acfaaafa229fdef9400e57b6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969192"
---
# <a name="type-promotion-visual-basic"></a>Typerweiterung (Visual Basic)
Wenn Sie ein Programmierelement ein Element in einem Modul deklarieren, stuft Visual Basic den Gültigkeitsbereich auf den Namespace, die das Modul. Dies bezeichnet man als *typerweiterung*.  
  
 Das folgende Beispiel zeigt eine rumpfdefinition eines Moduls und zwei Member des Moduls.  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 In `projModule`, Programmierung Elemente, die auf Modulebene deklariert werden höher gestuft `projNamespace`. Im vorherigen Beispiel `basicEnum` und `innerClass` höher gestuft werden, aber `numberSub` dagegen nicht, da er nicht auf Modulebene deklariert ist.  
  
## <a name="effect-of-type-promotion"></a>Auswirkungen der Typerweiterung  
 Die Auswirkungen der typerweiterung ist, dass ein Qualifizierungspfad nicht auf den Namen des Moduls. Im folgende Beispiel enthält zwei Aufrufe an die Prozedur im vorhergehenden Beispiel.  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 Im vorherigen Beispiel verwendet der erste Aufruf vollständige Qualifizierung-Zeichenfolgen. Jedoch muss dies nicht aufgrund der typerweiterung. Der zweite Aufruf auch greift auf die Elemente des Moduls ohne `projModule` in den Zeichenfolgen Qualifizierung.  
  
## <a name="defeat-of-type-promotion"></a>Entschärfen von Typerweiterung  
 Wenn der Namespace bereits einem Element mit dem gleichen Namen wie eine Modul-Element verfügt, ist die typerweiterung für diesen Modulmember außer Kraft gesetzt. Im folgenden Beispiel wird die rumpfdefinition einer Enumeration und ein Modul innerhalb eines Namespaces.  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 Im vorherigen Beispiel Visual Basic kann nicht heraufgestuft Klasse `abc` zu `thisNameSpace` da bereits eine Enumeration mit demselben Namen im Namespace-Ebene vorhanden ist. Für den Zugriff auf `abcSub`, müssen Sie den vollständigen Qualifizierungspfad verwenden `thisNamespace.thisModule.abc.abcSub`. Allerdings Klasse `xyz` weiterhin heraufgestuft, und Sie können den `xyzSub` mit den kürzeren Qualifizierungspfad `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Entschärfen von Typerweiterung für partielle Typen  
 Wenn eine Klasse oder Struktur in einem Modul verwendet die [teilweise](../../../../visual-basic/language-reference/modifiers/partial.md) Schlüsselwort typerweiterung ist automatisch für diese Klasse oder Struktur, außer Kraft gesetzt, und zwar unabhängig davon, ob der Namespace ein Element mit dem gleichen Namen hat. Andere Elemente im Modul sind immer noch die Gelegenheit für typerweiterung.  
  
 **Folgen.** Entschärfen von typerweiterung für eine partielle Definition kann es sich um unerwartete Ergebnisse und sogar zu Compilerfehlern führen. Im folgenden Beispiel wird das Skelett partiellen Definitionen einer Klasse, von denen innerhalb eines Moduls ist.  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 Im vorherigen Beispiel erwarten Entwickler den Compiler an, die beiden partiellen Definitionen von merge `sampleClass`. Der Compiler berücksichtigt jedoch keine Erweiterung der partiellen Definition in `sampleModule`. Daher versucht er, zwei separate Klassen zu kompilieren, sowohl für benannte `sampleClass` jedoch mit anderen Qualifizierung Pfade.  
  
 Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.  
  
## <a name="recommendations"></a>Empfehlungen  
 Die folgenden Empfehlungen stellen programmiergrundlagen dar.  
  
-   **Eindeutige Namen.** Wenn Sie vollständige Kontrolle über die Benennung von Programmierelementen verfügen, ist es immer eine gute Idee, eindeutige Namen verwenden. Identische Namen können erfordern zusätzliche Qualifizierung und Ihren Code schwieriger zu lesen. Sie können auch Fehler auftreten zu unerwarteten Ergebnissen führen.  
  
-   **Vollständige Qualifizierung.** Wenn Sie Module und andere Elemente im selben Namespace arbeiten, ist am sichersten, immer vollständige Qualifizierung für alle Programmiersprachen Elemente verwenden. Wenn typerweiterung für einen Modulmember außer Kraft gesetzt wird, und Sie diesen Member nicht vollständig qualifizieren, konnten Sie versehentlich ein anderes Programmierelements zugreifen.  
  
## <a name="see-also"></a>Siehe auch
- [Module-Anweisung](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
