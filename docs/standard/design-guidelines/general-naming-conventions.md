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
author: KrzysztofCwalina
ms.openlocfilehash: ae1b7ce83f6698cef470aabf07a12d89042ab8a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667686"
---
# <a name="general-naming-conventions"></a>Allgemeine Benennungskonventionen
Dieser Abschnitt beschreibt allgemeine Benennungskonventionen, die im Zusammenhang mit der Auswahl der Wörter, die Richtlinien zum Verwenden von Abkürzungen und Akronyme und Empfehlungen zum Vermeiden Sie sprachspezifische Namen.  
  
## <a name="word-choice"></a>Word-Auswahl  
 **✓ DO** übersichtlich Bezeichnernamen auswählen.  
  
 Z. B. eine Eigenschaft namens `HorizontalAlignment` ist Englisch-lesbarer als `AlignmentHorizontal`.  
  
 **✓ DO** ziehen Sie Lesbarkeit Knappheit zu finden.  
  
 Der Eigenschaftsname `CanScrollHorizontally` ist besser als `ScrollableX` (eine ungewöhnliche Verweis auf die X-Achse).  
  
 **X DO NOT** Unterstriche, Bindestriche oder andere nicht alphanumerischen Zeichen verwenden.  
  
 **X DO NOT** verwenden Ungarischer Notation benannt.  
  
 **X AVOID** Bezeichner, die häufig mit Schlüsselwörtern in Konflikt mit der übrigen Programmiersprachen verwendet.  
  
 Entsprechend der Regel 4, von der Common Language Specification (CLS) müssen alle kompatible Sprachen einen Mechanismus bereitstellen, der Zugriff auf benannte Elemente ermöglicht, die ein Schlüsselwort der Sprache als Bezeichner verwenden. C# verwendet beispielsweise das @-Zeichen als Escapesequenz Mechanismus in diesem Fall. Allerdings ist es immer noch eine gute Idee, häufige oder gemeinsame Schlüsselwörter zu vermeiden, da es sehr viel schwieriger, eine Methode mit der Escapesequenz als ein ohne diese zu verwenden ist.  
  
## <a name="using-abbreviations-and-acronyms"></a>Verwenden von Abkürzungen und Akronyme  
 **X DO NOT** Abkürzungen oder Kontraktionen als Teil des Bezeichnernamen verwenden.  
  
 Verwenden Sie z. B. `GetWindow` statt `GetWin`.  
  
 **X DO NOT** verwenden Sie Akronyme, die nicht weit verbreitete und sogar, wenn sie, falls erforderlich sind.  
  
## <a name="avoiding-language-specific-names"></a>Vermeiden sprachspezifische Namen  
 **✓ DO** verwenden semantisch interessante Namen anstelle der Language-spezifische Schlüsselwörter für Typnamen.  
  
 Z. B. `GetLength` ist ein besserer Name als `GetInt`.  
  
 **✓ DO** verwenden Sie eine generische CLR-Typnamen, anstatt einen sprachspezifischen Namen, in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung außer seinem Typ aufweist.  
  
 Z. B. eine Methode, die zum Konvertieren von <xref:System.Int64> heißen `ToInt64`, nicht `ToLong` (da <xref:System.Int64> ist ein CLR-Name für die c#-bestimmten Alias `long`). Die folgende Tabelle enthält einige Basisdatentypen, die mit der CLR-Typnamen (sowie die entsprechenden Typnamen für c#, Visual Basic und C++).  
  
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
|**object**|**Objekt**|**Objekt**|**Objekt**|  
  
 **✓ DO** verwenden Sie einen allgemeinen Namen, z. B. `value` oder `item`, anstatt wiederholen den Typnamen in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung hat und der Typ des Parameters nicht wichtig ist.  
  
## <a name="naming-new-versions-of-existing-apis"></a>Benennen die neue Versionen der vorhandenen APIs  
 **✓ DO** einen ähnlichen Namen wie der alte-API verwenden, wenn neue Versionen einer vorhandenen API zu erstellen.  
  
 Dadurch wird um die Beziehung zwischen der APIs zu markieren.  
  
 **✓ DO** bevorzugen Sie ein Suffix anstelle ein Präfix an, dass eine neue Version einer vorhandenen API hinzufügen.  
  
 Dies hilft beim Durchsuchen der Dokumentation, die Ermittlung oder mithilfe von IntelliSense. Die alte Version der API wird in der Nähe der neuen APIs, organisiert werden, da die meisten Browser und IntelliSense Bezeichner in alphabetischer Reihenfolge angezeigt.  
  
 **✓ CONSIDER** mithilfe eines brandneuen, jedoch aussagekräftigen-Bezeichners, anstatt ein Suffix oder Präfix.  
  
 **✓ DO** ein numerisches Suffix verwenden, um eine neue Version einer vorhandenen API anzugeben, insbesondere, wenn der vorhandene Name der API der einzige Name, die sinnvoll ist (d. h., wenn es sich um einen Industriestandard ist) und wenn jeder sinnvolle hinzufügen Suffix (oder Ändern des Namens) keine app Ropriate-Option.  
  
 **X DO NOT** verwenden, die "Ex" (oder ähnlich)-Suffix für einen Bezeichner zur Unterscheidung von einer früheren Version der gleichen-API.  
  
 **✓ DO** verwenden Sie das Suffix "64", bei der Einführung von Versionen von APIs, die für eine 64-Bit-Ganzzahl (eine lange ganze Zahl) anstelle von 32-Bit-Ganzzahl ausgeführt werden. Sie müssen sich nur auf diesen Ansatz verwenden, wenn die vorhandene 32-Bit-API vorhanden ist. Lassen Sie es für neue APIs mit nur einer 64-Bit-Version.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
