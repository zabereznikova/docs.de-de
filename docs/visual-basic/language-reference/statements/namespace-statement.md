---
title: Namespace-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9863286a8eda2559ab678c77a81cc7d6063c3e3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-statement"></a>Namespace-Anweisung
Der Name eines Namespace deklariert und bewirkt, dass den Quellcode, der die Deklaration in diesem Namespace kompiliert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a>Teile  
 Global  
 Dies ist optional. Können Sie einen Namespace aus der Stammnamespace des Projekts definieren. Finden Sie unter [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 `name`  
 Erforderlich. Ein eindeutiger Name, der den Namespace identifiziert. Ein gültiger Visual Basic-Bezeichner muss sein. Weitere Informationen finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `componenttypes`  
 Dies ist optional. Elemente, die den Namespace bilden. Diese umfassen, aber Sie sind nicht darauf beschränkt, Strukturen, Schnittstellen, Klassen, Module, Delegaten, Enumerationen und andere Namespaces.  
  
 `End Namespace`  
 Beendet eine `Namespace` Block.  
  
## <a name="remarks"></a>Hinweise  
 Namespaces werden als ein Organisations-System verwendet. Sie bieten eine Möglichkeit zum Klassifizieren und Präsentieren von Programmierelementen, die für andere Programme und Anwendungen verfügbar gemacht werden. Beachten Sie, dass ein Namespace keine *Typ* in dem Sinne, dass eine Klasse oder Struktur ist – ein Programmierelement haben Sie den Datentyp eines Namespace kann nicht deklariert werden.  
  
 Alle Programmierelemente deklariert wird, nach einem `Namespace` Anweisung zu diesem Namespace gehören. Visual Basic kompilieren Sie Elemente in den zuletzt deklarierten Namespace, bis er entweder trifft weiterhin ein `End Namespace` -Anweisung oder eine andere `Namespace` Anweisung.  
  
 Wenn ein Namespace bereits, auch außerhalb des Projekts definiert ist können Sie Programmierelemente hinzufügen. Zu diesem Zweck verwenden Sie eine `Namespace` Anweisung, damit Visual Basic können Sie Elemente in diesem Namespace zu kompilieren.  
  
 Sie können eine `Namespace` Anweisung nur auf der Namespace- oder Dateiebene. Dies bedeutet, dass die *Deklarationskontext* für ein Namespace muss eine Quelldatei oder einen anderen Namespace, und eine Klasse, Struktur, Modul, Schnittstelle oder Prozedur nicht möglich. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Sie können mehrere Namespaces innerhalb einer anderen deklarieren. Es ist keine flexiblen Grenzwert, der Schachtelungsebenen deklarieren, aber beachten Sie, dass wenn anderer Code, die im innersten Namespace deklarierten Elemente zugreift, muss ein Qualifizierungspfad verwendet werden, die die Namespacenamen in der Schachtelungshierarchie enthält.  
  
## <a name="access-level"></a>Zugriffsebene  
 Namespaces werden behandelt, als hätten sie eine `Public` Zugriffsebene. Ein Namespace kann zugegriffen werden, aus Code an einer beliebigen Stelle im selben Projekt als andere Projekte, die auf das Projekt zu verweisen und von einer Assembly aus dem Projekt erstellt.  
  
 Programmierelemente, die auf Namespace-Ebene, d. h. in einem Namespace, jedoch in keinem anderen Element deklariert haben `Public` oder `Friend` Zugriff. Falls nicht angegeben, verwendet die Zugriffsebene wie ein Element `Friend` standardmäßig. Elemente, die Sie auf Namespaceebene deklarieren können beinhalten Klassen, Strukturen, Modulen, Schnittstellen, Enumerationen und Delegaten. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
## <a name="root-namespace"></a>Stamm-Namespace  
 Alle Namespacenamen im Projekt basieren auf einer *Stammnamespace*. Visual Studio weist den Projektnamen als den Standard-Stammnamespace für den gesamten Code des Projekts zu. Wenn Ihr Projekt beispielsweise den Namen `Payroll` hat, gehören die Programmierelemente zum Namespace `Payroll`. Wenn Sie deklarieren `Namespace funding`, ist der vollständige Name des Namespaces `Payroll.funding`.  
  
 Wenn Sie einen vorhandenen Namespace im angeben möchten, eine `Namespace` -Anweisung, wie im Beispiel für die generische Liste, den Stammnamespace auf einen null-Wert festgelegt werden können. Klicken Sie hierzu auf **Projekteigenschaften** aus der **Projekt** Menü- und deaktivieren Sie dann die **Stammnamespace** Eintrag so, dass das Feld leer ist. Wenn Sie dies im Beispiel für die generische Liste nicht, würde der Visual Basic-Compiler `System.Collections.Generic` als einen neuen Namespace im Projekt `Payroll`, mit dem vollständigen Namen des `Payroll.System.Collections.Generic`.  
  
 Alternativ können Sie die `Global` Schlüsselwort verweisen auf Elemente des Namespaces, die außerhalb des Projekts definiert. Auf diese Weise können Sie den Projektnamen als Stammnamespace beibehalten werden sollen. Dies reduziert die Wahrscheinlichkeit, dass versehentlich von Programmierelementen zusammen mit den vorhandenen Namespaces zusammengeführt. Weitere Informationen finden Sie im Abschnitt "Global-Schlüsselwort in vollständig qualifizierte Namen" [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 Die `Global` -Schlüsselwort kann auch in einem Namespace-Anweisung verwendet werden. Dadurch können Sie einen Namespace aus dem Stammnamespace des Projekts definieren. Weitere Informationen finden Sie im Abschnitt "Global-Schlüsselwort im Namespace-Anweisungen" [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 **Problembehandlung bei.** Der Stammnamespace kann zu unerwarteten Verkettungen Namespacenamen führen. Wenn Sie den Verweis auf die Namespaces, die außerhalb des Projekts definiert vornehmen, können sie Visual Basic-Compiler als geschachtelte Namespaces im Stammnamespace construe. In diesem Fall erkennt der Compiler keine Typen, die bereits in den externen Namespaces definiert wurden. Um dies zu vermeiden, legen Sie den Stammnamespace auf einen null-Wert in "Stamm-Namespace" erläuterten oder verwenden Sie die `Global` Schlüsselwort, um Zugriff auf Elemente des externen Namespaces.  
  
## <a name="attributes-and-modifiers"></a>Attribute und -Modifizierern  
 Attribute können nicht mit einem Namespace angewendet werden. Ein Attribut trägt dazu bei Informationen zu den Metadaten der Assembly, die hat keine Bedeutung für Quelle Klassifizierern wie Namespaces.  
  
 Zugriff oder Prozedurmodifizierer oder andere Modifizierer, kann nicht mit einem Namespace angewendet werden. Da es sich nicht um einen Typ handelt, sind diese Modifizierer nicht aussagekräftig.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert zwei Namespaces, die in einer anderen geschachtelten.  
  
 [!code-vb[VbVbalrStatements#43](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert mehrere geschachtelte Namespaces in einer einzelnen Zeile ein, und dies ist äquivalent zum vorherigen Beispiel.  
  
 [!code-vb[VbVbalrStatements#41](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel greift auf die Klasse, die in den vorherigen Beispielen definiert.  
  
 [!code-vb[VbVbalrStatements#42](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel definiert das Skeleton des einen neuen generischen List-Klasse und fügt es der <xref:System.Collections.Generic?displayProperty=nameWithType> Namespace.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
