---
title: Typenliste (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 5fbb07154fce27feb257b431c1726446b42fbfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="type-list-visual-basic"></a>Typenliste (Visual Basic)
Gibt an, die *Typparameter* für eine *generische* Programmierelement. Mehrere Parameter werden durch Kommas getrennt. Nachfolgend ist die Syntax für einen Typparameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`genericmodifier`|Dies ist optional. Kann nur in generischen Schnittstellen und Delegaten verwendet werden. Sie können einen Typ kovariant deklarieren, indem die [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) Schlüsselwort oder kontravariant mithilfe der [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) Schlüsselwort. Siehe [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).|  
|`typename`|Erforderlich. Der Name des Typparameters. Dies ist ein Platzhalter, durch einen definierten, durch das entsprechende Typargument bereitgestellten Typ ersetzt werden.|  
|`constraintlist`|Dies ist optional. Liste der Anforderungen, die den Datentyp zu beschränken, die für die angegeben werden können `typename`. Wenn Sie mehrere Einschränkungen verfügen, schließen Sie sie in geschweifte Klammern (`{ }`) und trennen Sie diese durch Kommas. Führen Sie die Einschränkungsliste mit dem [als](../../../visual-basic/language-reference/statements/as-clause.md) Schlüsselwort. Verwenden Sie `As` nur einmal am Anfang der Liste.|  
  
## <a name="remarks"></a>Hinweise  
 Jedes generische Programmierelement muss mindestens ein Typparameter akzeptieren. Ein Typparameter ist ein Platzhalter für einen bestimmten Typ (ein *konstruierte Element*), dass Clientcode gibt an, wenn er eine Instanz des generischen Typs erstellt. Sie können definieren Sie eine generische Klasse, Struktur, Schnittstelle, Prozedur, klicken oder delegieren.  
  
 Weitere Informationen dazu, wann einen generischen Typ definieren, finden Sie unter [generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Weitere Informationen zu Typparameternamen, finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Klammern.** Wenn Sie eine Typparameterliste angeben, Sie es in Klammern einschließen müssen und führen Sie die Liste mit den [von](../../../visual-basic/language-reference/statements/of-clause.md) Schlüsselwort. Verwenden Sie `Of` nur einmal am Anfang der Liste.  
  
-   **Einschränkungen.** Eine Liste der *Einschränkungen* für einen Parameter die folgenden Elemente in beliebiger Kombination enthalten:  
  
    -   Eine beliebige Anzahl von Schnittstellen. Der angegebene Typ muss in dieser Liste jede Schnittstelle implementieren.  
  
    -   Höchstens einer Klasse. Der angegebene Typ muss von dieser Klasse erben.  
  
    -   Das `New`-Schlüsselwort. Der angegebene Typ muss einen parameterlosen Konstruktor verfügbar machen, den der generische Typ zugreifen können. Dies ist hilfreich, wenn einen Typparameter durch eine oder mehrere Schnittstellen zu beschränken. Ein Typ, der Schnittstellen implementiert macht nicht unbedingt einen Konstruktor, und je nach den Zugriff für einen Konstruktor, der Code in den generischen Typ möglicherweise nicht darauf zugreifen.  
  
    -   Entweder die `Class` Schlüsselwort oder der `Structure` Schlüsselwort. Die `Class` -Schlüsselwort schränkt einen generischen Typparameter erforderlich ist, dass jedes übergebene Typargument ein Verweistyp, z. B. eine Zeichenfolge, Array oder Delegaten, oder ein Objekt aus einer Klasse erstellt. Die `Structure` -Schlüsselwort schränkt einen generischen Typparameter erforderlich ist, dass alle an sie übergebene Typargument ein Werttyp ist, werden z. B. eine Struktur, Enumeration oder ein elementarer Datentyp. Darf keine enthalten beide `Class` und `Structure` in der gleichen `constraintlist`.  
  
     Der angegebene Typ muss jede Anforderung, die Sie in einschließen erfüllen `constraintlist`.  
  
     Einschränkungen für jeden Typparameter sind unabhängig von Einschränkungen für andere Type-Parameter.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zeitpunkt der Kompilierung Ersetzung.** Wenn Sie einen konstruierten Typ aus einem generischen Programmierelements erstellen, geben Sie einen definierten Typ für jeden Typparameter. Visual Basic-Compiler ersetzt für jedes Vorkommen eines angegebenen Typs `typename` innerhalb des generischen Elements.  
  
-   **Falls keine Einschränkungen vorliegen.** Wenn Sie keine Einschränkungen für einen Typparameter angeben, wird Code beschränkt auf die Operationen und Member, die von unterstützt die [Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md) für den Typparameter.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die rumpfdefinition einer generischen Wörterbuch-Klasse, z. B. eine Skelette-Funktion um einen neuen Eintrag zum Wörterbuch hinzuzufügen.  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Da `dictionary` ist generisch ist, der Code, die verwendet werden kann eine Vielzahl von Objekten daraus erstellen, jeweils die gleiche Funktionalität ist jedoch auf einen anderen Datentyp fungiert. Das folgende Beispiel zeigt eine Codezeile erstellt eine `dictionary` -Objekt mit `String` Einträge und `Integer` Schlüssel.  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die entsprechende rumpfdefinition, die im vorherigen Beispiel generiert.  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
 [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md)  
 [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
