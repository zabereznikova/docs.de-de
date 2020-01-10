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
ms.openlocfilehash: d1b01fac7368ffeceb554c6f12aecb8f8760fa1d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709334"
---
# <a name="general-naming-conventions"></a>Allgemeine Benennungskonventionen
In diesem Abschnitt werden allgemeine Benennungs Konventionen im Zusammenhang mit der Wort Auswahl, Richtlinien zur Verwendung von Abkürzungen und Akronymen und Empfehlungen zur Vermeidung der Verwendung von sprachspezifischen Namen beschrieben.  
  
## <a name="word-choice"></a>Wort Auswahl  
 **✓ DO** übersichtlich Bezeichnernamen auswählen.  
  
 Beispielsweise ist eine Eigenschaft mit dem Namen `HorizontalAlignment` besser lesbar als `AlignmentHorizontal`.  
  
 **✓ DO** ziehen Sie Lesbarkeit Knappheit zu finden.  
  
 Der Eigenschaftsname `CanScrollHorizontally` ist besser als `ScrollableX` (ein undurchsichtiger Verweis auf die X-Achse).  
  
 **X DO NOT** Unterstriche, Bindestriche oder andere nicht alphanumerischen Zeichen verwenden.  
  
 **X DO NOT** verwenden Ungarischer Notation benannt.  
  
 **X AVOID** Bezeichner, die häufig mit Schlüsselwörtern in Konflikt mit der übrigen Programmiersprachen verwendet.  
  
 Gemäß Regel 4 der Common Language Specification (CLS) müssen alle kompatiblen Sprachen einen Mechanismus bereitstellen, der den Zugriff auf benannte Elemente ermöglicht, die ein Schlüsselwort dieser Sprache als Bezeichner verwenden. C#Beispielsweise wird in diesem Fall das @-Zeichen als Escapezeichen verwendet. Es ist jedoch immer noch eine gute Idee, gängige Schlüsselwörter zu vermeiden, da es weitaus schwieriger ist, eine Methode mit der Escapesequenz zu verwenden, als Sie ohne Sie.  
  
## <a name="using-abbreviations-and-acronyms"></a>Verwenden von Abkürzungen und Akronymen  
 **X DO NOT** Abkürzungen oder Kontraktionen als Teil des Bezeichnernamen verwenden.  
  
 Verwenden Sie z. b. `GetWindow` anstelle von `GetWin`.  
  
 **X DO NOT** verwenden Sie Akronyme, die nicht weit verbreitete und sogar, wenn sie, falls erforderlich sind.  
  
## <a name="avoiding-language-specific-names"></a>Vermeiden von sprachspezifischen Namen  
 **✓ DO** verwenden semantisch interessante Namen anstelle der Language-spezifische Schlüsselwörter für Typnamen.  
  
 Beispielsweise ist `GetLength` ein besserer Name als `GetInt`.  
  
 **✓ DO** verwenden Sie eine generische CLR-Typnamen, anstatt einen sprachspezifischen Namen, in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung außer seinem Typ aufweist.  
  
 Beispielsweise sollte eine Methode, die in <xref:System.Int64> umwandelt, `ToInt64`, nicht `ToLong` benannt werden (da <xref:System.Int64> ein CLR-Name C#für den-spezifischen Alias `long`ist). In der folgenden Tabelle werden mehrere Basis Datentypen mit den CLR-Typnamen (sowie die entsprechenden Typnamen C#für, Visual Basic und C++) dargestellt.  
  
|C#|Visual Basic|C++|-CLR|  
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
|**object**|**Objekt**|**Objekt**|**Objekt**|  
  
 **✓ DO** verwenden Sie einen allgemeinen Namen, z. B. `value` oder `item`, anstatt wiederholen den Typnamen in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung hat und der Typ des Parameters nicht wichtig ist.  
  
## <a name="naming-new-versions-of-existing-apis"></a>Benennen neuer Versionen vorhandener APIs  
 **✓ DO** einen ähnlichen Namen wie der alte-API verwenden, wenn neue Versionen einer vorhandenen API zu erstellen.  
  
 Dadurch wird die Beziehung zwischen den APIs hervorgehoben.  
  
 **✓ DO** bevorzugen Sie ein Suffix anstelle ein Präfix an, dass eine neue Version einer vorhandenen API hinzufügen.  
  
 Dadurch wird die Ermittlung beim Durchsuchen der Dokumentation oder bei Verwendung von IntelliSense unterstützt. Die alte Version der API wird in der Nähe der neuen APIs organisiert, da die meisten Browser und IntelliSense Bezeichner in alphabetischer Reihenfolge anzeigen.  
  
 **✓ CONSIDER** mithilfe eines brandneuen, jedoch aussagekräftigen-Bezeichners, anstatt ein Suffix oder Präfix.  
  
 **✓ DO** ein numerisches Suffix verwenden, um eine neue Version einer vorhandenen API anzugeben, insbesondere, wenn der vorhandene Name der API der einzige Name, die sinnvoll ist (d. h., wenn es sich um einen Industriestandard ist) und wenn jeder sinnvolle hinzufügen Suffix (oder Ändern des Namens) keine app Ropriate-Option.  
  
 **X DO NOT** verwenden, die "Ex" (oder ähnlich)-Suffix für einen Bezeichner zur Unterscheidung von einer früheren Version der gleichen-API.  
  
 **✓ DO** verwenden Sie das Suffix "64", bei der Einführung von Versionen von APIs, die für eine 64-Bit-Ganzzahl (eine lange ganze Zahl) anstelle von 32-Bit-Ganzzahl ausgeführt werden. Diese Vorgehensweise ist nur dann erforderlich, wenn die vorhandene 32-Bit-API vorhanden ist. Verwenden Sie dies nicht für neue APIs mit einer 64-Bit-Version.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
