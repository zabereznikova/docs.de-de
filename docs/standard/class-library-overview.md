---
title: "&#220;bersicht &#252;ber die .NET&#160;Framework-Klassenbibliothek | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework-Klassenbibliothek, Informationen über"
  - ".NET Framework, Klassenbibliothek"
  - "Basistypen, Klassenbibliothek"
  - "Integrierte Typen"
  - "Klassenbibliothek [.NET Framework]"
  - "Klassenobjekte-Werttyp"
  - "Klassen [.NET Framework], Übersicht über Bibliotheken"
  - "CLS"
  - "Common Language Specification"
  - "Datentypen [.NET Framework]"
  - "Datentypen [.NET Framework], C#"
  - "Datentypen [.NET Framework], C++"
  - "Datentypen [.NET Framework], JScript"
  - "Datentypen [.NET Framework], Visual Basic"
  - "Gleitkommazahl-Werttyp"
  - "Ganzzahliger Werttyp"
  - "JScript, Datentypen"
  - "Bibliotheken, .NET Framework-Klassenbibliothek"
  - "Logischer Werttyp"
  - "Member [.NET Framework], Typ"
  - "Namespaces [.NET Framework]"
  - "Namespaces [.NET Framework], Informationen über Namespaces"
  - "Benennungskonventionen [.NET Framework]"
  - "System-Namespace"
  - "Typsystem [.NET Framework]"
  - "Typen, .NET Framework"
  - "Benutzerdefinierte Typen"
  - "Werttypen"
  - "Visual Basic, Datentypen"
  - "Visual C#, Datentypen"
  - "Visual C++, Datentypen"
ms.assetid: 7e4c5921-955d-4b06-8709-101873acf157
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# &#220;bersicht &#252;ber die .NET&#160;Framework-Klassenbibliothek
[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] enthält Klassen, Schnittstellen und Werttypen, die den Entwicklungsprozess beschleunigen und optimieren und den Zugriff auf Systemfunktionen ermöglichen.  .NET Framework gewährleistet durch überwiegend CLS\-kompatible Typen Interoperabilität zwischen verschiedenen Sprachen und kann daher in jeder Programmiersprache verwendet werden, deren Compiler der CLS \(Common Language Specification\) entspricht.  
  
 Die in .NET Framework verfügbaren Typen bilden die Grundlage für den Entwurf von Anwendungen, Komponenten und Steuerelementen in .NET.  [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] umfasst Typen zur Ausführung folgender Funktionen:  
  
-   Darstellung von Basisdatentypen und \-ausnahmen  
  
-   Kapseln von Datenstrukturen  
  
-   E\/A\-Operationen  
  
-   Zugriff auf Informationen über geladene Typen  
  
-   Aufrufen von .NET Framework\-Sicherheitsüberprüfungen  
  
