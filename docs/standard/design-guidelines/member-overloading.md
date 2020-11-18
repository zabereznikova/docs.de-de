---
title: Überladen von Membern
ms.date: 10/22/2008
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: 16e84f06ec388fe7e3c221f35c3e970b9b483ba5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820968"
---
# <a name="member-overloading"></a>Überladen von Membern
Das Überladen von Elementen bedeutet, dass zwei oder mehr Member für denselben Typ erstellt werden, die sich nur in der Anzahl oder dem Typ der Parameter unterscheiden, aber denselben Namen aufweisen. Im folgenden Beispiel wird die- `WriteLine` Methode überladen:

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

 ❌ Vermeiden Sie beliebig abweichende Parameternamen in über Ladungen. Wenn ein Parameter in einer Überladung dieselbe Eingabe wie ein Parameter in einer anderen Überladung darstellt, sollten die Parameter denselben Namen haben.

 ❌ Vermeiden Sie eine Inkonsistenz bei der Reihenfolge von Parametern in überladenen Elementen. Parameter mit dem gleichen Namen sollten in allen über Ladungen an derselben Position angezeigt werden.

 ✔️ machen nur die längste Überladung virtuell (wenn Erweiterbarkeit erforderlich ist). Kürzere über Ladungen sollten einfach bis zu einer längeren Überladung aufrufen.

 ❌ Verwenden Sie keine- `ref` oder- `out` Modifizierer, um Member überladen.

 Einige Sprachen können keine Aufrufe von über Ladungen wie diesem auflösen. Außerdem verfügen solche über Ladungen in der Regel über eine ganz andere Semantik und sollten wahrscheinlich nicht über Ladungen, sondern auch über zwei separate Methoden verfügen.

 ❌ Sie verfügen über keine über Ladungen mit Parametern an derselben Position und ähnlichen Typen, die noch über eine andere Semantik verfügen.

 ✔️ zulassen `null` , dass optionale Argumente übermittelt werden.

 ✔️ Verwenden Sie überladen von Elementen, anstatt Member mit Standardargumenten zu definieren.

 Standardargumente sind nicht CLS-kompatibel.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfs Richtlinien für Member](member.md)
- [Framework-Entwurfs Richtlinien](index.md)
