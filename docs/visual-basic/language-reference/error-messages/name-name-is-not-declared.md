---
title: Der Name "<name>" wurde nicht deklariert.
ms.date: 10/10/2018
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: 6fa4639b97e4314d8752ae520e94a58a189b7cbb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397167"
---
# <a name="name-name-is-not-declared"></a>Der Name "\<name>" wurde nicht deklariert.
Eine-Anweisung verweist auf ein Programmier Element, aber der Compiler kann kein Element mit diesem exakten Namen finden.  
  
 **Fehler-ID:** BC30451  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die Schreibweise des Namens in der verweisenden Anweisung. Bei Visual Basic wird die Groß-/Kleinschreibung nicht beachtet, aber jede andere Abweichung in der Rechtschreibung wird als vollständig anderer Name betrachtet. Beachten Sie, dass der Unterstrich (`_`) Teil des Namens und daher Teil der Schreibweise ist.  
  
2. Überprüfen Sie, ob der Member Access Operator ( `.` ) zwischen einem Objekt und seinem Member vorhanden ist. Wenn Sie z. B. ein <xref:System.Windows.Forms.TextBox> -Steuerelement namens `TextBox1`besitzen, müssen Sie für den Zugriff auf dessen <xref:System.Windows.Forms.TextBoxBase.Text%2A> -Eigenschaft `TextBox1.Text`eingeben. Wenn Sie stattdessen `TextBox1Text`eingeben, haben Sie einen anderen Namen erstellt.  
  
3. Wenn die Schreibweise korrekt ist und die Syntax des Zugriffs auf Objektmember richtig ist, überprüfen Sie, ob das Element deklariert wurde. Weitere Informationen finden Sie unter [deklarierte Elemente](../../programming-guide/language-features/declared-elements/index.md).  
  
4. Wenn das Programmier Element deklariert wurde, überprüfen Sie, ob es sich im Gültigkeitsbereich befindet. Wenn die verweisende Anweisung außerhalb des Bereichs liegt, der das Programmier Element deklariert, müssen Sie den Elementnamen möglicherweise qualifizieren. Weitere Informationen finden Sie unter [Scope in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md).  

5. Wenn Sie keinen voll qualifizierten Typ oder Typ und Elementnamen verwenden (z. b. bezieht sich der Code auf eine Eigenschaft als `MethodInfo.Name` anstelle von `System.Reflection.MethodInfo.Name` ), fügen Sie eine [Imports-Anweisung](../statements/imports-statement-net-namespace-and-type.md)hinzu.

6. Wenn Sie versuchen, ein SDK-Projekt (ein Projekt mit einer \* VBPROJ-Datei, das mit der Zeile beginnt) zu kompilieren `<Project Sdk="Microsoft.NET.Sdk">` , und die Fehlermeldung auf einen Typ oder Member in der Microsoft. VisualBasic. dll-Assembly verweist, konfigurieren Sie die Anwendung so, dass Sie mit einem Verweis auf die Visual Basic Lauf Zeit Bibliothek kompiliert wird. Standardmäßig ist eine Teilmenge der Bibliothek in die Assembly in einem SDK-Stil eingebettet.

   Beispielsweise kann das folgende Beispiel nicht kompiliert werden, da die- <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ChangeType%2A?displayProperty=fullName> Methode nicht gefunden werden kann. Sie ist nicht in die Teilmenge der in der Anwendung enthaltenen Visual Basic Laufzeit eingebettet.  

   [!code-vb[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/program1.vb?highlight=7)]

   Um diesen Fehler zu beheben, fügen Sie das-Element dem Projekt `<VBRuntime>Default</VBRuntime>` `<PropertyGroup>` Abschnitt hinzu, wie im folgenden Visual Basic Projektdatei gezeigt.

   [!code-xml[BC30451](~/samples/snippets/visualbasic/language-reference/error-messages/bc30451/vbruntime.vbproj?highlight=6)]

## <a name="see-also"></a>Weitere Informationen

- [Deklarationen und Konstanten: Zusammenfassung](../keywords/declarations-and-constants-summary.md)
- [Benennungskonventionen in Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
