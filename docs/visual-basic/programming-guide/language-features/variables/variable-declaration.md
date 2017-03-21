---
title: Variablendeklaration in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables, declarations
- Dim statement, variable declaration
- declaring variables
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime, variables
- variables [Visual Basic], lifetime
- access levels, variables
- scope, declaration statements
- variables [Visual Basic], access level
- local variables, declarations
- scope, variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8cabb2d319288653c80099c816e46e822429d6ec
ms.lasthandoff: 03/13/2017

---
# <a name="variable-declaration-in-visual-basic"></a>Variablendeklaration in Visual Basic
Sie deklarieren eine Variable, die den Namen und die Eigenschaften angeben. Die deklarationsanweisung für Variablen ist der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md). Bestimmen den Speicherort und den Inhalt Merkmale der Variablen.  
  
 Regeln für Variablennamen und Überlegungen finden Sie unter [Elementnamen deklariert](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Deklaration von Ebenen  
  
### <a name="local-and-member-variables"></a>Lokale und Membervariablen  
 Ein *lokale Variable* wird innerhalb einer Prozedur deklariert wird. Ein *Membervariable* ist ein Mitglied einer [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] eingeben; er wird auf Modulebene in einer Klasse, Struktur oder Modul, aber nicht innerhalb einer Prozedur, die für diese Klasse, Struktur oder Modul intern deklariert.  
  
### <a name="shared-and-instance-variables"></a>Freigegebene und Instanzvariablen  
 Die Kategorie einer Membervariable hängt in einer Klasse oder Struktur davon, ob sie freigegeben werden. Deklarierte mit der [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) -Schlüsselwort, es ist ein *freigegebene Variable*, und eine Kopie von allen Instanzen der Klasse oder Struktur gemeinsam genutztes.  
  
 Andernfalls ist es eine *Instanzvariable*, und eine separate Kopie für jede Instanz der Klasse oder Struktur erstellt wird. Eine solche Kopie einer Instanzvariablen steht nur für die Instanz der Klasse oder Struktur, in der sie erstellt wurde. Sie ist unabhängig von der eine Kopie der Instanzvariablen in einer anderen Instanz der Klasse oder Struktur.  
  
## <a name="declaring-data-type"></a>Deklarieren von-Datentyp  
 Die [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel in der deklarationsanweisung können Sie den Datentyp oder Objekttyp der deklarieren Sie Variablen definieren. Sie können einen der folgenden Typen für eine Variable angeben:  
  
-   Ein elementarer Datentyp, z. B. `Boolean`, `Long`, oder`Decimal`  
  
-   Ein zusammengesetzter Datentyp, z. B. ein Array oder eine Struktur  
  
-   Ein Objekttyp oder eine Klasse, die in der Anwendung oder in einer anderen Anwendung definiert  
  
-   Ein [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Klasse, z. B. <xref:System.Windows.Forms.Label>oder <xref:System.Windows.Forms.TextBox></xref:System.Windows.Forms.TextBox> </xref:System.Windows.Forms.Label>  
  
-   Geben Sie eine Schnittstelle, wie z. B. <xref:System.IComparable>oder <xref:System.IDisposable></xref:System.IDisposable> </xref:System.IComparable>  
  
 Sie können mehrere Variablen in einer Anweisung deklarieren, ohne den Datentyp wiederholen zu müssen. In den folgenden Anweisungen, die Variablen `i`, `j`, und `k` werden als Typ deklariert `Integer`, `l` und `m` als `Long`, und `x` und `y` als `Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Weitere Informationen zu Datentypen finden Sie unter [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Weitere Informationen zu Objekten finden Sie unter [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) und [Programmieren mit Komponenten](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).  
  
## <a name="local-type-inference"></a>Lokaler Typrückschluss  
 *Typrückschluss* ermittelt, die die Datentypen für lokale Variablen, die ohne eine `As` Klausel. Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungsausdrucks ab. Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben. Im folgenden Beispiel beide `num1` und `num2` sind stark typisiert als ganze Zahlen.  
  
 [!code-vb[VbVbalrTypeInference&#1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 Wenn Sie lokalen Typrückschluss verwenden möchten `Option Infer` muss festgelegt werden, um `On`. Weitere Informationen finden Sie unter [lokalen Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) und [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## <a name="characteristics-of-declared-variables"></a>Merkmale der deklarierten Variablen  
 Die *Lebensdauer* einer Variablen ist der Zeitraum der sie verwendet werden kann. Im Allgemeinen existiert eine Variable, solange das Element, das es (z. B. eine Prozedur oder Klasse) deklariert weiterhin vorhanden ist. Wenn die Variable nicht bestehen bleiben nach Ablauf der Lebensdauer des enthaltenden Elements muss, müssen Sie nicht lediglich in der Deklaration. Wenn die Variable länger als ihr enthaltendes Element bestehen bleiben muss, können Sie enthalten die `Static` oder `Shared` -Schlüsselwort in der `Dim` Anweisung. Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 Die *Bereich* einer Variablen ist ein Satz von Code, die darauf verweisen kann, ohne dessen Namen zu qualifizieren. Der Gültigkeitsbereich einer Variablen wird bestimmt, wo sie deklariert ist. Code befindet sich in einer bestimmten Region können die Variablen, die in diesem Bereich definiert werden, ohne ihren Namen zu qualifizieren. Weitere Informationen finden Sie unter [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 Einer Variablentyps *Zugriffsebene* wird das Ausmaß der Code die Berechtigung zum Zugriff darauf hat. Dies richtet sich nach den Zugriffsmodifizierer (wie z. B. [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) oder [Private](../../../../visual-basic/language-reference/modifiers/private.md)), mit denen Sie der `Dim` Anweisung. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Erstellen einer neuen Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)   
 [Gewusst wie: Verschieben von Daten in und aus einer Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Geschützte](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Statische](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