-   Datenzugriff und Bereitstellen einer eigenständigen Client\-GUI sowie einer servergesteuerten Client\-GUI  
  
 In [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stehen neben zahlreichen Schnittstellen abstrakte und konkrete \(nicht abstrakte\) Klassen zur Verfügung.  Sie können die konkreten Klassen unverändert verwenden oder eigene Klassen von ihnen ableiten.  Um auf die Funktionen einer Schnittstelle zuzugreifen, können Sie entweder eine Klasse erstellen und die entsprechende Schnittstelle in der Klasse implementieren oder eine Klasse von einer .NET Framework\-Klasse ableiten, die die Schnittstelle implementiert.  
  
## Benennungskonventionen  
 Für .NET Framework\-Typen wird ein Benennungsschema mit Punktsyntax verwendet, das der hierarchischen Struktur entspricht.  Bei diesem Verfahren werden verwandte Typen in Namespaces zusammengefasst, wodurch Suchvorgänge und Verweise vereinfacht werden.  Der erste Teil des vollständigen Namens, bis zum letzten Punkt, gibt den Namen des Namespaces wieder.  Der letzte Teil ist der Name des Typs.  **System.Collections.ArrayList** stellt z. B. den Typ **ArrayList** dar, der im Namespace **System.Collections** enthalten ist.  Die Typen in **System.Collections** werden zum Bearbeiten und Ändern von Objektauflistungen verwendet.  
  
 Dieses Benennungsschema erleichtert es Entwicklern von Bibliotheken, die Erweiterungen für [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] entwerfen, hierarchische Typengruppen zu erstellen und diese konsistent und aussagekräftig zu benennen.  Außerdem können Typen nach ihrem vollständigen Namen \(d. h. ihrem Namespace und Typnamen\) eindeutig identifiziert werden, wodurch Konflikte bei Typnamen vermieden werden.  Von Entwicklern von Bibliotheken wird erwartet, dass sie sich beim Erstellen der Namen für eigene Namespaces an die nachstehende Konvention halten:  
  
 *CompanyName*.*TechnologyName*  
  
 Der Namespace Microsoft.Word beispielsweise entspricht dieser Richtlinie.  
  
 Insbesondere für das Erstellen und Dokumentieren von Klassenbibliotheken empfiehlt sich ein Benennungsschema, bei dem verwandte Typen in Namespaces zusammengefasst werden.  Dieses wirkt sich jedoch nicht auf Sichtbarkeit, Memberzugriff, Vererbung, Sicherheit oder Bindung aus.  Ein Namespace kann von mehreren Assemblys verwendet werden, und eine einzelne Assembly kann Typen aus mehreren Namespaces enthalten.  Die Assembly stellt die formale Struktur für Versionsinformationen, Bereitstellung, Sicherheit, Ladevorgänge und Sichtbarkeit in der Common Language Runtime bereit.  
  
 Weitere Informationen über Namespaces und Typennamen finden Sie unter [Allgemeines Typsystem](../../docs/standard/base-types/common-type-system.md).  
  
## Systemnamespace  
 Beim <xref:System>\-Namespace handelt es sich um den Stammnamespace für Basistypen in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].  Dieser Namespace beinhaltet Klassen, die die von allen Anwendungen verwendeten Basisdatentypen darstellen: <xref:System.Object> \(der Stamm der Vererbungshierarchie\), <xref:System.Byte>, <xref:System.Char>, <xref:System.Array>, <xref:System.Int32>, <xref:System.String> usw.  Viele dieser Typen entsprechen den primitiven Datentypen, die in den verschiedenen Programmiersprachen verwendet werden.  Wenn Sie Code mithilfe von .NET Framework\-Typen schreiben, können Sie anstelle eines erwarteten Basisdatentyps von .NET Framework auch das entsprechende Schlüsselwort der verwendeten Sprache angeben.  
  
 In der folgenden Tabelle sind die in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] verfügbaren Basistypen mit einer Kurzbeschreibung der einzelnen Typen und den entsprechenden Typen in Visual Basic, C\#, C\+\+ und JScript aufgeführt.  
  
