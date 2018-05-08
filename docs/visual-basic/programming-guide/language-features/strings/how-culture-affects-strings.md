---
title: Auswirkungen der Kultur auf Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
ms.openlocfilehash: 41fd612695fbeacbc7b53cb9e5dbf67939e73482
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Auswirkungen der Kultur auf Zeichenfolgen in Visual Basic
Diese Hilfeseite wird erläutert, wie Visual Basic kulturinformationen verwendet, zeichenfolgenkonvertierungen und Vergleiche durchführen.  
  
## <a name="when-to-use-culture-specific-strings"></a>Wenn kulturspezifische Zeichenfolgen verwenden  
 Sie sollten in der Regel verwenden kulturspezifische Zeichenfolgen für alle Daten, die angezeigt und von Benutzern zu lesen und für interne Daten für die Anwendung kulturinvariant unstrukturierte Zeichenfolgen verwenden.  
  
 Z. B. Wenn Ihre Anwendung Benutzer ein Datum als Zeichenfolge eingeben anfordert, wird erwartet, dass Benutzer Zeichenfolgen gemäß ihrer Kultur zu formatieren und die Anwendung sollte die Zeichenfolge entsprechend zu konvertieren. Wenn die Anwendung dann dieses Datum in der Benutzeroberfläche darstellt, sollten sie es in der Kultur des Benutzers bereit.  
  
 Wenn die Anwendung das Datum mit einem zentralen Server hochlädt, sollten sie die Zeichenfolge entsprechend einer bestimmten Kultur, um Verwechslungen zwischen möglicherweise verschiedene Datumsformate zu verhindern formatieren.  
  
