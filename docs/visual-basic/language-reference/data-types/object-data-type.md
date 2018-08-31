---
title: Objekt-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 94d3ddcf71194eb69a2d26bcdf549aaf693e46e6
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43255705"
---
# <a name="object-data-type"></a>Object Data Type
Enthält die Adressen, die auf Objekte verweisen. Sie können den Verweistyp (Zeichenfolge, Array, Klasse oder Schnittstelle) zuweisen, um eine `Object` Variable. Ein `Object` Variablen finden Sie auch die Daten eines beliebigen Werttyps (numerisch, `Boolean`, `Char`, `Date`, Struktur oder Enumeration).  
  
## <a name="remarks"></a>Hinweise  
 Die `Object` -Datentyp kann auf Daten eines beliebigen Datentyps, einschließlich Objektinstanzen der Anwendung erkannt zeigen. Verwendung `Object` , wenn Sie nicht zur Kompilierzeit wissen welchen Datentyp die Variable möglicherweise zeigen Sie auf.  
  
 Der Standardwert von `Object` ist `Nothing` (ein null-Verweis).  
  
## <a name="data-types"></a>Datentypen  
 Sie können eine Variable, eine Konstante oder ein Ausdruck eines beliebigen Datentyps, Zuweisen einer `Object` Variable. Um zu bestimmen, den Datentyp einer `Object` -Variable aktuell verweist, können Sie mit der <xref:System.Type.GetTypeCode%2A> -Methode der der <xref:System.Type?displayProperty=nameWithType> Klasse. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 Die `Object` Datentyp ein Verweistyp ist. Visual Basic jedoch behandelt eine `Object` -Variable als einen Werttyp, wenn sie auf die Daten eines Werttyps verweist.  
  
## <a name="storage"></a>Speicher  
 Beliebige Datentyp verweist, eine `Object` sind keine enthalten dem Datenwert selbst, sondern stattdessen ein Zeiger auf den Wert. Sie verwendet stets die vier Bytes im Arbeitsspeicher des Computers, aber dies schließt nicht den Speicher für die Daten, die den Wert der Variablen darstellt. Aufgrund der Code, der den Zeiger verwendet, um die Daten zu suchen `Object` Variablen, die Werttypen sind etwas langsamer als explizit typisierte Variablen zugreifen.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Interop-Überlegungen.** Wenn Sie anbinden, Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen müssen bedenken, dass Zeigertypen in anderen Umgebungen nicht mit den Visual Basic kompatibel sind `Object` Typ.  
  
-   **Leistung:** Eine Variable, die Sie deklarieren, mit der `Object` flexibel genug, um einen Verweis auf ein Objekt enthalten ist. Jedoch beim Aufrufen einer Methode oder Eigenschaft auf eine solche Variable immer fallen *späte Bindung* (Laufzeit). Um zu erzwingen *frühe Bindung* (zum Zeitpunkt der Kompilierung) und eine bessere Leistung, deklarieren Sie die Variable mit einem bestimmten Klassennamen oder in der bestimmten Datentyp umzuwandeln.  
  
     Beim Deklarieren einer Objektvariablen, versuchen Sie es an einen bestimmten Klassentyp, z.B. <xref:System.OperatingSystem>, anstatt die generalisierte `Object` Typ. Verwenden Sie außerdem die spezifischste Klasse verfügbar sind, z. B. <xref:System.Windows.Forms.TextBox> anstelle von <xref:System.Windows.Forms.Control>, sodass Sie dessen Eigenschaften und Methoden zugreifen können. In der Regel können Sie die **Klassen** Liste der **Objektkatalog** verfügbaren Klassennamen zu finden.  
  
-   **Erweiternde.** Alle Datentypen und alle Verweistypen werden erweitert, um die `Object` -Datentyp. Dies bedeutet, Sie können einen beliebigen Typ zu konvertieren `Object` unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
     Allerdings, wenn die Konvertierung zwischen Werttypen und `Object`, Visual Basic führt Operationen mit Bezeichnung *Boxing* und *unboxing*, die Ausführung langsamer stellen.  
  
-   **Typzeichen.** `Object` hat kein literal-Typzeichen oder Bezeichner-Typzeichen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Object?displayProperty=nameWithType> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht eine `Object` Variable, die auf eine Objektinstanz verweisen.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Object>  
 [Datentypen](../../../visual-basic/language-reference/data-types/index.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Gewusst wie: Bestimmen der Gleichheit zweier Objekte](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
