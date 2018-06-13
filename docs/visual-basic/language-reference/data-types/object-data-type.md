---
title: Object Data Type
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
ms.openlocfilehash: e9b1da5a88c12e0d883c3afe63be98c3fa3e9173
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591620"
---
# <a name="object-data-type"></a>Object Data Type
Enthält die Adressen, die auf Objekte verweisen. Sie können Verweistyp (Zeichenfolge, Array, Klasse oder Schnittstelle) zuweisen, um eine `Object` Variable. Ein `Object` Variable kann auch auf Daten mit einem beliebigen Werttyp verweisen (numeric, `Boolean`, `Char`, `Date`, Struktur oder Enumeration).  
  
## <a name="remarks"></a>Hinweise  
 Die `Object` -Datentyp kann auf Daten eines beliebigen Datentyps, einschließlich jede Objektinstanz, die die Anwendung erkennt zeigen. Verwendung `Object` , wenn Sie nicht zur Kompilierzeit wissen welchen Datentyp die Variable möglicherweise zeigen Sie auf.  
  
 Der Standardwert von `Object` ist `Nothing` (ein null-Verweis).  
  
## <a name="data-types"></a>Datentypen  
 Sie können eine Variable, eine Konstante oder ein Ausdruck eines beliebigen Datentyps zum Zuweisen einer `Object` Variable. Zum Ermitteln des Datentyps einer `Object` Variable aktuell verweist, können Sie mithilfe der <xref:System.Type.GetTypeCode%2A> Methode der <xref:System.Type?displayProperty=nameWithType> Klasse. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 Die `Object` -Datentyp ist ein Verweistyp. Visual Basic behandelt jedoch eine `Object` -Variable als ein Werttyp, wenn sie auf Daten eines Werttyps verweist.  
  
## <a name="storage"></a>Speicher  
 Der Datentyp verweist, eine `Object` Variable enthält nicht dem Datenwert selbst, sondern einen Zeiger auf den Wert. Es verwendet vier Bytes immer im Arbeitsspeicher des Computers, aber dies schließt nicht den Speicher für die Daten, die den Wert der Variablen darstellt. Aufgrund der Code, der den Zeiger verwendet wird, um die Daten zu suchen `Object` -Variablen, die Werttypen sind etwas langsamer als explizit typisierte Variablen zugreifen.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Interop-Überlegungen.** Wenn Sie Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen Datenbreite sollten Sie bedenken, dass Zeigertypen in anderen Umgebungen nicht mit Visual Basic kompatibel sind `Object` Typ.  
  
-   **Leistung:** Eine Variable, die Sie deklarieren die `Object` flexibel genug, um einen Verweis auf ein beliebiges Objekt enthalten ist. Jedoch, wenn Sie eine Methode oder Eigenschaft für eine solche Variable aufrufen, immer anfallen *späte Bindung* (Laufzeit). Gezwungen *frühe Bindung* (zum Zeitpunkt der Kompilierung) und zu einer besseren Leistung, deklarieren Sie die Variable mit einem bestimmten Klassennamen, oder es in den betreffenden Datentyp umwandeln.  
  
     Wenn Sie eine Objektvariable deklarieren, verwenden Sie beispielsweise einen bestimmten Klassentyp versucht <xref:System.OperatingSystem>, anstatt das generalisierte `Object` Typ. Verwenden Sie zudem die spezifischste Klasse verfügbar sind, z. B. <xref:System.Windows.Forms.TextBox> anstelle von <xref:System.Windows.Forms.Control>, sodass Sie die Eigenschaften und Methoden zugreifen können. In der Regel können Sie die **Klassen** in Liste der **Objektkatalog** verfügbaren Klassennamen gefunden.  
  
-   **Widening.** Alle Datentypen und alle Verweistypen erweitert werden, um die `Object` -Datentyp. Dies bedeutet, Sie können einen beliebigen Typ zu konvertieren `Object` ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
     Allerdings, wenn die Konvertierung zwischen Werttypen und `Object`, Visual Basic führt Vorgänge aufgerufen *Boxing* und *unboxing*, die Ausführung verlangsamt bilden.  
  
-   **Typzeichen.** `Object` hat kein literal-Typzeichen oder Bezeichner-Typzeichen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Object?displayProperty=nameWithType> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht eine `Object` Variable verweist auf eine Objektinstanz.  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Object>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Gewusst wie: Bestimmen der Gleichheit zweier Objekte](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
