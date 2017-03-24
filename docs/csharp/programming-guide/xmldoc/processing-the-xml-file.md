---
title: "Verarbeiten der XML-Datei (C#&#160;Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "XML [C#], Verarbeiten"
  - "XML-Verarbeitung [C#]"
ms.assetid: 60c71193-9dac-4cd3-98c5-100bd0edcc42
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Verarbeiten der XML-Datei (C#&#160;Programmierhandbuch)
Für jedes Konstrukt, das zum Generieren von Dokumentation gekennzeichnet ist, wird vom Compiler eine ID\-Zeichenfolge generiert.  \(Weitere Informationen darüber, wie Code mit Tags versehen werden kann, finden Sie unter [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md).\) Das Konstrukt wird von der ID\-Zeichenfolge eindeutig identifiziert.  Programme, von denen die XML\-Datei verarbeitet wird, können die ID\-Zeichenfolge einsetzen, um das entsprechende .NET Framework\-Metadaten\-\/Reflektionselement zu identifizieren, auf das die Dokumentation angewendet werden kann.  
  
 Die XML\-Datei enthält keine hierarchische Darstellung des Codes. Es handelt sich um eine unstrukturierte Liste mit einer generierten ID für jedes Element.  
  
 Die folgenden Regeln werden vom Compiler beim Generieren der ID\-Zeichenfolgen beachtet:  
  
-   Die Zeichenfolge darf keinen Leerraum enthalten.  
  
-   Der erste Teil der ID\-Zeichenfolge kennzeichnet die Art des zu identifizierenden Members durch ein einzelnes Zeichen, gefolgt von einem Doppelpunkt.  Die folgenden Membertypen werden verwendet:  
  
    |Zeichen|Beschreibung|  
    |-------------|------------------|  
    |N|\-Namespace<br /><br /> Einem Namespace können keine Dokumentationskommentare hinzugefügt werden. Falls unterstützt, können jedoch **cref**\-Verweise hinzugefügt werden.|  
    |T|Typ: Klasse, Schnittstelle, Struktur, Auflistung, Delegat|  
    |F|Feld|  
    |P|Eigenschaft, einschließlich Indexern oder anderer indizierter Eigenschaften.|  
    |M|Methode \(einschließlich spezieller Methoden wie Konstruktoren, Operatoren usw.\)|  
    |E|event|  
    |\!|Fehlerzeichenfolge<br /><br /> Der verbleibende Teil der Zeichenfolge enthält Fehlerinformationen.  Vom C\#\-Compiler werden Fehlerinformationen für Links, die nicht aufgelöst werden können, erstellt.|  
  
-   Beim zweiten Teil der Zeichenfolge handelt es sich um den vollqualifizierten Namen eines Elements, beginnend mit dem Namespace\-Stammverzeichnis.  Der Name des Elements, der bzw. die einschließende\(n\) Typ\(en\) und der Namespace sind durch Punkte getrennt.  Wenn der Name des Elements selbst Punkte enthält, werden sie durch ein Nummernzeichen \(**\#**\) ersetzt.  Es wird vorausgesetzt, dass kein Element direkt im Namen ein Nummernzeichen enthält.  Der vollqualifizierte Name des String\-Konstruktors würde beispielsweise "System.String.\#ctor" lauten.  
  
-   Wenn es sich bei Eigenschaften und Methoden um Argumente der Methode handelt, folgt die in Klammern eingeschlossene Argumentliste.  Wenn keine Argumente vorhanden sind, werden keine Klammern verwendet.  Die Argumente werden durch Kommas voneinander getrennt.  Die Codierung jedes Arguments erfolgt genauso wie die Codierung in einer .NET Framework\-Signatur:  
  
    -   Basistypen.  Reguläre Typen, **ELEMENT\_TYPE\_CLASS** oder **ELEMENT\_TYPE\_VALUETYPE**, werden als vollqualifizierter Name des Typs repräsentiert.  
  
    -   Systeminterne Typen, z. B. ELEMENT\_TYPE\_I4, ELEMENT\_TYPE\_OBJECT, ELEMENT\_TYPE\_STRING, ELEMENT\_TYPE\_TYPEDBYREF.  und ELEMENT\_TYPE\_VOID\) werden als vollqualifizierter Name des entsprechenden vollständigen Typs repräsentiert.  Als Beispiel sei hier System.Int32 oder System.TypedReference aufgeführt.  
  
    -   **ELEMENT\_TYPE\_PTR** wird als \*, das auf den geänderten Typ folgt, repräsentiert.  
  
    -   **ELEMENT\_TYPE\_PTR** wird als @, das auf den geänderten Typ folgt, repräsentiert.  
  
    -   **ELEMENT\_TYPE\_PTR** wird als ^, das auf den geänderten Typ folgt, repräsentiert.  Dies wird nie vom C\#\-Compiler generiert.  
  
    -   ELEMENT\_TYPE\_CMOD\_REQ wird als '&#124;' mit nachstehendem vollqualifizierten Namen der Modifiziererklasse repräsentiert, das auf den geänderten Typ folgt.  Dies wird nie vom C\#\-Compiler generiert.  
  
    -   ELEMENT\_TYPE\_CMOD\_OPT wird als '\!' mit nachstehendem vollqualifizierten Namen der Modifiziererklasse repräsentiert, das auf den geänderten Typ folgt.  
  
    -   **ELEMENT\_TYPE\_SZARRAY** wird als \[\], das auf den Elementtyp des Arrays folgt, repräsentiert.  
  
    -   **ELEMENT\_TYPE\_GENERICARRAY** wird als \[?\], das auf den Elementtyp des Arrays folgt, repräsentiert.  Dies wird nie vom C\#\-Compiler generiert.  
  
    -   ELEMENT\_TYPE\_ARRAY wird als \[*lowerbound*:`size`,*lowerbound*:`size`\] repräsentiert, wobei die Anzahl der Kommas durch Rang \- 1 berechnet wird und die untere Grenze sowie die Größe jeder Dimension, sofern bekannt, dezimal repräsentiert werden.  Wenn die untere Grenze oder die Größe nicht angegeben ist, wird sie einfach ausgelassen.  Wenn die untere Grenze und die Größe für eine bestimmte Dimension ausgelassen werden, kann der **:** ebenfalls ausgelassen werden.  \[1:,1:\] ist beispielsweise ein zweidimensionales Array mit 1 als unterer Grenze und nicht angegebenen Größen.  
  
    -   ELEMENT\_TYPE\_FNPTR wird als "\=FUNC:`type`\(*signature*\)" repräsentiert, wobei `type` den Rückgabetyp darstellt und es sich bei *signature* um die Argumente der Methode handelt.  Sind keine Argumente vorhanden, werden keine Klammern verwendet.  Dies wird nie vom C\#\-Compiler generiert.  
  
     Die folgenden Signaturkomponenten werden nicht repräsentiert, weil sie nicht zur Unterscheidung überladener Methoden verwendet werden:  
  
    -   Aufrufkonvention  
  
    -   Rückgabetyp  
  
    -   ELEMENT\_TYPE\_SENTINEL  
  
-   Nur für Konvertierungsoperatoren, op\_Implicit und op\_Explicit, wird der Rückgabewert der Methode als "~" gefolgt vom Rückgabewert codiert, wie weiter oben gezeigt.  
  
-   Bei generischen Typen folgt auf den Namen des Typs ein Graviszeichen und dann eine Zahl, die die Anzahl der generischen Typparameter angibt.  Beispiel:  
  
     `<member name="T:SampleClass`2">` ist das Tag für einen Typ, der als `public class SampleClass\<T, U>` definiert wird.  
  
     Bei Methoden, die generische Typen als Parameter verwenden, werden die generischen Parameter des Typs als Zahlen mit vorangestelltem Graviszeichen angegeben \(z. B. \`0,\`1\).  Jede Zahl stellt eine bei 0 beginnende Arraynotation für die generischen Parameter des Typs dar.  
  
## Beispiele  
 In den folgenden Beispielen wird eine mögliche Generierung von ID\-Zeichenfolgen für eine Klasse und ihre Member gezeigt:  
  
 [!code-cs[csProgGuidePointers#21](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/processing-the-xml-file_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML\-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)