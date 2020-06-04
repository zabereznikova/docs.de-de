---
title: Variablendeklaration
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
ms.openlocfilehash: 587cb84faa09b686361c255c413ad852780b8971
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410295"
---
# <a name="variable-declaration-in-visual-basic"></a>Variablendeklaration in Visual Basic
Sie deklarieren eine Variable, um deren Namen und Merkmale anzugeben. Die Deklarations Anweisung für Variablen ist die [Dim-Anweisung](../../../language-reference/statements/dim-statement.md). Speicherort und Inhalt bestimmen die Merkmale der Variablen.  
  
 Informationen zu Variablen Benennungs Regeln und-Überlegungen finden Sie unter [deklarierte Element Namen](../declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Deklarations Stufen  
  
### <a name="local-and-member-variables"></a>Lokale Variablen und Element Variablen  
 Eine *lokale Variable* ist eine, die innerhalb einer Prozedur deklariert wird. Eine *Member-Variable* ist ein Member eines Visual Basic Typs. Sie wird auf Modulebene innerhalb einer Klasse, Struktur oder eines Moduls deklariert, jedoch nicht innerhalb einer Prozedur, die für diese Klasse, Struktur oder dieses Modul intern ist.  
  
### <a name="shared-and-instance-variables"></a>Freigegebene und Instanzvariablen  
 In einer Klasse oder Struktur ist die Kategorie einer Element Variablen davon abhängig, ob Sie freigegeben ist. Wenn Sie mit dem [Shared](../../../language-reference/modifiers/shared.md) -Schlüsselwort deklariert ist, handelt es sich um eine frei *gegebene Variable*, die in einer einzelnen Kopie vorhanden ist, die von allen Instanzen der Klasse oder Struktur gemeinsam genutzt wird.  
  
 Andernfalls handelt es sich um eine *Instanzvariable*, und für jede Instanz der Klasse oder Struktur wird eine separate Kopie davon erstellt. Eine bestimmte Kopie einer Instanzvariablen ist nur für die Instanz der Klasse oder Struktur verfügbar, in der Sie erstellt wurde. Es ist unabhängig von einer Kopie der Instanzvariablen in einer anderen Instanz der Klasse oder Struktur.  
  
## <a name="declaring-data-type"></a>Deklarierender Datentyp  
 Mit der [As](../../../language-reference/statements/as-clause.md) -Klausel in der Deklarations Anweisung können Sie den Datentyp oder Objekttyp der Variablen definieren, die Sie deklarieren. Sie können einen der folgenden Typen für eine Variable angeben:  
  
- Ein grundlegender Datentyp, z. b. `Boolean` , `Long` oder.`Decimal`  
  
- Ein zusammengesetzter Datentyp, z. b. ein Array oder eine Struktur.  
  
- Ein Objekttyp oder eine Klasse, die entweder in der Anwendung oder in einer anderen Anwendung definiert ist.  
  
- Eine .NET Framework Klasse, z. b. <xref:System.Windows.Forms.Label> oder.<xref:System.Windows.Forms.TextBox>  
  
- Ein Schnittstellentyp, z. b. <xref:System.IComparable> oder.<xref:System.IDisposable>  
  
 Sie können mehrere Variablen in einer Anweisung deklarieren, ohne den Datentyp wiederholen zu müssen. In den folgenden-Anweisungen werden die Variablen, `i` `j` und `k` als-Typ und als und als und `Integer` `l` als deklariert `m` `Long` `x` `y` `Single` :  
  
```vb  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Weitere Informationen zu-Datentypen finden Sie unter [Datentypen](../data-types/index.md). Weitere Informationen zu-Objekten finden Sie unter [Objekte und Klassen](../objects-and-classes/index.md) und [Programmieren mit-Komponenten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).  
  
## <a name="local-type-inference"></a>Lokaler Typrückschluss  
 Der *Typrückschluss* wird verwendet, um die Datentypen von lokalen Variablen zu bestimmen, die ohne-Klausel deklariert werden `As` . Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungs Ausdrucks ab. Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben. Im folgenden Beispiel werden sowohl als `num1` auch `num2` als ganze Zahlen stark typisiert.  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 Wenn Sie den lokalen Typrückschluss verwenden möchten, `Option Infer` muss auf festgelegt werden `On` . Weitere Informationen finden Sie unter [Local Type Inference (Lokaler Typrückschluss)](local-type-inference.md) und [Option Infer Statement (Option Infer-Anweisung)](../../../language-reference/statements/option-infer-statement.md).  
  
## <a name="characteristics-of-declared-variables"></a>Merkmale von deklarierten Variablen  
 Die *Lebensdauer* einer Variablen ist der Zeitraum, in dem Sie zur Verwendung verfügbar ist. Im Allgemeinen ist eine Variable vorhanden, solange das Element, das Sie deklariert (z. b. eine Prozedur oder eine Klasse), weiterhin vorhanden ist. Wenn die Variable nicht fortgesetzt werden muss, wenn Sie die Lebensdauer des enthaltenden Elements überschreitet, müssen Sie in der Deklaration nichts Besonderes tun. Wenn die Variable länger vorhanden sein muss als das enthaltende Element, können Sie das- `Static` Schlüsselwort oder das- `Shared` Schlüsselwort in seine- `Dim` Anweisung einschließen. Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../declared-elements/lifetime.md).  
  
 Der Gültigkeits *Bereich* einer Variablen ist der Satz des gesamten Codes, der darauf verweisen kann, ohne den Namen zu qualifizieren. Der Gültigkeitsbereich einer Variablen wird bestimmt, wo Sie deklariert ist. Code, der sich in einer bestimmten Region befindet, kann die Variablen verwenden, die in dieser Region definiert sind, ohne deren Namen qualifizieren zu müssen. Weitere Informationen finden Sie unter [Scope in Visual Basic](../declared-elements/scope.md).  
  
 Die *Zugriffsebene* einer Variablen ist der Umfang des Codes, der über die entsprechende Zugriffsberechtigung verfügt. Dies wird durch den Zugriffsmodifizierer (z. b. [öffentlich](../../../language-reference/modifiers/public.md) oder [Privat](../../../language-reference/modifiers/private.md)) bestimmt, den Sie in der- `Dim` Anweisung verwenden. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Erstellen einer neuen Variablen](how-to-create-a-new-variable.md)
- [Vorgehensweise: Verschieben von Daten in eine und aus einer Variablen](how-to-move-data-into-and-out-of-a-variable.md)
- [Datentypen](../../../language-reference/data-types/index.md)
- [Gebieten](../../../language-reference/modifiers/protected.md)
- [Kollegen](../../../language-reference/modifiers/friend.md)
- [Statisch](../../../language-reference/modifiers/static.md)
- [Merkmale deklarierter Elemente](../declared-elements/declared-element-characteristics.md)
- [Lokaler Typrückschluss](local-type-inference.md)
- [Option Infer-Anweisung](../../../language-reference/statements/option-infer-statement.md)
