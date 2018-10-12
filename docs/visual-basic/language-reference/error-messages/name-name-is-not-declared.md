---
title: Namen &#39; &lt;Namen&gt; &#39; ist nicht deklariert
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
author: rpetrusha
ms.author: ronpet
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 3f950bd5604fae7c7d48f6898a4514053061fe10
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49122801"
---
# <a name="name-39ltnamegt39-is-not-declared"></a>Namen &#39; &lt;Namen&gt; &#39; ist nicht deklariert
Eine Anweisung verweist auf ein Programmierelement, aber der Compiler kein Element mit genau diesem Namen gefunden.  
  
 **Fehler-ID:** BC30451  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung. Visual Basic ist die Groß-/Kleinschreibung, jedoch eine andere Variante der Schreibweise als einen ganz anderen Namen betrachtet wird. Beachten Sie, dass der Unterstrich (`_`) Teil des Namens und daher Teil der Schreibweise ist.  
  
2. Überprüfen Sie, ob Sie den Memberzugriffsoperator (`.`) zwischen einem Objekt und seine Member. Wenn Sie z. B. ein <xref:System.Windows.Forms.TextBox> -Steuerelement namens `TextBox1`besitzen, müssen Sie für den Zugriff auf dessen <xref:System.Windows.Forms.TextBoxBase.Text%2A> -Eigenschaft `TextBox1.Text`eingeben. Wenn Sie stattdessen `TextBox1Text`eingeben, haben Sie einen anderen Namen erstellt.  
  
3. Wenn die Schreibweise korrekt ist und die Syntax des Objekts Memberzugriff richtig ist, stellen Sie sicher, dass das Element deklariert wurde. Weitere Informationen finden Sie unter [Declared Elements](../../programming-guide/language-features/declared-elements/index.md).  
  
4. Wenn das Programmierelement deklariert wurde, überprüfen Sie, dass sie im Bereich befindet. Wenn die verweisende Anweisung außerhalb des Bereichs, der das Programmierelement deklariert ist, müssen Sie möglicherweise den Namen des zu qualifizieren. Weitere Informationen finden Sie unter [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).  

5. Wenn Sie keine voll qualifizierte Typ oder Namen von Typen und Member verwenden (z. B. Ihr Code verweist auf eine Eigenschaft als `MethodInfo.Name` anstelle von `System.Reflection.MethodInfo.Name`), Hinzufügen einer [Imports-Anweisung](../statements/imports-statement-net-namespace-and-type.md).

6. Wenn Sie versuchen, eine SDK-Projekt zu kompilieren (ein Projekt mit einem \*VBPROJ-Datei, die mit der Zeile beginnt `<Project Sdk="Microsoft.NET.Sdk">`), und die Fehlermeldung verweist auf einen Typ oder Member in der "Microsoft.VisualBasic.dll"-Assembly, Ihre Anwendung so konfigurieren Kompilieren Sie mit einem Verweis auf die Visual Basic-Laufzeitbibliothek. Standardmäßig wird eine Teilmenge der Bibliothek in die Assembly in einem Projekt von SDK-Stil eingebettet.

   Im folgenden Beispiel wird beispielsweise nicht, kompiliert, da die <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A?displayProperty=fullName> Methode wurde nicht gefunden. Es ist nicht in der Teilmenge der Visual Basic-Laufzeit enthalten, die mit Ihrer Anwendung eingebettet werden.  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb)]

   Um diesen Fehler zu beheben, fügen die `<VBRuntime>Default</VBRuntime>` Element an den Projekten `<PropertyGroup>` Abschnitt, wie im folgenden Visual Basic-Projekt-Datei gezeigt.

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a>Siehe auch  

[Deklarationen und Konstanten: Zusammenfassung](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Namen deklarierter Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
