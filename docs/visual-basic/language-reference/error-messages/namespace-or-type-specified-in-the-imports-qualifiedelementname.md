---
title: Namespace oder Typ angegeben, in die Importe &#39; &lt;qualifizierterelementname&gt; &#39; ist nicht&#39;t jeden öffentlichen Member enthalten oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 8be0df5cbe4b8d4a640c9b6c2e126b3828254fd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595104"
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace oder Typ angegeben, in die Importe &#39; &lt;qualifizierterelementname&gt; &#39; ist nicht&#39;t jeden öffentlichen Member enthalten oder kann nicht gefunden werden
Namespace oder Typ angegeben, in die Importe\<qualifizierter_elementname >' enthält keine öffentlichen Member oder kann nicht gefunden werden. Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält. Stellen Sie sicher, dass der Aliasname keine andere Aliase enthält.  
  
 Ein `Imports` Anweisung gibt ein enthaltendes Element, das entweder nicht gefunden werden oder keine definiert `Public` Elemente.  
  
 Ein *mit Element* möglich, einen Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration. Das enthaltende Element enthält Elemente, z. B. Variablen, Prozeduren oder andere Elemente enthält.  
  
 Importieren von dient zum Code den Zugriff auf Member für Namespace oder Typ zu ermöglichen, ohne sie zu qualifizieren. Das Projekt müssen möglicherweise auch einen Verweis auf den Namespace oder Typ hinzufügen. Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Wenn der Compiler die angegebene enthaltende Element nicht finden kann, und klicken Sie dann nicht Verweise aufgelöst werden kann, die sie verwenden. Wenn das Element gefunden wird, aber das Element nicht macht `Public` Elemente, und klicken Sie dann auf kein Verweis erfolgreich sein kann. In beiden Fällen ist es ohne Bedeutung, um das Element zu importieren.  
  
 Sollten Sie bedenken, wenn Sie ein enthaltendes Element importieren und ein Importalias zuweisen, dann Sie Importalias nicht verwenden, um ein anderes Element zu importieren. Der folgende Code generiert einen Compilerfehler.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **Fehler-ID:** BC40056  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass das enthaltende Element aus Ihrem Projekt zugänglich ist.  
  
2.  Stellen Sie sicher, dass die Spezifikation des enthaltenden Elements Importalias bereits ein anderer Import nicht enthalten ist.  
  
3.  Stellen Sie sicher, dass das enthaltende Element verfügbar, mindestens eine macht `Public` Member.  
  
## <a name="see-also"></a>Siehe auch  
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
