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
ms.openlocfilehash: 3939d05b74dc6b9d79cae8307f5c5c736a1917d5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968269"
---
# <a name="type-list-visual-basic"></a>Typenliste (Visual Basic)
Gibt an, die *Typparameter* für eine *generische* Programmierelement. Mehrere Parameter werden durch Kommas getrennt. Es folgt die Syntax für einen Typ-Parameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`genericmodifier`|Dies ist optional. Kann nur in generischen Schnittstellen und Delegaten verwendet werden. Sie können einen Typ als Kovariante deklarieren, mit der [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) -Schlüsselwort oder kontravariant mithilfe der [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) Schlüsselwort. Siehe [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).|  
|`typename`|Erforderlich. Der Name des Typparameters. Dies ist ein Platzhalter, durch das entsprechende Typargument vom definierten Typ ersetzt werden.|  
|`constraintlist`|Dies ist optional. Liste der Anforderungen, die den Datentyp, der für angegeben werden können, einschränken `typename`. Wenn Sie mehrere Einschränkungen verfügen, schließen Sie sie in geschweifte Klammern (`{ }`), und trennen Sie diese durch Kommas. Führen Sie die Einschränkungsliste mit dem [als](../../../visual-basic/language-reference/statements/as-clause.md) Schlüsselwort. Verwenden Sie `As` nur einmal am Anfang der Liste.|  
  
## <a name="remarks"></a>Hinweise  
 Jedes generische Programmierelement muss mindestens einen Typparameter ausführen. Ein Typparameter ist ein Platzhalter für einen bestimmten Typ (ein *konstruierte Element*), dass Clientcode gibt an, wenn sie eine Instanz des generischen Typs erstellt. Definieren Sie eine generische Klasse kann, Struktur, Schnittstelle, Prozedur oder delegieren.  
  
 Weitere Informationen dazu, wann Sie einen generischen Typ definieren, finden Sie unter [generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md). Weitere Informationen zu Typparameternamen, finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Klammern.** Wenn Sie eine Liste der Parameter angeben, Sie es in Klammern einschließen müssen und führen Sie die Liste mit den [von](../../../visual-basic/language-reference/statements/of-clause.md) Schlüsselwort. Verwenden Sie `Of` nur einmal am Anfang der Liste.  
  
-   **Einschränkungen.** Eine Liste der *Einschränkungen* für einen Parameter die folgenden Elemente in beliebiger Kombination enthalten kann:  
  
    -   Eine beliebige Anzahl von Schnittstellen. Der angegebene Typ muss jeder Schnittstelle in der Liste implementieren.  
  
    -   Höchstens eine Klasse. Der angegebene Typ muss von dieser Klasse erben.  
  
    -   Das `New`-Schlüsselwort. Der angegebene Typ muss einen parameterlosen Konstruktor verfügbar machen, den der generische Typ zugreifen können. Dies ist hilfreich, wenn Sie einen Typparameter durch eine oder mehrere Schnittstellen einschränken. Ein Typ, der Schnittstellen implementiert ist nicht unbedingt einen Konstruktor verfügbar machen, und abhängig von die Zugriffsebene eines Konstruktors, der Code in den generischen Typ möglicherweise nicht darauf zugreifen können.  
  
    -   Entweder die `Class` Schlüsselwort oder `Structure` Schlüsselwort. Die `Class` -Schlüsselwort schränkt einen generischen Typparameter erforderlich ist, dass jedes Typargument übergeben, einen Verweistyp handelt, z. B. eine Zeichenfolge, Array oder Delegaten werden oder ein Objekt aus einer Klasse erstellt. Die `Structure` Schlüsselwort schränkt einen generischen Parameter anfordern, dass alle an sie übergebene Typargument ein Werttyp, ist beispielsweise eine Struktur, Enumeration oder elementarer Datentyp. Dürfen nicht zusammen `Class` und `Structure` in der gleichen `constraintlist`.  
  
     Der angegebene Typ muss jeder Anforderung, die Sie in einschließen genügen `constraintlist`.  
  
     Einschränkungen für jeden Typparameter sind unabhängig von Einschränkungen für andere Type-Parameter.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Während der Kompilierung Ersetzung.** Wenn Sie einen konstruierten Typ aus einer generischen Programmierelements erstellen, geben Sie keinen definierten Typ für jeden Typparameter an. Visual Basic-Compiler ersetzt diesen angegebenen Typ für jedes Vorkommen des `typename` innerhalb des generischen Elements.  
  
-   **Die Abwesenheit von Einschränkungen.** Wenn Sie keine Einschränkungen für einen Typparameter angeben, ist Ihr Code die Operationen und Member, die von unterstützt werden auf die [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) für den Typparameter.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die rumpfdefinition einer generischen Wörterbuch-Klasse, einschließlich eine Skelette-Funktion um einen neuen Eintrag zum Wörterbuch hinzuzufügen.  
  
 [!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Da `dictionary` ist generisch ist, der Code, der verwendet wird kann eine Vielzahl von Objekten aus erstellen, jeweils die gleiche Funktionalität müssen jedoch, die auf einen anderen Datentyp. Das folgende Beispiel zeigt eine einzige Zeile Code, der erstellt eine `dictionary` Objekt mit `String` Einträge und `Integer` Schlüssel.  
  
 [!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die entsprechende rumpfdefinition, die im vorherigen Beispiel generiert.  
  
 [!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch
- [Of](../../../visual-basic/language-reference/statements/of-clause.md)
- [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md)
- [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Vorgehensweise: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
