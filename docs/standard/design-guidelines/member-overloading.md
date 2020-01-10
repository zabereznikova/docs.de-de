---
title: Überladen von Membern
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: e7decab042dd1ee36beacb18956e175196cd112c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709282"
---
# <a name="member-overloading"></a>Überladen von Membern
Das Überladen von Elementen bedeutet, dass zwei oder mehr Member für denselben Typ erstellt werden, die sich nur in der Anzahl oder dem Typ der Parameter unterscheiden, aber denselben Namen aufweisen. Im folgenden Beispiel wird die `WriteLine`-Methode überladen:  
  
```csharp  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Da nur Methoden, Konstruktoren und indizierte Eigenschaften über Parameter verfügen können, können nur die Elemente überladen werden.  
  
 Überladen ist eine der wichtigsten Techniken zur Verbesserung der Benutzerfreundlichkeit, Produktivität und Lesbarkeit von wiederverwendbaren Bibliotheken. Das Überladen der Anzahl von Parametern ermöglicht die Bereitstellung einfacherer Versionen von Konstruktoren und Methoden. Das Überladen für den Parametertyp ermöglicht die Verwendung desselben Element namens für Member, die identische Vorgänge für einen ausgewählten Satz von unterschiedlichen Typen ausführen.  
  
 **✓ DO** versuchen, beschreibende Parameternamen zu verwenden, um anzugeben, die Standardeinstellung von kürzeren Überladungen verwendet.  
  
 **X AVOID** nach dem Zufallsprinzip varying Parameternamen in Überladungen. Wenn ein Parameter in einer Überladung dieselbe Eingabe wie ein Parameter in einer anderen Überladung darstellt, sollten die Parameter denselben Namen haben.  
  
 **X AVOID** Mitglieder überlastet werden in der Reihenfolge der Parameter in inkonsistent. Parameter mit dem gleichen Namen sollten in allen über Ladungen an derselben Position angezeigt werden.  
  
 **✓ DO** stellen nur die längste Überladung virtuellen (wenn Erweiterbarkeit erforderlich ist). Kürzere über Ladungen sollten einfach bis zu einer längeren Überladung aufrufen.  
  
 **X DO NOT** verwenden `ref` oder `out` Modifizierer zum Überladen von Membern.  
  
 Einige Sprachen können keine Aufrufe von über Ladungen wie diesem auflösen. Außerdem verfügen solche über Ladungen in der Regel über eine ganz andere Semantik und sollten wahrscheinlich nicht über Ladungen, sondern auch über zwei separate Methoden verfügen.  
  
 **X DO NOT** Überladungen mit Parametern, die an der gleichen Position und ähnliche Typen noch mit einer anderen Semantik haben.  
  
 **✓ DO** zulassen `null` für optionale Argumente übergeben werden soll.  
  
 **✓ DO** verwenden Member überladen, anstatt Elemente mit Standardargumenten definieren.  
  
 Standardargumente sind nicht CLS-kompatibel.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
