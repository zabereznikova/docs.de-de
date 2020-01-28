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
ms.openlocfilehash: c9cb178e838aab99c22089b527a6bd2e86b325de
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727839"
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

 versuchen Sie ✔️, beschreibende Parameternamen zu verwenden, um den von kürzeren über Ladungen verwendeten Standardwert anzugeben.

 ❌ vermeiden, willkürlich abweichende Parameternamen in über Ladungen zu verändern. Wenn ein Parameter in einer Überladung dieselbe Eingabe wie ein Parameter in einer anderen Überladung darstellt, sollten die Parameter denselben Namen haben.

 ❌ vermeiden, dass die Reihenfolge von Parametern in überladenen Elementen inkonsistent ist. Parameter mit dem gleichen Namen sollten in allen über Ladungen an derselben Position angezeigt werden.

 ✔️ machen nur die längste Überladung virtuell (wenn Erweiterbarkeit erforderlich ist). Kürzere über Ladungen sollten einfach bis zu einer längeren Überladung aufrufen.

 ❌ verwenden keine `ref` oder `out` modifiziererer, um Member zu überladen.

 Einige Sprachen können keine Aufrufe von über Ladungen wie diesem auflösen. Außerdem verfügen solche über Ladungen in der Regel über eine ganz andere Semantik und sollten wahrscheinlich nicht über Ladungen, sondern auch über zwei separate Methoden verfügen.

 ❌ verfügen über keine über Ladungen mit Parametern an derselben Position und ähnlichen Typen, die noch über eine andere Semantik verfügen.

 ✔️ erlauben, dass `null` für optionale Argumente übermittelt werden.

 ✔️ Verwenden Sie überladen von Elementen, anstatt Member mit Standardargumenten zu definieren.

 Standardargumente sind nicht CLS-kompatibel.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
