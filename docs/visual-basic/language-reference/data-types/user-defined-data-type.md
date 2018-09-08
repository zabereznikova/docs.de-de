---
title: Den benutzerdefinierten Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 1dac93145b6e11a0d149f03b43e1e0b28b770925
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185531"
---
# <a name="user-defined-data-type"></a>Benutzerdefinierter Datentyp
Enthält Daten in einem Format, die Sie definieren. Die `Structure` -Anweisung definiert das Format.  
  
 Frühere Versionen von Visual Basic unterstützt den benutzerdefinierten Typ (UDT). Die aktuelle Version erweitert den UDT einen *Struktur*. Eine Struktur ist eine Verkettung aus einem oder mehreren *Mitglieder* verschiedener Datentypen. Visual Basic behandelt eine Struktur als einzelne Einheit, jedoch auch einzeln seine Member zugreifen können.  
  
## <a name="remarks"></a>Hinweise  
 Definieren Sie und verwenden Sie einen Datentyp für die Struktur aus, wenn verschiedene Datentypen in einer einzigen Einheit kombiniert werden sollen, oder wenn keines der elementare Datentypen Ihre Anforderungen erfüllen.  
  
 Der Standardwert eines Datentyps für die Struktur besteht aus der Kombination der Standardwerte der einzelnen Elemente.  
  
## <a name="declaration-format"></a>Deklaration-Format  
 Eine Structure-Deklaration beginnt mit der [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) und endet mit dem `End Structure` Anweisung. Die `Structure` -Anweisung gibt den Namen der Struktur, die auch der Bezeichner des Datentyps ist, wird die Struktur definiert. Andere Teile des Codes können diesen Bezeichner verwenden, um zu deklarieren, dass die Variablen, Parameter und Funktion Rückgabewerte von dieser Struktur den Datentyp.  
  
 Die Deklarationen zwischen der `Structure` und `End Structure` Anweisungen definieren, die Member der Struktur.  
  
## <a name="member-access-levels"></a>Zugriffsebenen für Member  
 Deklarieren Sie jeden Member mit einem [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md) oder eine Anweisung, die Zugriffsebene, wie z. B. angibt [öffentliche](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../visual-basic/language-reference/modifiers/private.md). Bei Verwendung einer `Dim` -Anweisung, die als Zugriffsebene standardmäßig öffentlich.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Die Arbeitsspeichernutzung.** Wie bei allen zusammengesetzten Datentypen können Sie den gesamten Speicherverbrauch auch bei Strukturen nicht dadurch zuverlässig berechnen, indem Sie die nominalen Speicherbelegungen ihrer Member addieren. Darüber hinaus können Sie nicht davon ausgehen, dass die Member im Speicher in derselben Reihenfolge wie in der Deklaration angeordnet sind. Wenn Sie das Speicherlayout einer Struktur steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut auf die `Structure`-Anweisung anwenden.  
  
-   **Interop-Überlegungen.** Wenn die Komponenten, die nicht für .NET Framework geschrieben wurden verbunden sind, strukturieren z. B. Automatisierungs- oder COM-Objekte, denken Sie daran, dass benutzerdefinierte Typen in anderen Umgebungen nicht kompatibel mit Visual Basic sind Typen.  
  
-   **Erweiternde.** Es ist keine automatische Konvertierung zu oder von beliebigen Datentyps der Struktur. Sie können die Konvertierungsoperatoren definieren, bei der Struktur mit der [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md), und Sie können jeden Konvertierungsoperator sein deklarieren `Widening` oder `Narrowing`.  
  
-   **Typzeichen.** Struktur-Datentypen haben keine literal-Typzeichen oder Bezeichner-Typzeichen.  
  
-   **Framework-Typ.** Es gibt keinen entsprechenden Typ in .NET Framework. Alle Strukturen erben von der .NET Framework-Klasse <xref:System.ValueType?displayProperty=nameWithType>, aber keine einzelne Struktur entspricht <xref:System.ValueType?displayProperty=nameWithType>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Gliederung der Deklaration einer Struktur.  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ValueType>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [Datentypen](../../../visual-basic/language-reference/data-types/index.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
