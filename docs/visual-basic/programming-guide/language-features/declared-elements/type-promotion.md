---
title: Typerweiterung
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
ms.openlocfilehash: aa05bd7dc87510aedb0facadf4b7590c8ec57d1f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345276"
---
# <a name="type-promotion-visual-basic"></a>Typerweiterung (Visual Basic)
Wenn Sie ein Programmier Element in einem Modul deklarieren, Visual Basic den Bereich auf den Namespace herauf Stufen, der das Modul enthält. Dies wird als *Typerweiterung*bezeichnet.  
  
 Das folgende Beispiel zeigt eine Skelett Definition eines Moduls und zwei Member dieses Moduls.  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 Innerhalb `projModule`werden Programmier Elemente, die auf Modulebene deklariert werden, zu `projNamespace`herauf gestuft. Im vorherigen Beispiel werden `basicEnum` und `innerClass` herauf gestuft, aber `numberSub` ist nicht, da es nicht auf Modulebene deklariert ist.  
  
## <a name="effect-of-type-promotion"></a>Auswirkung der Typerweiterung  
 Die Auswirkung der Typerweiterung besteht darin, dass eine Qualifizierungs Zeichenfolge nicht den Modulnamen enthalten muss. Im folgenden Beispiel werden zwei Aufrufe der Prozedur im vorherigen Beispiel durchführt.  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 Im vorherigen Beispiel verwendet der erste-Befehl komplette Qualifizierungs Zeichenfolgen. Dies ist jedoch aufgrund der typherauf Stufung nicht erforderlich. Der zweite-Befehl greift auch auf die Member des Moduls zu, ohne `projModule` in die Qualifizierungs Zeichenfolgen einzubeziehen.  
  
## <a name="defeat-of-type-promotion"></a>Bekämpfung der herauf Stufung von Typen  
 Wenn der Namespace bereits einen Member mit demselben Namen wie ein Modulmember hat, wird die Typerweiterung für dieses Modulmember unterstrichen. Das folgende Beispiel zeigt eine Gerüst Definition einer Enumeration und eines Moduls innerhalb desselben Namespace.  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 Im vorherigen Beispiel können Visual Basic die Klasse `abc` nicht auf `thisNameSpace` herauf Stufen, weil bereits eine Enumeration mit dem gleichen Namen auf der Namespace Ebene vorhanden ist. Um auf `abcSub`zuzugreifen, müssen Sie die vollständige Qualifizierungs Zeichenfolge `thisNamespace.thisModule.abc.abcSub`verwenden. Klassen `xyz` werden jedoch immer noch herauf gestuft, und Sie können mit der kürzeren Qualifizierungs Zeichenfolge `thisNamespace.xyz.xyzSub`auf `xyzSub` zugreifen.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Die unter Stufung der herauf Stufung von Typen für partielle Typen  
 Wenn eine Klasse oder Struktur innerhalb eines Moduls das [partielle](../../../../visual-basic/language-reference/modifiers/partial.md) Schlüsselwort verwendet, wird die Typerweiterung für diese Klasse oder Struktur automatisch unterstrichen, unabhängig davon, ob der Namespace über einen Member mit demselben Namen verfügt. Andere Elemente im Modul sind immer noch für die Typerweiterung geeignet.  
  
 **Konsequenzen.** Die unter Folge einer typherauf Stufung einer partiellen Definition kann unerwartete Ergebnisse und sogar Compilerfehler verursachen. Im folgenden Beispiel werden Skeleton partielle Definitionen einer-Klasse veranschaulicht, von denen eine innerhalb eines Moduls ist.  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 Im vorherigen Beispiel erwartet der Entwickler möglicherweise, dass der Compiler die beiden partiellen Definitionen von `sampleClass`zusammenführen kann. Der Compiler kann jedoch die herauf Stufung der partiellen Definition nicht innerhalb `sampleModule`in Erwägung gezogen. Daher wird versucht, zwei separate und unterschiedliche Klassen zu kompilieren, beide mit dem Namen `sampleClass`, aber mit unterschiedlichen Qualifizierungs Pfaden.  
  
 Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.  
  
## <a name="recommendations"></a>Empfehlungen  
 Die folgenden Empfehlungen stellen eine gute Programmierpraxis dar.  
  
- **Eindeutige Namen.** Wenn Sie die vollständige Kontrolle über die Benennung von Programmier Elementen haben, empfiehlt es sich immer, eindeutige Namen überall zu verwenden. Identische Namen erfordern eine zusätzliche Qualifizierung und können dazu führen, dass Ihr Code schwieriger zu lesen ist. Sie können auch zu geringfügigen Fehlern und unerwarteten Ergebnissen führen.  
  
- **Vollständige Qualifizierung.** Wenn Sie mit Modulen und anderen Elementen im gleichen Namespace arbeiten, besteht der sicherste Ansatz darin, stets die vollständige Qualifikation für alle Programmier Elemente zu verwenden. Wenn die Typerweiterung für ein Modulmember besiegt wird und Sie diesen Member nicht vollständig qualifizieren, können Sie versehentlich auf ein anderes Programmier Element zugreifen.  
  
## <a name="see-also"></a>Siehe auch

- [Module-Anweisung](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Bereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
