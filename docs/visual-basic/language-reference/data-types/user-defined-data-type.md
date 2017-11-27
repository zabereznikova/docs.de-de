---
title: Benutzerdefinierter Datentyp
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e1876d61a2ce89b04c6e5061b868f0be365639f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="user-defined-data-type"></a>Benutzerdefinierter Datentyp
Enthält Daten in einem Format, das Sie definieren. Die `Structure` -Anweisung definiert das Format.  
  
 Frühere Versionen von Visual Basic unterstützen den benutzerdefinierten Typ (UDT). Die aktuelle Version wird den UDT erweitert eine *Struktur*. Eine Struktur ist eine Verkettung aus einem oder mehreren *Elemente* verschiedener Datentypen. Visual Basic behandelt eine Struktur als einzelne Einheit, obwohl Sie Member auch einzeln zugreifen können.  
  
## <a name="remarks"></a>Hinweise  
 Definieren Sie und verwenden Sie einen Datentyp für die Struktur, wenn Sie verschiedene Datentypen in einer einzigen Einheit kombinieren müssen, oder keines der elementare Datentypen Ihren vorstellungen.  
  
 Der Standardwert eines Datentyps Struktur besteht aus der Kombination der Standardwerte der einzelnen Membern.  
  
## <a name="declaration-format"></a>Deklaration Format  
 Eine Strukturdeklaration beginnt mit der [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) und endet mit der `End``Structure` Anweisung. Die `Structure` -Anweisung gibt den Namen der Struktur, die auch der Bezeichner des Datentyps ist die Struktur besteht im definieren. Andere Teile des Codes können diesen Bezeichner verwenden, um zu deklarieren, dass Variablen, Parameter und -Funktion zurückgegeben werden Werte, um diese Struktur den Datentyp haben.  
  
 Die Deklarationen zwischen der `Structure` und `End``Structure` Anweisungen definieren die Member der Struktur.  
  
## <a name="member-access-levels"></a>Zugriffsebenen der Member  
 Muss deklariert werden, jeden Member mit einem [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md) oder eine Anweisung, die Zugriffsebene,, wie z. B. angibt [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md), ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../visual-basic/language-reference/modifiers/private.md). Bei Verwendung einer `Dim` -Anweisung, die als Zugriffsebene standardmäßig öffentlich.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Speicherverbrauch.** Wie bei allen zusammengesetzten Datentypen können Sie den gesamten Speicherverbrauch auch bei Strukturen nicht dadurch zuverlässig berechnen, indem Sie die nominalen Speicherbelegungen ihrer Member addieren. Darüber hinaus können Sie nicht davon ausgehen, dass die Member im Speicher in derselben Reihenfolge wie in der Deklaration angeordnet sind. Wenn Sie das Speicherlayout einer Struktur steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut auf die `Structure`-Anweisung anwenden.  
  
-   **Interop-Überlegungen.** Wenn Sie Komponenten, die nicht für .NET Framework geschrieben wurden Datenbreite, strukturieren z. B. Automatisierungs- oder COM-Objekte, denken Sie daran, dass benutzerdefinierte Typen in anderen Umgebungen nicht mit Visual Basic kompatibel sind Typen.  
  
-   **Widening.** Es wird keine automatische Konvertierung zu oder von beliebigen Datentyps der Struktur. Sie können Konvertierungsoperatoren definieren, auf die Struktur mit den [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md), und Sie können jeden Konvertierungsoperator zu deklarieren `Widening` oder `Narrowing`.  
  
-   **Typzeichen.** Struktur-Datentypen haben keine literal-Typzeichen oder Bezeichner-Typzeichen.  
  
-   **Framework-Typ.** Es ist keine entsprechende Typ in .NET Framework. Alle Strukturen erben von der .NET Framework-Klasse <xref:System.ValueType?displayProperty=nameWithType>, aber keine einzelne Struktur entspricht <xref:System.ValueType?displayProperty=nameWithType>.  
  
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
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