|Kategorie|Klassenname|Beschreibung|Datentyp in Visual Basic|Datentyp in C\#|C\+\+\-Datentyp|Datentyp in JScript|  
|---------------|-----------------|------------------|------------------------------|---------------------|---------------------|-------------------------|  
|Ganze Zahl|<xref:System.Byte>|Eine 8\-Bit\-Ganzzahl ohne Vorzeichen.|**Byte**|**byte**|**unsigned char**|**Byte**|  
||<xref:System.SByte>|Eine 8\-Bit\-Ganzzahl mit Vorzeichen.<br /><br /> Nicht CLS\-kompatibel.|**SByte**|**sbyte**|**char**<br /><br /> \- oder \-<br /><br /> **char** **mit Vorzeichen**|**SByte**|  
||<xref:System.Int16>|Eine 16\-Bit\-Ganzzahl mit Vorzeichen.|**Short**|**short**|**short**|**short**|  
||<xref:System.Int32>|Eine 32\-Bit\-Ganzzahl mit Vorzeichen.|**Ganze Zahl**|**int**|**int**<br /><br /> \- oder \-<br /><br /> **long**|**int**|  
||<xref:System.Int64>|Eine 64\-Bit\-Ganzzahl mit Vorzeichen.|**Long**|**long**|**\_\_int64**|**long**|  
||<xref:System.UInt16>|Eine 16\-Bit\-Ganzzahl ohne Vorzeichen.<br /><br /> Nicht CLS\-kompatibel.|**UShort**|**ushort**|**unsigned short**|**UInt16**|  
||<xref:System.UInt32>|Eine 32\-Bit\-Ganzzahl ohne Vorzeichen.<br /><br /> Nicht CLS\-kompatibel.|**UInteger**|**uint**|**unsigned int**<br /><br /> \- oder \-<br /><br /> **unsigned long**|**UInt32**|  
||<xref:System.UInt64>|Eine 64\-Bit\-Ganzzahl ohne Vorzeichen.<br /><br /> Nicht CLS\-kompatibel.|**ULong**|**ulong**|**unsigned \_\_int64**|**UInt64**|  
|Gleitkomma|<xref:System.Single>|Eine Gleitkommazahl einfacher Genauigkeit \(32 Bit\).|**Single**|**float**|**float**|**float**|  
||<xref:System.Double>|Eine Gleitkommazahl doppelter Genauigkeit \(64 Bit\).|**Double**|**double**|**double**|**double**|  
|Logisch|<xref:System.Boolean>|Ein boolescher Wert \(true oder false\).|**Boolean**|**bool**|**bool**|**bool**|  
|Andere|<xref:System.Char>|Ein Unicode\-Zeichen \(16 Bit\).|**Char**|**char**|**wchar\_t**|**char**|  
||<xref:System.Decimal>|Dezimalwert \(128 Bit\).|**Decimal**|**decimal**|**Decimal**|**Decimal**|  
||<xref:System.IntPtr>|Eine ganze Zahl mit Vorzeichen, deren Größe von der zugrunde liegenden Plattform abhängt \(32\-Bit\-Wert auf einer 32\-Bit\-Plattform und 64\-Bit\-Wert auf einer 64\-Bit\-Plattform\).|**IntPtr**<br /><br /> Kein integrierter Typ.|**IntPtr**<br /><br /> Kein integrierter Typ.|**IntPtr**<br /><br /> Kein integrierter Typ.|**IntPtr**|  
||<xref:System.UIntPtr>|Eine ganze Zahl, deren Größe von der zugrunde liegenden Plattform abhängt \(32\-Bit\-Wert auf einer 32\-Bit\-Plattform und 64\-Bit\-Wert auf einer 64\-Bit\-Plattform\).<br /><br /> Nicht CLS\-kompatibel.|**UIntPtr**<br /><br /> Kein integrierter Typ.|**UIntPtr**<br /><br /> Kein integrierter Typ.|**UIntPtr**<br /><br /> Kein integrierter Typ.|**UIntPtr**|  
|Klassenobjekte|<xref:System.Object>|Der Stamm der Objekthierarchie.|**Objekt**|**Objekt**|**Object\***|**Objekt**|  
||<xref:System.String>|Eine unveränderliche Zeichenfolge fester Länge mit Unicode\-Zeichen.|**Zeichenfolge**|**string**|**String\***|**Zeichenfolge**|  
  
 Neben den Basisdatentypen umfasst der <xref:System>\-Namespace mehr als 100 Klassen, die von Klassen für die Behandlung von Ausnahmen bis zu Klassen reichen, die für wesentliche Konzepte der Laufzeit vorgesehen sind, beispielsweise Anwendungsdomänen oder der Garbage Collector.  Der <xref:System>\-Namespace beinhaltet darüber hinaus zahlreiche Namespaces zweiter Ebene.  
  
 Weitere Informationen über die Namespaces finden Sie in der [.NET Framework\-Klassenbibliothek](http://go.microsoft.com/fwlink/?LinkID=227195).  In der Referenzdokumentation finden Sie eine Kurzübersicht zu jedem Namespace sowie eine formale Beschreibung aller Typen und der zugehörigen Elemente.  
  
## Siehe auch  
 [Allgemeines Typsystem](../../docs/standard/base-types/common-type-system.md)   
 [.NET Framework\-Klassenbibliothek](http://go.microsoft.com/fwlink/?LinkID=227195)   
 [Übersicht](../../docs/framework/get-started/overview.md)