## <a name="culture-sensitive-functions"></a>Kulturabhängigen Funktionen  
 Alle Visual Basic-zeichenfolgenkonvertierung Funktionen (mit Ausnahme von der `Str` und `Val` Funktionen) Informationen zur Kultur der Anwendung verwenden, um sicherzustellen, dass die Konvertierungen und Vergleiche für die Kultur der Anwendung geeignet sind Benutzer.  
  
 Der Schlüssel Verwendung erfolgreich zeichenfolgenkonvertierung Funktionen in Anwendungen, die auf Computern mit verschiedenen kultureinstellungen ausgeführt ist, zu verstehen, welche Funktionen eine bestimmte Kultur-Einstellung verwenden, und die aktuelle kultureinstellung verwenden. Beachten Sie, dass die Anwendung länderspezifischen Einstellungen werden standardmäßig die länderspezifischen Einstellungen des Betriebssystems geerbt werden, ein. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, und [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Die `Str` (konvertiert Zahlen in Zeichenfolgen) und `Val` (konvertiert Zeichenfolgen in Zahlen)-Funktionen verwenden Sie nicht kulturinformationen für die Anwendung bei der Konvertierung zwischen Zeichenfolgen und Zahlen. Stattdessen erkennen sie nur den Punkt (.) als gültiges Dezimaltrennzeichen. Die unterschiedliche Kulturen berücksichtigt analoge dieser Funktionen sind:  
  
-   **Konvertierungen, die die aktuelle Kultur zu verwenden.** Die `CStr` und `Format` Funktionen konvertieren eine Zahl in eine Zeichenfolge, und die `CDbl` und `CInt` Funktionen konvertieren eine Zeichenfolge in eine Zahl.  
  
-   **Konvertierungen, die eine bestimmte Kultur verwenden.** Number-Objekt hat eine `ToString(IFormatProvider)` Methode, die eine Zahl in eine Zeichenfolge konvertiert und ein `Parse(String, IFormatProvider)` Methode, die eine Zeichenfolge in eine Zahl konvertiert. Z. B. die `Double` Typ ermöglicht die <xref:System.Double.ToString%28System.IFormatProvider%29> und <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> Methoden.  
  
 Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Conversion.Str%2A> und <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Eine bestimmte Kultur  
 Stellen Sie sich vor, dass Sie eine Anwendung, die ein Datum entwickeln (als Zeichenfolge formatiert) an einen Webdienst sendet. In diesem Fall muss die Anwendung eine bestimmte Kultur für die zeichenfolgenkonvertierung verwenden. Um zu verdeutlichen, warum zu veranschaulichen, betrachten Sie das Ergebnis unter Verwendung des Datums <xref:System.DateTime.ToString> Methode: Wenn Ihre Anwendung diese Methode verwendet, so formatieren Sie das Datum 4. Juli 2005, gibt "7/4/2005 12:00:00 Uhr" bei der Ausführung mit der Kultur Englisch-USA (En-US), es gibt jedoch " 04.07.2005 00:00:00 "bei der Ausführung mit der Kultur für Deutsch (de-DE).  
  
 Wenn Sie eine zeichenfolgenkonvertierung in eine bestimmte Kulturformat ausführen müssen, sollten Sie verwenden die `CultureInfo` -Klasse, die in integrierten der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Sie können ein neues erstellen `CultureInfo` Objekt für eine bestimmte Kultur durch Übergeben der Kulturname, der <xref:System.Globalization.CultureInfo.%23ctor%2A> Konstruktor. Die Namen der unterstützten Kultur werden aufgeführt, der <xref:System.Globalization.CultureInfo> Klasse Hilfeseite.  
  
 Alternativ können Sie eine Instanz von Abrufen der *invarianten Kultur* aus der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> Eigenschaft. Die invariante Kultur basiert auf der Kultur Englisch, aber es gibt einige Unterschiede. Beispielsweise gibt die invariante Kultur ein 24-Stundenformat anstelle von 12-Stunden-Format an.  
  
 Um ein Datum in der Kultur Zeichenfolge zu konvertieren, übergeben die <xref:System.Globalization.CultureInfo> -Objekt, das Date-Objekt <xref:System.DateTime.ToString%28System.IFormatProvider%29> Methode. Im folgenden Codebeispiel beispielsweise zeigt "07/04/2005 00:00:00" unabhängig von kultureinstellungen der Anwendung.  
  
 [!code-vb[VbVbalrConcepts#1](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  Datumsliterale werden immer entsprechend der Kultur Englisch interpretiert.  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 Es gibt zwei wichtige Situationen, in denen Zeichenfolgenvergleiche erforderlich sind:  
  
-   **Sortieren von Daten für die Anzeige für den Benutzer.** Verwenden Sie die Vorgänge auf Grundlage der aktuellen Kultur, damit die Zeichenfolgen ordnungsgemäß sortiert.  
  
-   **Ermittelt, ob zwei anwendungsinterne Zeichenfolgen (i. d. r. aus Sicherheitsgründen) genau übereinstimmen.** Verwenden Sie die Vorgänge, die die aktuelle Kultur zu ignorieren.  
  
 Sie können beide Typen von Vergleichen mit der Visual Basic ausführen <xref:Microsoft.VisualBasic.Strings.StrComp%2A> Funktion. Geben Sie den optionalen `Compare` Argument für den Typ des Vergleichs zu steuern: `Text` für die meisten ein- und Ausgaben `Binary` für genaue Übereinstimmungen zu ermitteln.  
  
 Die `StrComp` Funktion gibt eine ganze Zahl, die die Beziehung zwischen den zwei verglichenen Zeichenfolgen basierend auf der Sortierreihenfolge angibt. Ein positiver Wert für das Ergebnis gibt an, dass die erste Zeichenfolge größer als die zweite Zeichenfolge ist. Ein negatives Ergebnis gibt an, die erste Zeichenfolge kleiner ist, und 0 (null) gibt an, die Zeichenfolgen auf Gleichheit.  
  
 [!code-vb[VbVbalrStrings#22](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 Können Sie auch die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Partner, der die `StrComp` -Funktion, die <xref:System.String.Compare%2A?displayProperty=nameWithType> Methode. Dies ist eine statische, überladene Methode der Basisklasse String-Klasse. Im folgende Beispiel wird veranschaulicht, wie diese Methode verwendet wird:  
  
 [!code-vb[VbVbalrStrings#48](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 Für eine präzisere Steuerung des wie Vergleiche ausgeführt werden, können Sie zusätzliche Überladungen der <xref:System.String.Compare%2A> Methode. Mit der <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode, die Sie verwenden die `comparisonType` Argument, um welche Art von Vergleich so um, anzugeben.  
  
|Wert für `comparisonType` Argument|Typ des Vergleichs|Empfohlene Verwendung|  
|---|---|---|  
|`Ordinal`|Vergleich basierend auf Zeichenfolgen Komponentenbytes.|Verwenden Sie diesen Wert für den Vergleich: Groß-/Kleinschreibung Bezeichner, die sicherheitsbezogenen Einstellungen oder andere nicht linguistische Bezeichner, bei denen die Bytes genau übereinstimmen müssen.|  
|`OrdinalIgnoreCase`|Vergleich basierend auf Zeichenfolgen Komponentenbytes.<br /><br /> `OrdinalIgnoreCase` verwendet die invariante kulturinformationen zum bestimmen, wann zwei Zeichen in der Großschreibung unterscheiden.|Verwenden Sie diesen Wert für den Vergleich: Groß-/Kleinschreibung IDs, die sicherheitsbezogenen Einstellungen und in Windows gespeicherten Daten.|  
|`CurrentCulture` oder `CurrentCultureIgnoreCase`|Vergleich basierend auf der Interpretation der Zeichenfolgen in der aktuellen Kultur.|Verwenden Sie diese Werte für den Vergleich: Daten, die angezeigt werden, für den Benutzer, die meisten Benutzereingaben und anderen Daten, die linguistische Interpretation erfordern.|  
|`InvariantCulture` oder `InvariantCultureIgnoreCase`|Vergleich basierend auf der Interpretation der Zeichenfolgen in der invarianten Kultur.<br /><br /> Dies unterscheidet sich die `Ordinal` und `OrdinalIgnoreCase`, da die invariante Kultur Zeichen außerhalb des zulässigen Bereichs als entsprechende invarianten Zeichen behandelt.|Verwenden Sie diese Werte nur für den Vergleich dauerhafter Daten oder anzeigen linguistisch relevanter Daten, die eine feste Sortierreihenfolge erfordern.|  
  
### <a name="security-considerations"></a>Sicherheitsüberlegungen  
 Wenn Ihre Anwendung sicherheitsrelevanten abhängig vom Ergebnis eines Vergleichs oder Änderung der Groß-/Kleinschreibung erstellt und gibt dann den Vorgang verwenden, sollten die <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode, und übergeben Sie `Ordinal` oder `OrdinalIgnoreCase` für die `comparisonType` Argument.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Globalization.CultureInfo>  
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
