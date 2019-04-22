---
title: Effiziente Verwendung von Datentypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 0b517bca3a9e296eb891e30df91c1d32eb357432
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830122"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Effiziente Verwendung von Datentypen (Visual Basic)
Nicht deklarierte Variablen und Variablen, die ohne einen Datentyp zugewiesen sind die `Object` -Datentyp. Dies erleichtert es, Programme zu schreiben, schnell, aber es kann dazu führen, dass sie langsamer ausgeführt.  
  
## <a name="strong-typing"></a>Starke Typisierung  
 Die Angabe von Datentypen für alle Variablen wird bezeichnet als *starke Typisierung*. Mit starker Typisierung hat mehrere Vorteile:  
  
-   Sie können IntelliSense-Unterstützung für Variablen. Dadurch können Sie die Eigenschaften und andere Member anzeigen, während der Eingabe im Code.  
  
-   Es nutzt die Vorteile der typüberprüfung zur Compiler. Anweisungen, die zur Laufzeit aufgrund von Fehlern wie z. B. Überlauf möglich abzufangen. Es fängt auch Aufrufe von Methoden für Objekte, die diese nicht unterstützen.  
  
-   Es führt zu einer schnelleren Ausführung Ihres Codes.  
  
## <a name="most-efficient-data-types"></a>Die effizienteste-Datentypen  
 Für Variablen, die niemals Bruchzahlen enthalten, werden die ganzzahligen Datentypen effizienter als die nicht ganzzahligen Typen. In Visual Basic `Integer` und `UInteger` die effizientesten numerischen Typen sind.  
  
 Für Bruchzahlen `Double` der effizienteste Datentyp ist, da die Prozessoren auf den aktuellen Plattformen Operationen mit Gleitkommazahlen mit doppelter Genauigkeit ausführen. Allerdings Vorgänge mit `Double` sind nicht so schnell wie bei ganzzahligen Typen wie z. B. `Integer`.  
  
## <a name="specifying-data-type"></a>Angeben eines Datentyps  
 Verwenden der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) zum Deklarieren einer Variablen eines bestimmten Typs. Können Sie gleichzeitig ihre Zugriffsebene angeben, mit der [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselwort, wie in der folgende Beispiel.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>Zeichen-Konvertierung  
 Die `AscW` und `ChrW` Funktionen, die im Unicode-Format verwendet werden. Verwenden Sie diese vorzuziehen, `Asc` und `Chr`, die müssen in und aus Unicode-übersetzen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Numerische Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense)
