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
ms.openlocfilehash: 6c28ca22e96616ff09e147400bfdb2adb922ff0e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085801"
---
# <a name="type-promotion-visual-basic"></a>Typerweiterung (Visual Basic)

Wenn Sie ein Programmier Element in einem Modul deklarieren, Visual Basic den Bereich auf den Namespace herauf Stufen, der das Modul enthält. Dies wird als *Typerweiterung*bezeichnet.  
  
 Das folgende Beispiel zeigt eine Skelett Definition eines Moduls und zwei Member dieses Moduls.  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 In `projModule` werden Programmier Elemente, die auf Modulebene deklariert werden, zu herauf gestuft `projNamespace` . Im vorherigen Beispiel `basicEnum` werden und höher gestuft `innerClass` , aber `numberSub` nicht, da Sie nicht auf Modulebene deklariert werden.  
  
## <a name="effect-of-type-promotion"></a>Auswirkung der Typerweiterung  

 Die Auswirkung der Typerweiterung besteht darin, dass eine Qualifizierungs Zeichenfolge nicht den Modulnamen enthalten muss. Im folgenden Beispiel werden zwei Aufrufe der Prozedur im vorherigen Beispiel durchführt.  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 Im vorherigen Beispiel verwendet der erste-Befehl komplette Qualifizierungs Zeichenfolgen. Dies ist jedoch aufgrund der typherauf Stufung nicht erforderlich. Der zweite-Befehl greift auch auf die Member des Moduls zu, ohne in die Qualifizierungs Zeichenfolgen einzubeziehen `projModule` .  
  
## <a name="defeat-of-type-promotion"></a>Bekämpfung der herauf Stufung von Typen  

 Wenn der Namespace bereits einen Member mit demselben Namen wie ein Modulmember hat, wird die Typerweiterung für dieses Modulmember unterstrichen. Das folgende Beispiel zeigt eine Gerüst Definition einer Enumeration und eines Moduls innerhalb desselben Namespace.  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 Im vorherigen Beispiel kann Visual Basic die Klasse nicht auf herauf Stufen, `abc` `thisNameSpace` da bereits eine Enumeration mit dem gleichen Namen auf der Namespace Ebene vorhanden ist. Für den Zugriff auf `abcSub` müssen Sie die vollständige Qualifikations Zeichenfolge verwenden `thisNamespace.thisModule.abc.abcSub` . `xyz`Die Klasse wird jedoch immer noch herauf gestuft, und Sie können `xyzSub` mit der kürzeren Qualifizierungs Zeichenfolge auf zugreifen `thisNamespace.xyz.xyzSub` .  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Die unter Stufung der herauf Stufung von Typen für partielle Typen  

 Wenn eine Klasse oder Struktur innerhalb eines Moduls das [partielle](../../../language-reference/modifiers/partial.md) Schlüsselwort verwendet, wird die Typerweiterung für diese Klasse oder Struktur automatisch unterstrichen, unabhängig davon, ob der Namespace über einen Member mit demselben Namen verfügt. Andere Elemente im Modul sind immer noch für die Typerweiterung geeignet.  
  
 **Konsequenzen.** Die unter Folge einer typherauf Stufung einer partiellen Definition kann unerwartete Ergebnisse und sogar Compilerfehler verursachen. Im folgenden Beispiel werden Skeleton partielle Definitionen einer-Klasse veranschaulicht, von denen eine innerhalb eines Moduls ist.  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 Im vorherigen Beispiel erwartet der Entwickler möglicherweise, dass der Compiler die beiden partiellen Definitionen von zusammenführen kann `sampleClass` . Der Compiler kann jedoch die herauf Stufung der partiellen Definition nicht in in Erwägung gezogen `sampleModule` . Daher wird versucht, zwei separate und eindeutige Klassen zu kompilieren, die beide den Namen haben, `sampleClass` jedoch mit unterschiedlichen Qualifizierungs Pfaden.  
  
 Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.  
  
## <a name="recommendations"></a>Empfehlungen  

 Die folgenden Empfehlungen stellen eine gute Programmierpraxis dar.  
  
- **Eindeutige Namen.** Wenn Sie die vollständige Kontrolle über die Benennung von Programmier Elementen haben, empfiehlt es sich immer, eindeutige Namen überall zu verwenden. Identische Namen erfordern eine zusätzliche Qualifizierung und können dazu führen, dass Ihr Code schwieriger zu lesen ist. Sie können auch zu geringfügigen Fehlern und unerwarteten Ergebnissen führen.  
  
- **Vollständige Qualifizierung.** Wenn Sie mit Modulen und anderen Elementen im gleichen Namespace arbeiten, besteht der sicherste Ansatz darin, stets die vollständige Qualifikation für alle Programmier Elemente zu verwenden. Wenn die Typerweiterung für ein Modulmember besiegt wird und Sie diesen Member nicht vollständig qualifizieren, können Sie versehentlich auf ein anderes Programmier Element zugreifen.  
  
## <a name="see-also"></a>Siehe auch

- [Module-Anweisung](../../../language-reference/statements/module-statement.md)
- [Namespace-Anweisung](../../../language-reference/statements/namespace-statement.md)
- [Partial](../../../language-reference/modifiers/partial.md)
- [Gültigkeitsbereich in Visual Basic](scope.md)
- [Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen](how-to-control-the-scope-of-a-variable.md)
- [References to Declared Elements](references-to-declared-elements.md)
