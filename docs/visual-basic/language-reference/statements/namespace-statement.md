---
title: Namespace-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
ms.openlocfilehash: 7f6b976af7933b3895f6992488d2d1532a8fc2f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784136"
---
# <a name="namespace-statement"></a>Namespace-Anweisung
Der Name eines Namespace deklariert und bewirkt, dass den Quellcode, der die Deklaration innerhalb dieses Namespace kompiliert werden.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a>Teile  
 Global  
 Dies ist optional. Können Sie einen Namespace aus dem Stammnamespace des Projekts definieren. Finden Sie unter [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 `name`  
 Erforderlich. Ein eindeutiger Name, der den Namespace identifiziert. Ein gültiger Visual Basic-Bezeichner muss sein. Weitere Informationen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `componenttypes`  
 Dies ist optional. Elemente, die den Namespace bilden. Diese umfassen, aber Sie sind nicht begrenzt, Enumerationen, Strukturen, Schnittstellen, Klassen, Module, Delegaten und andere Namespaces.  
  
 `End Namespace`  
 Beendet eine `Namespace` Block.  
  
## <a name="remarks"></a>Hinweise  
 Namespaces werden als Organisation System verwendet. Sie bieten eine Möglichkeit zum Klassifizieren und präsentieren Programmierelemente, die in anderen Programmen und Anwendungen verfügbar gemacht werden. Beachten Sie, dass ein Namespace keine *Typ* in dem Sinne, dass eine Klasse oder Struktur ist – ein Programmierelement, haben den Datentyp eines Namespace kann nicht deklariert werden.  
  
 Alle Programmierelemente, die danach deklariert eine `Namespace` Anweisung gehören zu diesem Namespace. Visual Basic wird fortgesetzt, kompiliert Sie Elemente in den letzten deklarierten Namespace, bis er entweder trifft eine `End Namespace` -Anweisung oder einer anderen `Namespace` Anweisung.  
  
 Wenn ein Namespace bereits, auch außerhalb des Projekts definiert ist, können Sie Programmierelemente, hinzufügen. Zu diesem Zweck verwenden Sie eine `Namespace` Anweisung, damit Visual Basic Elemente in diesem Namespace kompiliert.  
  
 Sie können eine `Namespace` Anweisung nur auf die Datei oder der Namespace-Ebene. Dies bedeutet, dass die *Deklarationskontext* für ein Namespace, eine Quelldatei oder einem anderen Namespace sein muss, und eine Klasse, Struktur, Modul, Schnittstelle oder Prozedur nicht möglich. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Sie können einen Namespace in einer anderen deklarieren. Es gibt keine strenge Begrenzung der Schachtelungsebenen deklarieren, aber denken Sie daran, dass wenn anderer Code die Elemente in der innersten Namespace deklariert zugreift, muss ein Qualifizierungspfad verwendet werden, die die Namespacenamen in der Schachtelungshierarchie enthält.  
  
## <a name="access-level"></a>Zugriffsebene  
 Namespaces werden behandelt, als hätten sie eine `Public` Zugriffsebene. Ein Namespace kann zugegriffen werden, von Code an einer beliebigen Stelle im selben Projekt, aus anderen Projekten, die auf das Projekt zu verweisen und einer Assembly, die aus dem Projekt erstellt.  
  
 Programmierelemente, die auf Namespace-Ebene, d. h. in einem Namespace, jedoch nicht in ein anderes Element deklariert haben `Public` oder `Friend` Zugriff. Falls nicht angegeben, verwendet die Zugriffsebene wie ein Element `Friend` standardmäßig. Elemente, die Sie auf Namespaceebene deklarieren enthalten Klassen, Strukturen, Module, Schnittstellen, Enumerationen und Delegaten. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
## <a name="root-namespace"></a>Stamm-Namespace  
 Alle Namespacenamen in Ihrem Projekt basieren auf einer *Stammnamespace*. Visual Studio weist den Projektnamen als den Standard-Stammnamespace für den gesamten Code des Projekts zu. Wenn Ihr Projekt beispielsweise den Namen `Payroll`hat, gehören die Programmierelemente zum Namespace `Payroll`. Wenn Sie deklarieren `Namespace funding`, ist der vollständige Name dieses Namespace `Payroll.funding`.  
  
 Wenn Sie einen vorhandenen Namespace im angeben möchten einer `Namespace` -Anweisung, wie im Beispiel für die generische Liste, Sie Ihre Stamm-Namespace mit einem Nullwert festlegen können. Zu diesem Zweck klicken Sie auf **Projekteigenschaften** aus der **Projekt** Menü und deaktivieren Sie dann die **Stammnamespace** Eintrag so, dass das Feld leer ist. Visual Basic-Compiler würde dauern, wenn Sie dies im Beispiel für die generische Liste nicht, `System.Collections.Generic` als im Projekt einen neuen Namespace `Payroll`, durch den vollständigen Namen des `Payroll.System.Collections.Generic`.  
  
 Alternativ können Sie die `Global` Schlüsselwort zum Verweisen auf Elemente des Namespaces, die außerhalb des Projekts definiert. Auf diese Weise können Sie den Projektnamen als den Stammnamespace beibehalten. Dies reduziert die Wahrscheinlichkeit, dass versehentlich von Programmierelementen zusammen, mit denen des vorhandenen Namespaces zusammengeführt. Weitere Informationen finden Sie im Abschnitt "Global-Schlüsselwort in vollständig qualifizierten Namen" in [-Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 Die `Global` -Schlüsselwort kann auch in einer Namespace-Anweisung verwendet werden. Dadurch können Sie einen Namespace aus dem Stammnamespace des Projekts definieren. Weitere Informationen finden Sie im Abschnitt "Global-Schlüsselwort in Namespace-Anweisungen in [-Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 **Problembehandlung bei.** Der Stammnamespace kann zu unerwarteten Verkettungen von Namespace-Namen führen. Wenn Sie den Verweis auf die Namespaces, die außerhalb des Projekts definiert vornehmen, können sie Visual Basic-Compiler als geschachtelte Namespaces im Stammnamespace construe. In diesem Fall erkennt der Compiler keine Typen, die bereits in den externen Namespaces definiert wurden. Um dies zu vermeiden, legen Ihre Stamm-Namespace mit einem Nullwert wie beschrieben in "Namespace" Root ", oder Verwenden der `Global` Schlüsselwort, um Zugriff auf Elemente von externen Namespaces.  
  
## <a name="attributes-and-modifiers"></a>Attribute und Modifizierer  
 Sie können keine Attribute auf einen Namespace anwenden. Ein Attribut fügt Informationen an den Metadaten der Assembly, die hat keine Bedeutung für die Quelle von Klassifizierern wie z. B. Namespaces.  
  
 Zugriff oder Prozedurmodifizierer oder andere Modifizierer kann nicht mit einem Namespace angewendet werden. Da es sich nicht um einen Typ handelt, sind diese Modifizierer ohne Bedeutung.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert zwei in einer anderen geschachtelten Namespaces.  
  
 [!code-vb[VbVbalrStatements#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#43)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert mehrere geschachtelte Namespaces in einer einzelnen Zeile, und dies entspricht dem vorherigen Beispiel.  
  
 [!code-vb[VbVbalrStatements#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#41)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel greift auf die Klasse definiert, die in den vorherigen Beispielen.  
  
 [!code-vb[VbVbalrStatements#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#42)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Skelett einer neuen generischen List-Klasse definiert und fügt es der <xref:System.Collections.Generic?displayProperty=nameWithType> Namespace.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>Siehe auch

- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
