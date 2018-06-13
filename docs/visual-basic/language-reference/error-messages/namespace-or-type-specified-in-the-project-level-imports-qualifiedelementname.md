---
title: Namespace oder Typ angegeben, in das Projekt auf Dokumentebene Importe &#39; &lt;qualifizierterelementname&gt; &#39; ist nicht&#39;t jeden öffentlichen Member enthalten oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: d6d0c931262d892ec3e65888a76f25218b23d868
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595812"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace oder Typ angegeben, in das Projekt auf Dokumentebene Importe &#39; &lt;qualifizierterelementname&gt; &#39; ist nicht&#39;t jeden öffentlichen Member enthalten oder kann nicht gefunden werden
Namespace oder Typ angegeben, in das Projekt auf Dokumentebene Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder kann nicht gefunden werden. Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält. Stellen Sie sicher, dass der Aliasname keine andere Aliase enthält.  
  
 Eine Import-Eigenschaft eines Projekts gibt ein enthaltendes Element, das entweder nicht gefunden werden oder keine definiert `Public` Elemente.  
  
 Ein *mit Element* möglich, einen Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration. Das enthaltende Element enthält Elemente, z. B. Variablen, Prozeduren oder andere Elemente enthält.  
  
 Importieren von dient zum Code den Zugriff auf Member für Namespace oder Typ zu ermöglichen, ohne sie zu qualifizieren. Das Projekt müssen möglicherweise auch einen Verweis auf den Namespace oder Typ hinzufügen. Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Wenn der Compiler die angegebene enthaltende Element nicht finden kann, und klicken Sie dann nicht Verweise aufgelöst werden kann, die sie verwenden. Wenn das Element gefunden wird, aber das Element nicht macht `Public` Elemente, und klicken Sie dann auf kein Verweis erfolgreich sein kann. In beiden Fällen ist es ohne Bedeutung, um das Element zu importieren.  
  
 Verwenden Sie die **Projekt-Designer** an Elemente zu importieren. Verwenden der **importierte Namespaces** Teil der **Verweise** Seite. Sie können zum Abrufen der **Projekt-Designer** durch Doppelklicken auf die **Mein Projekt** Symbol in **Projektmappen-Explorer**.  
  
 **Fehler-ID:** BC40057  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Öffnen der **Projekt-Designer** und wechseln Sie zu der **Verweis** Seite.  
  
2.  In der **importierte Namespaces** Abschnitt, stellen Sie sicher, dass das enthaltende Element aus Ihrem Projekt zugänglich ist.  
  
3.  Stellen Sie sicher, dass das enthaltende Element verfügbar, mindestens eine macht `Public` Member.  
  
## <a name="see-also"></a>Siehe auch  
 [Seite „Verweise“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
