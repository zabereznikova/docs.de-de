---
title: Übersicht über die .NET-Klassenbibliothek
description: Informationen zur .NET-Klassenbibliothek. .NET-APIs enthalten Klassen, Schnittstellen, Delegate und Werttypen, die den Zugriff auf Systemfunktionen ermöglichen.
ms.date: 02/08/2018
helpviewer_keywords:
- classes [.NET], library overview
- .NET, library overview
- class objects value type
- naming conventions [.NET]
- types, .NET
- user-defined types
- Visual Basic, data types
- data types [.NET], C++
- Visual C#, data types
- libraries, .NET
- data types [.NET], F#
- System namespace
- F#, data types
- .NET, class library
- type system [.NET]
- data types [.NET]
- value types
- data types [.NET], Visual Basic
- Common Language Specification
- namespaces [.NET]
- floating point value type
- class library [.NET]
- CLS
- logical value type
- built-in types
- namespaces [.NET], about namespaces
- Visual C++, data types
- members [.NET], type
- data types [.NET], C#
- integer value type
- base types, class library
ms.assetid: 7e4c5921-955d-4b06-8709-101873acf157
ms.openlocfilehash: 44a46db4fa7ebf6dd5802cc07e7d18744c72ad68
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831259"
---
# <a name="net-class-library-overview"></a>Übersicht über die .NET-Klassenbibliothek

.NET-APIs enthalten Klassen, Schnittstellen, Delegate und Werttypen, die den Entwicklungsprozess beschleunigen und optimieren und den Zugriff auf Systemfunktionen ermöglichen. .NET Framework gewährleistet durch überwiegend CLS-kompatible Typen Interoperabilität zwischen verschiedenen Sprachen und kann daher in jeder Programmiersprache verwendet werden, deren Compiler der CLS (Common Language Specification) entspricht.  
  
Die .NET-Typen bilden die Grundlage für den Entwurf von Anwendungen, Komponenten und Steuerelementen in .NET. .NET umfasst Typen zur Ausführung folgender Funktionen:  
  
- Darstellung von Basisdatentypen und -ausnahmen  
  
- Kapseln von Datenstrukturen  
  
- E/A-Operationen  
  
- Zugriff auf Informationen über geladene Typen  
  
- Aufrufen von .NET-Sicherheitsüberprüfungen  
  
- Datenzugriff und Bereitstellen einer eigenständigen Client-GUI sowie einer servergesteuerten Client-GUI  
  
In .NET stehen neben zahlreichen Schnittstellen abstrakte und konkrete (nicht abstrakte) Klassen zur Verfügung. Sie können die konkreten Klassen unverändert verwenden oder in vielen Fällen eigene Klassen von diesen ableiten. Sie können entweder eine Klasse erstellen, die die Schnittstelle implementiert, oder eine Klasse von einer der .NET-Klassen ableiten, die die Schnittstelle implementiert, um die Funktionen einer Schnittstelle zu verwenden.  
  
## <a name="naming-conventions"></a>Namenskonventionen

 Für .NET-Typen wird ein Benennungsschema mit Punktsyntax verwendet, das der hierarchischen Struktur entspricht. Bei diesem Verfahren werden verwandte Typen in Namespaces zusammengefasst, wodurch Suchvorgänge und Verweise vereinfacht werden. Der erste Teil des vollständigen Namens, bis zum letzten Punkt, gibt den Namen des Namespaces wieder. Der letzte Teil ist der Name des Typs. `System.Collections.Generic.List<T>` stellt beispielsweise den Typ `List<T>` dar, der zum Namespace `System.Collections.Generic` gehört. Die Typen in <xref:System.Collections.Generic> können mit generischen Sammlungen verwendet werden.  
  
 Dieses Benennungsschema erleichtert es Entwicklern von Bibliotheken, Erweiterungen für .NET zu entwerfen, um hierarchische Typengruppen zu erstellen und diese konsistent und aussagekräftig zu benennen. Außerdem können Typen nach ihrem vollständigen Namen (d. h. ihrem Namespace und Typnamen) eindeutig identifiziert werden, wodurch Konflikte bei Typnamen vermieden werden. Von Entwicklern von Bibliotheken wird erwartet, dass sie sich beim Erstellen der Namen für eigene Namespaces an die nachstehende Konvention halten:  
  
 *CompanyName*.*TechnologyName*  
  
 Der Namespace `Microsoft.Word` entspricht beispielsweise dieser Richtlinie.  
  
 Für das Erstellen und Dokumentieren von Klassenbibliotheken empfiehlt sich ein Benennungsschema, bei dem verwandte Typen in Namespaces zusammengefasst werden. Dieses wirkt sich jedoch nicht auf Sichtbarkeit, Memberzugriff, Vererbung, Sicherheit oder Bindung aus. Ein Namespace kann von mehreren Assemblys verwendet werden, und eine einzelne Assembly kann Typen aus mehreren Namespaces enthalten. Die Assembly stellt die formale Struktur für Versionsinformationen, Bereitstellung, Sicherheit, Ladevorgänge und Sichtbarkeit in der Common Language Runtime bereit.  
  
 Weitere Informationen über Namespaces und Typennamen finden Sie unter [Allgemeines Typsystem](base-types/common-type-system.md).  
  
