---
title: Variablendeklaration in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: 699737ffbe0b136af8862931fadacec26772b928
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833281"
---
# <a name="variable-declaration-in-visual-basic"></a>Variablendeklaration in Visual Basic
Sie deklarieren eine Variable, die den Namen und Eigenschaften angeben. Die deklarationsanweisung für Variablen ist der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md). Bestimmen sein Speicherort und den Inhalt der Merkmale der Variablen.  
  
 Regeln für Variablennamen und Überlegungen finden Sie unter [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Deklaration von Ebenen  
  
### <a name="local-and-member-variables"></a>Lokale und Membervariablen  
 Ein *lokale Variable* wird innerhalb einer Prozedur deklariert wird. Ein *Membervariable* ist ein Mitglied einer Visual Basic-Typ; er wird auf Modulebene in einer Klasse, Struktur oder Modul, aber nicht innerhalb einer Prozedur, die für diese Klasse, Struktur oder Modul intern deklariert.  
  
### <a name="shared-and-instance-variables"></a>Freigegebene und Instanzvariablen  
 In einer Klasse oder Struktur hängt von die Kategorie einer Membervariablen gespeichert, und zwar unabhängig davon, ob er freigegeben ist. Wenn mit dem er deklariert wird die [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) -Schlüsselwort, es ist eine *freigegebene Variable*, und es in eine einzige Kopie von allen Instanzen der Klasse oder Struktur gemeinsam vorhanden ist.  
  
 Andernfalls ist es ein *Instanzvariable*, und für jede Instanz der Klasse oder Struktur wird eine separate Kopie erstellt. Eine bestimmte Kopie eine Instanzvariable steht nur für die Instanz der Klasse oder Struktur, die in der es erstellt wurde. Er ist unabhängig von einer Kopie der Instanzvariable in einer anderen Instanz der Klasse oder Struktur.  
  
## <a name="declaring-data-type"></a>Deklarieren von-Datentyp  
 Die [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel in der deklarationsanweisung können Sie den Datentyp oder der Objekttyp der deklarieren Sie Variablen zu definieren. Sie können einen der folgenden Typen für eine Variable angeben:  
  
-   Geben Sie ein elementarer Datentyp, z. B. `Boolean`, `Long`, oder `Decimal`  
  
-   Einen zusammengesetzten Datentyp, z. B. ein Array oder eine Struktur  
  
-   Ein Objekttyp oder die Klasse, die in Ihrer Anwendung oder in einer anderen Anwendung definiert wird  
  
-   Ein [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Klasse, z. B. <xref:System.Windows.Forms.Label> oder <xref:System.Windows.Forms.TextBox>  
  
-   Geben Sie eine Schnittstelle, z. B. <xref:System.IComparable> oder <xref:System.IDisposable>  
  
 Sie können mehrere Variablen in einer Anweisung deklarieren, ohne den Datentyp wiederholen zu müssen. In den folgenden Anweisungen, die Variablen `i`, `j`, und `k` als Typ deklariert sind `Integer`, `l` und `m` als `Long`, und `x` und `y` als `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Weitere Informationen zu Datentypen finden Sie unter [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Weitere Informationen zu Objekten finden Sie unter [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) und [Programmieren mit Komponenten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).  
  
## <a name="local-type-inference"></a>Lokaler Typrückschluss  
 *Typrückschluss* wird verwendet, um zu bestimmen, die die Datentypen für lokale Variablen deklariert, ohne eine `As` Klausel. Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungsausdrucks ab. Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben. Im folgenden Beispiel beide `num1` und `num2` sind stark typisiert, als ganze Zahlen.  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 Wenn Sie mithilfe des lokalen Typrückschlusses, möchten `Option Infer` muss festgelegt werden, um `On`. Weitere Informationen finden Sie unter [Local Type Inference (Lokaler Typrückschluss)](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) und [Option Infer Statement (Option Infer-Anweisung)](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## <a name="characteristics-of-declared-variables"></a>Merkmale der deklarierten Variablen  
 Die *Lebensdauer* einer Variablen ist der Zeitraum der sie verwendet werden kann. Im Allgemeinen ist eine Variable vorhanden, solange das Element, das ihn, (z. B. eine Prozedur oder die Zielklasse deklariert) ausgeführt wird, vorhanden sein. Wenn die Variable nicht weiter nach Ablauf der Lebensdauer von ihr enthaltendes Element vorhandenen muss, müssen Sie keine gar nichts Besonderes in der Deklaration. Wenn die Variable länger als ihr enthaltendes Element gespeichert bleiben muss, können Sie enthalten die `Static` oder `Shared` -Schlüsselwort in der `Dim` Anweisung. Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 Die *Bereich* einer Variablen ist die Menge des gesamten Codes, die darauf verweisen kann, ohne Angabe ihres Namens. Der Gültigkeitsbereich einer Variablen wird bestimmt, wo er deklariert wurde. Code befindet sich in einer bestimmten Region können die Variablen, die in dieser Region definiert werden, ohne ihren Namen zu qualifizieren. Weitere Informationen finden Sie unter [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Einer Variablentyps des *Zugriffsebene* wird das Ausmaß der Code mit der Berechtigung, darauf zuzugreifen. Dies richtet sich nach den Zugriffsmodifizierer (wie z. B. [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) oder [Private](../../../../visual-basic/language-reference/modifiers/private.md)), mit denen Sie der `Dim` Anweisung. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer neuen Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)
- [Vorgehensweise: Verschieben von Daten in und aus einer Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
- [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
