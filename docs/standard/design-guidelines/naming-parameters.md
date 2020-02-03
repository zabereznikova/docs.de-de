---
title: Benennen von Parametern
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
ms.openlocfilehash: ebe2e2db4b109057bf576d4e18cfe511c657707e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743828"
---
# <a name="naming-parameters"></a>Benennen von Parametern
Neben dem offensichtlichen Grund für die Lesbarkeit ist es wichtig, den Richtlinien für Parameternamen zu folgen, da Parameter in der-Dokumentation und im-Designer angezeigt werden, wenn visuelle Entwurfs Tools IntelliSense-und Klassen Suchfunktionen bereitstellen.

 ✔️ Verwenden Sie "CamelCase" in Parameternamen.

 ✔️ beschreibende Parameternamen verwenden.

 ✔️ sollten Sie die Verwendung von Namen basierend auf der Bedeutung eines Parameters anstelle des Parameter Typs in Erwägung gezogen.

### <a name="naming-operator-overload-parameters"></a>Überladungs Parameter für Benennungs Operator
 ✔️ Verwenden Sie `left` und `right` für Parameternamen für binäre Operatoren, wenn es keine Bedeutung für die Parameter gibt.

 ✔️ `value` für Überladungs Parameternamen von unären Operatoren verwenden, wenn es keine Bedeutung für die Parameter gibt.

 Wenn Sie einen signifikanten Wert hinzufügen, ✔️ aussagekräftige Namen für Operator Überladungs Parameter in Erwägung gezogen.

 ❌ keine Abkürzungen oder numerischen Indizes für Parameternamen der Operator Überladung verwenden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
