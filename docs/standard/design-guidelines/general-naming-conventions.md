---
title: Allgemeine Benennungskonventionen
description: Verwenden Sie allgemeine Benennungs Konventionen im Zusammenhang mit der Wort Auswahl, Richtlinien zur Verwendung von Abkürzungen und Akronymen sowie Anleitungen zum Vermeiden von sprachspezifischen Namen.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
ms.openlocfilehash: ff9efd40b630e8e25963b3d69b026feea2823ece
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821098"
---
# <a name="general-naming-conventions"></a>Allgemeine Benennungskonventionen

In diesem Abschnitt werden allgemeine Benennungs Konventionen im Zusammenhang mit der Wort Auswahl, Richtlinien zur Verwendung von Abkürzungen und Akronymen und Empfehlungen zur Vermeidung der Verwendung von sprachspezifischen Namen beschrieben.

## <a name="word-choice"></a>Wort Auswahl
 ✔️ Wählen Sie leicht lesbare Bezeichnernamen aus.

 Beispielsweise ist eine Eigenschaft mit dem Namen `HorizontalAlignment` besser lesbar als `AlignmentHorizontal` .

 ✔️ bevorzugen die Lesbarkeit gegenüber der Übersichtlichkeit.

 Der Eigenschaftsname `CanScrollHorizontally` ist besser als `ScrollableX` (ein undurchsichtiger Verweis auf die X-Achse).

 ❌ Verwenden Sie keine Unterstriche, Bindestriche oder andere nicht alphanumerische Zeichen.

 ❌ Verwenden Sie keine ungarische Notation.

 ❌ Vermeiden Sie die Verwendung von bezeichlern, die mit Schlüsselwörtern häufig verwendeter Programmiersprachen in Konflikt stehen

 Gemäß Regel 4 der Common Language Specification (CLS) müssen alle kompatiblen Sprachen einen Mechanismus bereitstellen, der den Zugriff auf benannte Elemente ermöglicht, die ein Schlüsselwort dieser Sprache als Bezeichner verwenden. C# verwendet in diesem Fall z. b. das @-Zeichen als Escapezeichen. Es ist jedoch immer noch eine gute Idee, gängige Schlüsselwörter zu vermeiden, da es weitaus schwieriger ist, eine Methode mit der Escapesequenz zu verwenden, als Sie ohne Sie.

## <a name="using-abbreviations-and-acronyms"></a>Verwenden von Abkürzungen und Akronymen
 ❌ Verwenden Sie keine Abkürzungen oder gegen übereinstigkeiten als Teil der Bezeichnernamen.

 Verwenden Sie z `GetWindow` . b. anstelle von `GetWin` .

 ❌ Verwenden Sie keine Akronyme, die nicht weitgehend akzeptiert werden, und auch dann nicht, wenn dies der Fall ist.

## <a name="avoiding-language-specific-names"></a>Vermeiden von Language-Specific Namen
 ✔️ verwenden semantisch interessante Namen anstelle von sprachspezifischen Schlüsselwörtern für Typnamen.

 Beispielsweise `GetLength` ist ein besserer Name als `GetInt` .

 ✔️ verwenden einen generischen CLR-Typnamen anstelle eines sprachspezifischen namens, in den seltenen Fällen, in denen ein Bezeichner über den Typ hinaus keine semantische Bedeutung hat.

 Beispielsweise sollte eine Methode, die in <xref:System.Int64> die-Klasse umwandelt, den Namen `ToInt64` hat, nicht `ToLong` (da <xref:System.Int64> ein CLR-Name für den c#-spezifischen Alias ist `long` ). In der folgenden Tabelle werden mehrere Basis Datentypen mit den CLR-Typnamen (sowie die entsprechenden Typnamen für c#, Visual Basic und C++) dargestellt.

|C#|Visual Basic|C++|CLR|
|---------|------------------|-----------|---------|
|**sbyte**|**SByte**|**char**|**SByte**|
|**byte**|**Byte**|**unsigned char**|**Byte**|
|**short**|**Short**|**short**|**Int16**|
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|
|**int**|**Integer**|**int**|**Int32**|
|**uint**|**UInt32**|**unsigned int**|**UInt32**|
|**long**|**Long**|**__int64**|**Int64**|
|**ulong**|**UInt64**|**__int64 ohne Vorzeichen**|**UInt64**|
|**float**|**Single**|**float**|**Single**|
|**double**|**Double**|**double**|**Double**|
|**bool**|**Boolean**|**bool**|**Boolean**|
|**char**|**Char**|**wchar_t**|**Char**|
|**string**|**String**|**String**|**String**|
|**object**|**Object**|**Object**|**Object**|

 ✔️ einen allgemeinen Namen verwenden, z. b. `value` oder `item` , anstatt den Typnamen zu wiederholen, in den seltenen Fällen, in denen ein Bezeichner keine Semantik Bedeutung hat und der Typ des Parameters nicht wichtig ist.

## <a name="naming-new-versions-of-existing-apis"></a>Benennen neuer Versionen vorhandener APIs
 ✔️ einen Namen verwenden, der der alten API ähnelt, wenn neue Versionen einer vorhandenen API erstellt werden.

 Dadurch wird die Beziehung zwischen den APIs hervorgehoben.

 ✔️ lieber ein Suffix anstelle eines Präfixes hinzufügen, um eine neue Version einer vorhandenen API anzugeben.

 Dadurch wird die Ermittlung beim Durchsuchen der Dokumentation oder bei Verwendung von IntelliSense unterstützt. Die alte Version der API wird in der Nähe der neuen APIs organisiert, da die meisten Browser und IntelliSense Bezeichner in alphabetischer Reihenfolge anzeigen.

 ✔️ sollten Sie die Verwendung eines ganz neuen, aber aussagekräftigen Bezeichners in Erwägung gezogen, anstatt ein Suffix oder ein Präfix hinzuzufügen.

 in ✔️ wird ein numerisches Suffix verwendet, um eine neue Version einer vorhandenen API anzugeben. Dies gilt insbesondere, wenn der vorhandene Name der API der einzige Name ist, der sinnvoll ist (d. h., wenn es sich um einen Industriestandard handelt) und das Hinzufügen eines sinnvollen Suffixes (oder Ändern des Namens) keine geeignete Option ist.

 ❌ Verwenden Sie das Suffix "ex" (oder ein ähnliches Suffix) nicht für einen Bezeichner, um ihn von einer früheren Version derselben API zu unterscheiden.

 in ✔️ wird das Suffix "64" verwendet, wenn Versionen von APIs eingeführt werden, die mit einer 64-Bit-Ganzzahl (Long Integer) anstelle einer 32-Bit-Ganzzahl arbeiten. Diese Vorgehensweise ist nur dann erforderlich, wenn die vorhandene 32-Bit-API vorhanden ist. Verwenden Sie dies nicht für neue APIs mit einer 64-Bit-Version.

 *Teile &copy; 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfsrichtlinien](index.md)
- [Richtlinien für die Benennung](naming-guidelines.md)
- [.NET-Namenskonventionen für EditorConfig](/visualstudio/ide/editorconfig-naming-conventions)
