---
title: Allgemeine Benennungskonventionen
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 207227b3e5c52b7c6e0f704543379874f3708c03
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338103"
---
# <a name="general-naming-conventions"></a>Allgemeine Benennungskonventionen
Dieser Abschnitt beschreibt allgemeine Benennungskonventionen angeben, die auf Wortwahl, beziehen Richtlinien zur Verwendung von Abkürzungen und Akronyme und Empfehlungen zum Vermeiden Sie die Verwendung von sprachspezifischen Namen.  
  
## <a name="word-choice"></a>Word-Auswahl  
 **Führen Sie ✓** übersichtlich Bezeichnernamen auswählen.  
  
 Angenommen, eine Eigenschaft namens `HorizontalAlignment` ist Englisch-lesbarer als `AlignmentHorizontal`.  
  
 **Führen Sie ✓** ziehen Sie Lesbarkeit Knappheit zu finden.  
  
 Der Eigenschaftenname `CanScrollHorizontally` ist besser als `ScrollableX` (eine unbekannte Verweis auf die X-Achse).  
  
 **X nicht** Unterstriche, Bindestriche oder andere nicht alphanumerischen Zeichen verwenden.  
  
 **X nicht** verwenden Ungarischer Notation benannt.  
  
 **X vermeiden** Bezeichner, die häufig mit Schlüsselwörtern in Konflikt mit der übrigen Programmiersprachen verwendet.  
  
 Gemäß der Regel 4 der Common Language Specification (CLS) müssen alle kompatible Sprachen einen Mechanismus bereit, der Zugriff auf benannte Elemente ermöglicht, die ein Schlüsselwort für diese Sprache nicht als Bezeichner verwendet. C#-, verwendet z. B. das @-Zeichen als Escapezeichen Mechanismus in diesem Fall. Allerdings ist es immer noch eine gute Idee, häufige oder gemeinsame Schlüsselwörter vermeiden, da es sehr viel schwieriger, eine Methode mit der-Escapesequenz als ohne sie zu verwenden ist.  
  
## <a name="using-abbreviations-and-acronyms"></a>Verwenden von Abkürzungen und Akronyme  
 **X nicht** Abkürzungen oder Kontraktionen als Teil des Bezeichnernamen verwenden.  
  
 Verwenden Sie z. B. `GetWindow` statt `GetWin`.  
  
 **X nicht** verwenden Sie Akronyme, die nicht weit verbreitete und sogar, wenn sie, falls erforderlich sind.  
  
## <a name="avoiding-language-specific-names"></a>Vermeiden von sprachspezifischen Namen  
 **Führen Sie ✓** verwenden semantisch interessante Namen anstelle der Language-spezifische Schlüsselwörter für Typnamen.  
  
 Beispielsweise `GetLength` ist ein besserer Name als `GetInt`.  
  
 **Führen Sie ✓** verwenden Sie eine generische CLR-Typnamen, anstatt einen sprachspezifischen Namen, in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung außer seinem Typ aufweist.  
  
 Z. B. eine Methode zum Konvertieren von <xref:System.Int64> heißen `ToInt64`, nicht `ToLong` (da <xref:System.Int64> ist ein CLR-Name für die c#-bestimmten Alias `long`). Die folgende Tabelle enthält einige Basisdatentypen mithilfe der CLR-Typnamen (sowie die zugehörigen Typnamen für c#, Visual Basic und C++).  
  
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
  
 **Führen Sie ✓** verwenden Sie einen allgemeinen Namen, z. B. `value` oder `item`, anstatt wiederholen den Typnamen in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung hat und der Typ des Parameters nicht wichtig ist.  
  
## <a name="naming-new-versions-of-existing-apis"></a>Benennen die neue Versionen der vorhandenen-APIs  
 **Führen Sie ✓** einen ähnlichen Namen wie der alte-API verwenden, wenn neue Versionen einer vorhandenen API zu erstellen.  
  
 Dadurch wird um die Beziehung zwischen der APIs zu markieren.  
  
 **Führen Sie ✓** bevorzugen Sie ein Suffix anstelle ein Präfix an, dass eine neue Version einer vorhandenen API hinzufügen.  
  
 Dadurch wird die Ermittlung unterstützt, beim Durchsuchen der Dokumentation, oder Verwenden von IntelliSense. Die alte Version der API wird in der Nähe der neuen APIs organisiert werden, da die meisten Browsern und IntelliSense Bezeichner in alphabetischer Reihenfolge anzuzeigen.  
  
 **✓ GGF.** mithilfe eines brandneuen, jedoch aussagekräftigen-Bezeichners, anstatt ein Suffix oder Präfix.  
  
 **Führen Sie ✓** ein numerisches Suffix verwenden, um eine neue Version einer vorhandenen API anzugeben, insbesondere, wenn der vorhandene Name der API der einzige Name, die sinnvoll ist (d. h., wenn es sich um einen Industriestandard ist) und wenn jeder sinnvolle hinzufügen Suffix (oder Ändern des Namens) keine app Ropriate-Option.  
  
 **X nicht** verwenden, die "Ex" (oder ähnlich)-Suffix für einen Bezeichner zur Unterscheidung von einer früheren Version der gleichen-API.  
  
 **Führen Sie ✓** verwenden Sie das Suffix "64", bei der Einführung von Versionen von APIs, die für eine 64-Bit-Ganzzahl (eine lange ganze Zahl) anstelle von 32-Bit-Ganzzahl ausgeführt werden. Sie müssen nur so vorgehen möchten, wenn die vorhandene 32-Bit-API vorhanden ist. Führen Sie es für die neuen APIs mit nur einer 64-Bit-Version.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
