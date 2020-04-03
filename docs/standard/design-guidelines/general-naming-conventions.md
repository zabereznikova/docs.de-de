---
title: Allgemeine Benennungskonventionen
ms.date: 10/22/2008
ms.technology: dotnet-standard
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
ms.openlocfilehash: ef4a8f571a67477739bbc59d3103ba78dea47177
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635917"
---
# <a name="general-naming-conventions"></a>Allgemeine Benennungskonventionen

In diesem Abschnitt werden allgemeine Namenskonventionen beschrieben, die sich auf die Wortauswahl beziehen, Richtlinien zur Verwendung von Abkürzungen und Akronymen sowie Empfehlungen, wie die Verwendung sprachspezifischer Namen vermieden werden kann.

## <a name="word-choice"></a>Word-Auswahl
 ✔️ do wählen Sie leicht lesbare Bezeichnernamen.

 Eine benannte `HorizontalAlignment` Eigenschaft ist z. B. besser englisch lesbar als `AlignmentHorizontal`.

 ✔️ do bevorzugen Lesbarkeit gegenüber Kürze.

 Der Eigenschaftsname `CanScrollHorizontally` `ScrollableX` ist besser als (ein obskurer Verweis auf die X-Achse).

 ❌Verwenden Sie KEINE Unterstriche, Bindestriche oder andere nicht-alphanumerische Zeichen.

 ❌Verwenden Sie NICHT die ungarische Notation.

 ❌AVOID mit Bezeichnern, die mit Schlüsselwörtern weit verbreiteter Programmiersprachen in Konflikt stehen.

 Gemäß Regel 4 der Common Language Specification (CLS) müssen alle konformen Sprachen einen Mechanismus bereitstellen, der den Zugriff auf benannte Elemente ermöglicht, die ein Schlüsselwort dieser Sprache als Bezeichner verwenden. In diesem Fall wird z. B. das Zeichen " - als Escape-Mechanismus verwendet. Es ist jedoch immer noch eine gute Idee, häufige Schlüsselwörter zu vermeiden, da es viel schwieriger ist, eine Methode mit der Escape-Sequenz zu verwenden als eine ohne sie.

## <a name="using-abbreviations-and-acronyms"></a>Verwenden von Abkürzungen und Akronymen
 ❌Verwenden Sie KEINE Abkürzungen oder Kontraktionen als Teil von Bezeichnernamen.

 Verwenden Sie `GetWindow` z. `GetWin`B. anstelle von .

 ❌Verwenden Sie KEINE Akronyme, die nicht allgemein akzeptiert werden, und auch wenn sie es sind, nur wenn nötig.

## <a name="avoiding-language-specific-names"></a>Vermeiden sprachspezifischer Namen
 ✔️ verwenden semantisch interessante Namen anstelle von sprachspezifischen Schlüsselwörtern für Typnamen.

 Ist z. B. `GetLength` `GetInt`ein besserer Name als .

 ✔️ verwenden einen generischen CLR-Typnamen anstelle eines sprachspezifischen Namens, in den seltenen Fällen, in denen ein Bezeichner keine semantische Bedeutung hat, der über seinen Typ hinausgeht.

 Eine Methode, die in <xref:System.Int64> konvertiert `ToInt64`wird, `ToLong` sollte <xref:System.Int64> z. B. den Namen " `long`""" und """" """" (weil es sich um einen CLR-Namen für den Alias "C"" handelt) nennen. In der folgenden Tabelle werden mehrere Basisdatentypen mit den CLR-Typnamen (sowie die entsprechenden Typnamen für C-, Visual Basic- und C++-Typen) dargestellt.

|C#|Visual Basic|C++|CLR|
|---------|------------------|-----------|---------|
|**sbyte**|**SByte**|**char**|**SByte**|
|**Byte**|**Byte**|**unsigned char**|**Byte**|
|**short**|**kurz**|**short**|**Int16**|
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|
|**int**|**Integer**|**int**|**Int32**|
|**uint**|**UInt32**|**unsigned int**|**UInt32**|
|**Lange**|**Lange**|**__int64**|**Int64**|
|**Ulong**|**UInt64**|**unsigned __int64**|**UInt64**|
|**float**|**Single**|**float**|**Single**|
|**double**|**Double**|**double**|**Double**|
|**bool**|**Boolean**|**bool**|**Boolean**|
|**char**|**Char**|**Wchar_t**|**Char**|
|**string**|**String**|**String**|**String**|
|**Objekt**|**Object**|**Object**|**Object**|

 ✔️ verwenden einen allgemeinen Namen, z. `value` B. oder , `item`anstatt den Typnamen zu wiederholen, in den seltenen Fällen, in denen ein Bezeichner keine semantische Bedeutung hat und der Typ des Parameters nicht wichtig ist.

## <a name="naming-new-versions-of-existing-apis"></a>Benennen neuer Versionen vorhandener APIs
 ✔️ verwenden beim Erstellen neuer Versionen einer vorhandenen API einen Namen, der der alten API ähnelt.

 Dies hilft, die Beziehung zwischen den APIs hervorzuheben.

 ✔️ möchten lieber ein Suffix als ein Präfix hinzufügen, um eine neue Version einer vorhandenen API anzugeben.

 Dies unterstützt die Erkennung beim Durchsuchen der Dokumentation oder bei der Verwendung von IntelliSense. Die alte Version der API wird in der Nähe der neuen APIs organisiert, da die meisten Browser und IntelliSense Bezeichner in alphabetischer Reihenfolge anzeigen.

 ✔️ CONSIDER mit einem brandneuen, aber aussagekräftigen Bezeichner, anstatt ein Suffix oder ein Präfix hinzuzufügen.

 ✔️ verwenden Sie ein numerisches Suffix, um eine neue Version einer vorhandenen API anzugeben, insbesondere wenn der vorhandene Name der API der einzige Name ist, der sinnvoll ist (d. h. wenn es sich um einen Industriestandard handelt) und wenn das Hinzufügen eines aussagekräftigen Suffixes (oder Ändern des Namens) nicht geeignet ist.

 ❌Verwenden Sie NICHT das Suffix "Ex" (oder ein ähnliches Suffix) für einen Bezeichner, um ihn von einer früheren Version derselben API zu unterscheiden.

 ✔️ DO verwenden das Suffix "64", wenn Versionen von APIs eingeführt werden, die auf einer 64-Bit-Ganzzahl (einer langen Ganzzahl) anstelle einer 32-Bit-Ganzzahl arbeiten. Sie müssen diesen Ansatz nur wählen, wenn die vorhandene 32-Bit-API vorhanden ist. Tun Sie es nicht für brandneue APIs mit nur einer 64-Bit-Version.

 *Teile &copy; 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Benennungsrichtlinien](../../../docs/standard/design-guidelines/naming-guidelines.md)
- [.NET-Namenskonventionen für EditorConfig](/visualstudio/ide/editorconfig-naming-conventions)
