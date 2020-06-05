---
title: Der in Imports '<qualifiedelementname>' auf Projektebene angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 0ee235252d69e6f77ce53b048f45e73d0969e864
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409451"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Der in Imports '\<qualifiedelementname>' auf Projektebene angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
Der in den Importen auf Projektebene angegebene Namespace oder Typ \<qualifiedelementname> enthält keinen öffentlichen Member oder kann nicht gefunden werden. Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentlichen Member enthält. Stellen Sie sicher, dass der Alias Name keine anderen Aliase enthält.  
  
 Eine Import-Eigenschaft eines Projekts gibt ein enthaltende Element an, das entweder nicht gefunden werden kann oder keine Member definiert `Public` .  
  
 Ein *enthaltende Element* kann ein Namespace, eine Klasse, eine Struktur, ein Modul, eine Schnittstelle oder eine Enumeration sein. Das enthaltende Element enthält Member, z. b. Variablen, Prozeduren oder andere enthaltende Elemente.  
  
 Der Zweck des Importierens besteht darin, dass Ihr Code auf Namespaces oder Typmember zugreifen kann, ohne Sie qualifizieren zu müssen. Das Projekt muss möglicherweise auch einen Verweis auf den Namespace oder den Typ hinzufügen. Weitere Informationen finden Sie unter "Importieren enthaltender Elemente" in [Verweise auf deklarierte Elemente](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Wenn der Compiler das angegebene enthaltende Element nicht finden kann, kann er keine Verweise auflösen, die ihn verwenden. Wenn das-Element gefunden wird, aber das-Element keine Member verfügbar macht `Public` , kann kein Verweis erfolgreich sein. In beiden Fällen ist es bedeutungslos, das-Element zu importieren.  
  
 Verwenden Sie den **Projekt-Designer** , um die zu importierenden Elemente anzugeben. Verwenden Sie den Abschnitt **importierte Namespaces** der Seite **Verweise** . Sie können zum Projekt- **Designer** gelangen, indem Sie in **Projektmappen-Explorer**auf das Symbol " **mein Projekt** " doppelklicken.  
  
 **Fehler-ID:** BC40057  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Öffnen Sie den **Projekt-Designer** , und wechseln Sie zur Seite **Verweis** .  
  
2. Überprüfen Sie im Abschnitt **importierte Namespaces** , ob auf das enthaltende Element von Ihrem Projekt aus zugegriffen werden kann.  
  
3. Vergewissern Sie sich, dass das enthaltende Element mindestens einen Member verfügbar macht `Public` .  
  
## <a name="see-also"></a>Weitere Informationen

- [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [Öffentlich](../modifiers/public.md)
- [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