## <a name="system-namespace"></a>System-Namespace

 Beim <xref:System>-Namespace handelt es sich um den Stammnamespace für Basistypen in .NET. Dieser Namespace beinhaltet Klassen, die die von allen Anwendungen verwendeten Basisdatentypen darstellen: <xref:System.Object> (der Stamm der Vererbungshierarchie), <xref:System.Byte>, <xref:System.Char>, <xref:System.Array>, <xref:System.Int32>, <xref:System.String> usw. Viele dieser Typen entsprechen den primitiven Datentypen, die in den verschiedenen Programmiersprachen verwendet werden. Wenn Sie Code mithilfe von .NET-Typen schreiben, können Sie anstelle eines erwarteten Basisdatentyps von .NET auch das entsprechende Schlüsselwort der verwendeten Programmiersprache angeben.  
  
 In der folgenden Tabelle sind die in .NET verfügbaren Basistypen mit einer Kurzbeschreibung der einzelnen Typen und den entsprechenden Typen in Visual Basic, C#, C++ und F# aufgeführt.  
  
|Kategorie|Klassenname|Beschreibung|Datentyp in Visual Basic|Datentyp in C#|C++/CLI-Datentyp|F#-Datentyp|  
|--------------|----------------|-----------------|----------------------------|-------------------|---------------------|-----------------------|  
|Ganze Zahl|<xref:System.Byte>|Eine 8-Bit-Ganzzahl ohne Vorzeichen.|**Byte**|**byte**|**unsigned char**|**byte**|  
||<xref:System.SByte>|Eine 8-Bit-Ganzzahl mit Vorzeichen.<br /><br /> Nicht CLS-kompatibel.|**SByte**|**sbyte**|**char**<br /> - oder -<br /> **char** **mit Vorzeichen**|**sbyte**|  
||<xref:System.Int16>|Eine 16-Bit-Ganzzahl mit Vorzeichen.|**Short**|**short**|**short**|**int16**|  
||<xref:System.Int32>|Eine 32-Bit-Ganzzahl mit Vorzeichen.|**Integer**|**int**|**int**<br /><br /> - oder -<br /><br /> **long**|**int**|  
||<xref:System.Int64>|Eine 64-Bit-Ganzzahl mit Vorzeichen.|**Long**|**long**|**__int64**|**int64**|  
||<xref:System.UInt16>|Eine 16-Bit-Ganzzahl ohne Vorzeichen.<br /><br /> Nicht CLS-kompatibel.|**UShort**|**ushort**|**unsigned short**|**uint16**|  
||<xref:System.UInt32>|Eine 32-Bit-Ganzzahl ohne Vorzeichen.<br /><br /> Nicht CLS-kompatibel.|**UInteger**|**uint**|**unsigned int**<br /> - oder -<br /> **unsigned long**|**uint32**|  
||<xref:System.UInt64>|Eine 64-Bit-Ganzzahl ohne Vorzeichen.<br /><br /> Nicht CLS-kompatibel.|**ULong**|**ulong**|**__int64 ohne Vorzeichen**|**uint64**|  
|Gleitkomma|<xref:System.Single>|Eine Gleitkommazahl einfacher Genauigkeit (32 Bit).|**Single**|**float**|**float**|**float32**<br> oder<br>**single**|  
||<xref:System.Double>|Eine Gleitkommazahl doppelter Genauigkeit (64 Bit).|**Double**|**double**|**double**|**float**<br> oder <br> **double**|  
|Logisch|<xref:System.Boolean>|Ein boolescher Wert (true oder false).|**Boolean**|**bool**|**bool**|**bool**|  
|Andere|<xref:System.Char>|Ein Unicode-Zeichen (16 Bit).|**Char**|**char**|**wchar_t**|**char**|  
||<xref:System.Decimal>|Dezimalwert (128 Bit).|**Decimal**|**decimal**|**Decimal**|**decimal**|  
||<xref:System.IntPtr>|Eine ganze Zahl mit Vorzeichen, deren Größe von der zugrunde liegenden Plattform abhängt (32-Bit-Wert auf einer 32-Bit-Plattform und 64-Bit-Wert auf einer 64-Bit-Plattform).|**IntPtr**<br /><br /> Kein integrierter Typ.|**IntPtr**<br /><br /> Kein integrierter Typ.|**IntPtr**<br /><br /> Kein integrierter Typ.|**unativeint**|  
||<xref:System.UIntPtr>|Eine ganze Zahl, deren Größe von der zugrunde liegenden Plattform abhängt (32-Bit-Wert auf einer 32-Bit-Plattform und 64-Bit-Wert auf einer 64-Bit-Plattform).<br /><br /> Nicht CLS-kompatibel.|**UIntPtr**<br /><br /> Kein integrierter Typ.|**UIntPtr**<br /><br /> Kein integrierter Typ.|**UIntPtr**<br /><br /> Kein integrierter Typ.|**unativeint**|  
||<xref:System.Object>|Der Stamm der Objekthierarchie.|**Objekt**|**object**|**Object^**|**obj**|  
||<xref:System.String>|Eine unveränderliche Zeichenfolge fester Länge mit Unicode-Zeichen.|**String**|**string**|**String^**|**string**|  
  
 Neben den Basisdatentypen umfasst der <xref:System>-Namespace mehr als 100 Klassen, die von Klassen für die Behandlung von Ausnahmen bis zu Klassen reichen, die für wesentliche Konzepte der Laufzeit vorgesehen sind, beispielsweise Anwendungsdomänen oder der Garbage Collector. Der <xref:System>-Namespace beinhaltet darüber hinaus zahlreiche Namespaces zweiter Ebene.  
  
 Verwenden Sie für weitere Informationen zu Namespaces den [.NET-API-Browser](../../api/index.md), um die .NET Framework-Klassenbibliothek zu durchsuchen. Die API-Referenzdokumentation bietet Dokumentationen zu jedem Namespace, den dazu gehörigen Typen und Membern.  
  
## <a name="see-also"></a>Siehe auch

- [Allgemeines Typsystem](base-types/common-type-system.md)
- [.NET API-Browser](../../api/index.md)
- [Übersicht](../framework/get-started/overview.md)
