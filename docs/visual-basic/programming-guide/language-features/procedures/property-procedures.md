---
title: Eigenschaftenprozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: f3b57ae45815fbd91cad17cddbed4d01037eb92f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002085"
---
# <a name="property-procedures-visual-basic"></a>Eigenschaftenprozeduren (Visual Basic)
Eine Eigenschaften Prozedur ist eine Reihe von Visual Basic-Anweisungen, die eine benutzerdefinierte Eigenschaft für ein Modul, eine Klasse oder eine Struktur bearbeiten. Eigenschaften Prozeduren werden auch als *Eigenschaftenaccessoren*bezeichnet.  
  
 Visual Basic bietet die folgenden Eigenschaften Prozeduren:  
  
- Eine `Get`-Prozedur gibt den Wert einer Eigenschaft zurück. Sie wird aufgerufen, wenn Sie in einem Ausdruck auf die-Eigenschaft zugreifen.  
  
- Eine `Set`-Prozedur legt eine Eigenschaft auf einen Wert fest, einschließlich eines Objekt Verweises. Sie wird aufgerufen, wenn Sie der-Eigenschaft einen Wert zuweisen.  
  
 In der Regel definieren Sie Eigenschafts Prozeduren in Paaren, indem Sie die Anweisungen `Get` und `Set` verwenden. Sie können jedoch auch eine der beiden Prozeduren definieren, wenn die Eigenschaft schreibgeschützt ([Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md)) oder schreibgeschützt ([Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)) ist.  
  
 Wenn Sie eine automatisch implementierte Eigenschaft verwenden, können Sie die `Get`-und `Set`-Prozedur weglassen. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](./auto-implemented-properties.md).  
  
 Sie können Eigenschaften in Klassen, Strukturen und Modulen definieren. Eigenschaften sind standardmäßig `Public`. Dies bedeutet, dass Sie Sie von überall in Ihrer Anwendung aufrufen können, die auf den Container der Eigenschaft zugreifen können.  
  
 Einen Vergleich von Eigenschaften und Variablen finden Sie [unter Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md).  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Eine Eigenschaft selbst wird durch einen Codeblock definiert, der in der- [Eigenschafts Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md) und der `End Property`-Anweisung eingeschlossen ist. Innerhalb dieses Blocks erscheint jede Eigenschaften Prozedur als interner Block, der in einer Deklarations Anweisung (`Get` oder `Set`) und der entsprechenden `End`-Deklaration eingeschlossen ist.  
  
 Die Syntax zum Deklarieren einer Eigenschaft und ihrer Prozeduren lautet wie folgt:  
  
```vb  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 Mit dem `Modifiers` können Zugriffsebenen und Informationen zum überschreiben, überschreiben, freigeben und shadoading angegeben werden. Außerdem können Sie angeben, ob die Eigenschaft schreibgeschützt oder schreibgeschützt ist. Der `AccessLevel` für die `Get`-oder `Set`-Prozedur kann eine beliebige Ebene sein, die restriktiver ist als die für die Eigenschaft selbst angegebene Zugriffsebene. Weitere Informationen finden Sie unter [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### <a name="data-type"></a>Datentyp  
 Der Datentyp der Eigenschaft und die Prinzipal Zugriffsebene werden in der `Property`-Anweisung definiert, nicht in den Eigenschaften Prozeduren. Eine Eigenschaft kann nur einen Datentyp aufweisen. Beispielsweise können Sie keine Eigenschaft zum Speichern eines `Decimal`-Werts definieren, sondern einen `Double`-Wert abrufen.  
  
### <a name="access-level"></a>Zugriffsebene  
 Sie können jedoch eine Prinzipal Zugriffsebene für eine Eigenschaft definieren und die Zugriffsebene in einer der Eigenschaften Prozeduren weiter einschränken. Sie können z. b. eine `Public`-Eigenschaft definieren und dann eine `Private Set`-Prozedur definieren. Die `Get`-Prozedur bleibt `Public`. Sie können die Zugriffsebene nur in einer der Prozeduren einer Eigenschaft ändern, und Sie können Sie nur restriktiver machen als die Prinzipal Zugriffsebene. Weitere Informationen finden Sie unter [Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen @ no__t-0.  
  
## <a name="parameter-declaration"></a>Parameter Deklaration  
 Sie deklarieren jeden Parameter auf dieselbe Weise wie bei [unter Prozeduren](./sub-procedures.md), mit der Ausnahme, dass der Übergabe Mechanismus `ByVal` sein muss.  
  
 Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben. Die Syntax zum Angeben eines Standardwerts lautet wie folgt:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a>Eigenschaftswert  
 In einer `Get`-Prozedur wird der Rückgabewert für den aufrufenden Ausdruck als Wert der-Eigenschaft bereitgestellt.  
  
 In einer `Set`-Prozedur wird der neue Eigenschafts Wert an den-Parameter der `Set`-Anweisung übergeben. Wenn Sie explizit einen Parameter deklarieren, müssen Sie ihn mit dem gleichen Datentyp wie die-Eigenschaft deklarieren. Wenn Sie keinen Parameter deklarieren, verwendet der Compiler den impliziten Parameter `Value`, um den neuen Wert darzustellen, der der Eigenschaft zugewiesen werden soll.  
  
## <a name="calling-syntax"></a>Aufruf Syntax  
 Sie rufen eine Eigenschaften Prozedur implizit auf, indem Sie einen Verweis auf die-Eigenschaft erstellen. Sie verwenden den Namen der Eigenschaft auf die gleiche Weise wie den Namen einer Variablen, mit dem Unterschied, dass Sie Werte für alle nicht optionalen Argumente angeben müssen, und Sie müssen die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.  
  
 Die Syntax für einen impliziten Rückruf einer `Set`-Prozedur lautet wie folgt:  
  
 `propertyname[(argumentlist)] = expression`  
  
 Die Syntax für einen impliziten Rückruf einer `Get`-Prozedur lautet wie folgt:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und des Aufruf  
 Die folgende Eigenschaft speichert einen vollständigen Namen als zwei konstituierende Namen, den Vornamen und den Nachnamen. Wenn der aufrufenden Code `fullName` liest, werden die beiden konstituierenden Namen in der `Get`-Prozedur kombiniert, und der vollständige Name wird zurückgegeben. Wenn der Aufruf Code einen neuen vollständigen Namen zuweist, versucht die Prozedur "`Set`", Sie in zwei Bestandteile zu zerlegen. Wenn kein Leerzeichen gefunden wird, wird alles als Vorname gespeichert.  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 Das folgende Beispiel zeigt typische Aufrufe der-Eigenschaften Prozeduren von `fullName`.  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Function-Prozeduren](./function-procedures.md)
- [Operatorprozeduren](./operator-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)
- [Vorgehensweise: Create a Property @ no__t-0
- [Vorgehensweise: Eigenschaften Prozedur "@ no__t-0" aufzurufen
- [Vorgehensweise: Deklarieren und rufen Sie eine Default-Eigenschaft in Visual Basic @ no__t-0
- [Vorgehensweise: Wert in der Eigenschaft @ no__t-0 einfügen
- [Vorgehensweise: Einen Wert aus der Eigenschaft "@ no__t-0" erhalten
