---
title: Benennen von Ressourcen
description: Überprüfen Sie die Benennungs Richtlinien für Ressourcen in .net, die den Richtlinien für Benennungs Eigenschaften ähneln.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: 765337bcf9fad4f9a8c9272a15b5c77d02770471
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768247"
---
# <a name="naming-resources"></a>Benennen von Ressourcen
Da auf lokalisierbare Ressourcen über bestimmte Objekte verwiesen werden kann, als ob es sich um Eigenschaften handelt, ähneln die Benennungs Richtlinien für Ressourcen den Eigenschafts Richtlinien.

 ✔️ Verwenden Sie die Pass-/Schreibweise in Ressourcen Schlüsseln.

 ✔️ Stellen beschreibende und nicht kurze Bezeichner bereit.

 ❌Verwenden Sie keine sprachspezifischen Schlüsselwörter der Haupt-CLR-Sprachen.

 ✔️ nur alphanumerische Zeichen und Unterstriche in Benennungs Ressourcen verwenden.

 ✔️ die folgende Benennungs Konvention für Ausnahme Nachrichten Ressourcen verwenden.

 Der Ressourcen Bezeichner sollte der Name des Ausnahme Typs und ein kurzer Bezeichner der Ausnahme sein:

 `ArgumentExceptionIllegalCharacters` `ArgumentExceptionInvalidName`
 `ArgumentExceptionFileNameIsMalformed`

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Framework-Entwurfs Richtlinien](index.md)
- [Benennungs Richtlinien](naming-guidelines.md)
