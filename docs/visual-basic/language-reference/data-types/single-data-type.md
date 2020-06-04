---
title: Single-Datentyp
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: ecb0f5f6416a2dd4ddd6888cb80ed3ac11ee58df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415530"
---
# <a name="single-data-type-visual-basic"></a>Single-Datentyp (Visual Basic)

Enthält signierte IEEE 32-Bit (4-Byte)-Gleit Komma Zahlen mit einfacher Genauigkeit, die den Wert from-3.4028235 e + 38 bis- -1 401298E e-45 für negative Werte und von -1 401298E e-45 bis 3.4028235 e + 38 für positive Werte enthalten. Zahlen mit einfacher Genauigkeit speichern eine Näherung einer reellen Zahl.  
  
## <a name="remarks"></a>Bemerkungen  

 Verwenden Sie den- `Single` Datentyp, um Gleit Komma Werte zu enthalten, die nicht die vollständige Daten Breite von erfordern `Double` . In einigen Fällen können die Common Language Runtime Ihre `Single` Variablen eng zusammenpacken und den Speicherverbrauch verbrauchen.  
  
 Der Standardwert von `Single` lautet 0.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
- **Präziser.** Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen bei bestimmten Vorgängen führen, wie z. b. Werte Vergleich und `Mod` Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
- **Tet.** Der- `Single` Datentyp wird zu erweitert `Double` . Dies bedeutet, dass Sie `Single` in konvertieren können, `Double` ohne dass ein Fehler auftritt <xref:System.OverflowException?displayProperty=nameWithType> .  
  
- **Nachfolgende Nullen.** Die Gleit Komma Datentypen verfügen über keine interne Darstellung von nachfolgenden 0 Zeichen. Sie unterscheiden z. b. nicht zwischen 4,2000 und 4,2. Folglich werden nachfolgende 0 Zeichen nicht angezeigt, wenn Sie Gleit Komma Werte anzeigen oder drucken.  
  
- **Geben Sie Zeichen ein.** Durch Anhängen des Literaltypzeichens `F` an ein Literal wird der `Single`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `!` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Single`-Datentyp erzwungen.  
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Single?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Single?displayProperty=nameWithType>
- [Datentypen](index.md)
- [Decimal-Datentyp](decimal-data-type.md)
- [Double-Datentyp](double-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
