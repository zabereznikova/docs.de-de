---
title: "User-Defined Data Type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "UserDefined"
  - "UDT"
  - "vb.UDT"
  - "User-Defined"
  - "vb.UserDefined"
  - "vb.User-Defined"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "user-defined data types, Visual Basic"
  - "user-defined types"
  - "structures, as user-defined data types"
  - "user-defined types, Visual Basic"
  - "user-defined types, structure declaration"
  - "user-defined types, structures in Visual Basic"
  - "user-defined data types, structure declaration"
  - "data types [Visual Basic], assigning"
  - "Structure statement"
  - "data types [Visual Basic], user-defined"
  - "user-defined data types, structures in Visual Basic"
  - "user-defined data types"
  - "types [Visual Basic], user-defined"
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# User-Defined Data Type
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Enthält Daten in einem Format, das Sie definieren.  Das Format wird durch die `Structure`\-Anweisung definiert.  
  
 Frühere Versionen von Visual Basic unterstützen den benutzerdefinierten Typ \(UDT\).  In der aktuellen Version wird der UDT zu einer *Struktur* erweitert.  Strukturen sind Verkettungen mehrerer *Member* verschiedener Datentypen.  Visual Basic behandelt eine Struktur als einzelne Einheit, dennoch können Sie auch auf einzelne Member der Struktur zugreifen.  
  
## Hinweise  
 Definieren und verwenden Sie einen Structure\-Datentyp, wenn Sie verschiedene Datentypen zu einer Einheit kombinieren müssen oder wenn keiner der elementaren Datentypen Ihren Anforderungen entspricht.  
  
 Der Standardwert eines Structure\-Datentyps ergibt sich aus der Kombination der Standardwerte seiner einzelnen Member.  
  
## Deklarationsformat  
 Eine Strukturdeklaration beginnt mit der [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) und endet mit der `End` `Structure`\-Anweisung.  Die `Structure`\-Anweisung gibt den Namen der Struktur an. Dieser ist auch der Bezeichner des Datentyps, der durch die Struktur definiert wird.  Von anderen Abschnitten des Codes kann dieser Bezeichner dazu verwendet werden, um Variablen, Parameter und Rückgabewerte von Funktionen als Datentyp dieser Struktur zu deklarieren.  
  
 Die Deklarationen zwischen der `Structure`\-Anweisung und der `End` `Structure`\-Anweisung definieren die Member der Struktur.  
  
## Memberzugriffsebenen  
 Sie müssen jeden Member mit einer [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) oder einer Anweisung deklarieren, die die Zugriffsebene angibt, beispielsweise [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md) oder [Private](../../../visual-basic/language-reference/modifiers/private.md).  Wenn Sie eine `Dim`\-Anweisung verwenden, wird als Zugriffsebene standardmäßig Public festgelegt.  
  
## Programmiertipps  
  
-   **Speicherverbrauch.** Wie bei allen zusammengesetzten Datentypen können Sie den gesamten Speicherverbrauch auch bei Strukturen durch Addition der nominalen Speicherbelegungen ihrer Member nicht zuverlässig berechnen.  Darüber hinaus können Sie nicht davon ausgehen, dass die Member im Speicher in derselben Reihenfolge wie in der Deklaration angeordnet sind.  Wenn Sie das Speicherlayout einer Struktur steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>\-Attribut auf die `Structure`\-Anweisung anwenden.  
  
-   **Interop\-Überlegungen.** Wenn eine Schnittstelle mit Komponenten vorhanden ist, die nicht für .NET\-Framework geschrieben wurden \(z. B. Automatisierungs\- oder COM\-Objekte\) ist zu beachten, dass benutzerdefinierte Typen in anderen Umgebungen nicht mit Visual Basic\-Strukturtypen kompatibel sind.  
  
-   **Erweiterung.** Es gibt keine automatische Konvertierung in einen oder aus einem Strukturdatentyp.  Mit der [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md) können Sie Konvertierungsoperatoren der Struktur definieren, und Sie können jeden Konvertierungsoperator als `Widening` oder `Narrowing` deklarieren.  
  
-   **Typzeichen.** Strukturdatentypen verfügen über kein Literaltypzeichen oder Typkennzeichen.  
  
-   **Frameworktyp.** Es gibt keinen entsprechenden Typ in .NET Framework.  Alle Strukturen erben von der .NET Framework\-Klasse <xref:System.ValueType?displayProperty=fullName>, allerdings entspricht keine einzelne Struktur <xref:System.ValueType?displayProperty=fullName>.  
  
## Beispiel  
 Das folgende Beispiel zeigt die Gliederung der Deklaration einer Struktur.  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## Siehe auch  
 <xref:System.ValueType>   
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)