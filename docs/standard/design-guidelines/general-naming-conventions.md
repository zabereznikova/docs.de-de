---
title: "Allgemeine Benennungskonventionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "[Namen [.NET Framework], Konflikte"
  - "Typnamen, Konflikte"
  - "Sprachspezifische Typnamen"
  - "[Namen [.NET Framework], Informationen über Benennungsrichtlinien"
  - "[Namen [.NET Framework], Abkürzung"
  - "Benennungsrichtlinien für Abkürzungen"
  - "Benennungsrichtlinien"
  - "Schreibweise für Ungarn"
  - "[Namen [.NET Framework], Namen"
  - "[Namen [.NET Framework], Akronyme"
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Allgemeine Benennungskonventionen
Dieser Abschnitt beschreibt allgemeine Benennungskonventionen, die auf Wortwahl, beziehen die Richtlinien zum Verwenden von Abkürzungen und Akronyme und Empfehlungen zum Vermeiden sprachspezifischen Namen.  
  
## Wortwahl  
 **✓ führen** leicht lesbare Bezeichnernamen wählen.  
  
 Z. B. eine Eigenschaft mit dem Namen `HorizontalAlignment` ist Englisch\-übersichtlicher als `AlignmentHorizontal`.  
  
 **✓ führen** ziehen Sie Lesbarkeit weggelassen.  
  
 Der Eigenschaftenname `CanScrollHorizontally` ist besser als `ScrollableX` \(ein unklarer Verweis auf die X\-Achse\).  
  
 **X nicht** Unterstriche, Bindestriche oder andere nicht alphanumerischen Zeichen verwenden.  
  
 **X nicht** Schreibweise für Ungarn verwenden.  
  
 **X vermeiden** Verwendung von Bezeichnern, die mit Schlüsselwörtern weit Konflikt Programmiersprachen verwendet.  
  
 Gemäß Regel 4 der Common Language Specification \(CLS\) müssen alle kompatible Sprachen einen Mechanismus bereit, der Zugriff auf benannte Elemente, die Schlüsselwörter der Sprache als Bezeichner verwenden. C\# verwendet beispielsweise das @\-Zeichen als Escapesequenz Mechanismus für die in diesem Fall. Es ist jedoch trotzdem eine gute Idee, gemeinsame Schlüsselwörter vermeiden, da es sehr viel schwieriger, eine Methode mit der Escape\-Sequenz als eine ohne zu verwenden ist.  
  
## Verwenden von Abkürzungen und Akronyme  
 **X nicht** Abkürzungen oder Kontraktionen als Teil von Bezeichnernamen verwenden.  
  
 Verwenden Sie z. B. `GetWindow` statt `GetWin`.  
  
 **X nicht** verwenden Sie Akronyme, die nicht weit verbreitete und sogar, nur bei Bedarf werden.  
  
## Vermeiden sprachspezifische Namen  
 **✓ führen** für Typnamen semantisch interessante Namen statt sprachspezifische Schlüsselwörter verwenden.  
  
 Z. B. `GetLength` ist ein besserer Name als `GetInt`.  
  
 **✓ führen** verwenden generischer CLR\-Typname, anstatt einen sprachspezifischen Namen in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung außer seinem Typ verfügt.  
  
 Z. B. eine Methode zum Konvertieren von <xref:System.Int64> sollte mit dem Namen `ToInt64`, nicht `ToLong` \(da <xref:System.Int64> ist eine CLR\-Name für die c\#\-bestimmten Alias `long`\). Die folgende Tabelle zeigt einige Basisdatentypen, die mit der CLR\-Typnamen \(sowie die zugehörigen Typnamen für c\#, Visual Basic und C\+\+\).  
  
|C\#|Visual Basic|C\+\+|CLR|  
|---------|------------------|-----------|---------|  
|**sbyte**|**SByte**|**char**|**SByte**|  
|**byte**|**Byte**|**unsigned char**|**Byte**|  
|**short**|**Kurz**|**short**|**Int16**|  
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|  
|**int**|**Ganze Zahl**|**int**|**Int32**|  
|**uint**|**UInt32**|**unsigned int**|**UInt32**|  
|**long**|**Long**|**\_\_int64**|**Int64**|  
|**ulong**|**UInt64**|**unsigned \_\_int64**|**UInt64**|  
|**float**|**Single**|**float**|**Single**|  
|**double**|**Double**|**double**|**Double**|  
|**bool**|**Boolesch**|**bool**|**Boolesch**|  
|**char**|**Char**|**wchar\_t**|**Char**|  
|**string**|**Zeichenfolge**|**Zeichenfolge**|**Zeichenfolge**|  
|**object**|**Objekt**|**Objekt**|**Objekt**|  
  
 **✓ führen**  verwenden Sie einen allgemeinen Namen, z. B. `value` oder `item`, anstatt wiederholt den Typnamen in den seltenen Fällen, wenn ein Bezeichner keine semantische Bedeutung hat und der Typ des Parameters nicht wichtig ist.  
  
## Benennen die neue Versionen von vorhandenen APIs  
 **✓ führen** einen Namen wie die alte API verwenden, wenn Sie neue Versionen einer vorhandenen API zu erstellen.  
  
 Dadurch wird um die Beziehung zwischen der APIs zu markieren.  
  
 **✓ führen** lieber ein Suffix anstelle ein Präfix an, dass eine neue Version einer vorhandenen API hinzufügen.  
  
 Dies hilft beim Durchsuchen der Dokumentation der Ermittlung oder mithilfe von Intellisense. Die alte Version der API wird nahe der neuen APIs organisiert werden, da die meisten Browser und Intellisense Bezeichner in alphabetischer Reihenfolge angezeigt.  
  
 **✓ ggf.** mit einer völlig neuen, aber sinnvoll\-ID, statt ein Suffix oder Präfix hinzufügen.  
  
 **✓ führen** ein numerisches Suffix an eine neue Version einer vorhandenen API, insbesondere wenn der vorhandene Name der API der einzige Name, die sinnvoll ist ist \(d. h., wenn es sich um einen Industriestandard handelt\) und jede sinnvolle hinzufügen Suffix \(oder Ändern des Namens\) keine geeignete Option ist verwenden.  
  
 **X nicht** verwenden die "Ex" \(oder eine ähnliche\)\-Suffix für einen Bezeichner zur Unterscheidung von einer früheren Version derselben API.  
  
 **✓ führen** verwenden Sie das Suffix "64", bei der Einführung von Versionen der APIs, die auf einer 64\-Bit\-Ganzzahl \(lange ganze Zahl\) anstelle von 32\-Bit\-Ganzzahl verwendet werden. Sie müssen nur so vorgehen, wenn die vorhandene 32\-Bit\-API vorhanden ist. Führen Sie es für neue APIs mit nur einer 64\-Bit\-Version.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)