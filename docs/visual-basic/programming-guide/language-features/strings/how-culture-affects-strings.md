---
title: Auswirkungen der Kultur auf Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
ms.openlocfilehash: 7301d52cf2c55394f731a8b7af5427e5fa66ba88
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591963"
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Auswirkungen der Kultur auf Zeichenfolgen in Visual Basic
Diese Hilfeseite beschreibt, wie Visual Basic kulturinformationen verwendet, um zeichenfolgenkonvertierungen und vergleichen zu können.  
  
## <a name="when-to-use-culture-specific-strings"></a>Wenn Sie kulturabhängigen Zeichenfolgen verwenden  
 In der Regel, Sie sollten verwenden kulturspezifische Zeichenfolgen für alle Daten, die angezeigt und von Benutzern lesen, und invarianter Kultur Zeichenfolgen für interne Daten Ihrer Anwendung.  
  
 Wenn Ihre Anwendung Benutzer ein Datum als Zeichenfolge eingeben aufgefordert werden, z. B. wird erwartet, dass Benutzer, die Zeichenfolgen gemäß ihrer Kultur formatiert, und die Anwendung muss die Zeichenfolge entsprechend zu konvertieren. Wenn Ihre Anwendung klicken Sie dann dieses Datum in der Benutzeroberfläche darstellt, sollte er es in der Kultur des Benutzers darstellen.  
  
 Wenn die Anwendung das Datum an einen zentralen Server hochgeladen wird, sollte sie jedoch die Zeichenfolge entsprechend einer bestimmten Kultur, um Verwechslungen zwischen möglicherweise eine andere Datums-und Uhrzeitformate formatieren.  
  
## <a name="culture-sensitive-functions"></a>Kulturabhängigen Funktionen  
 Alle Visual Basic-zeichenfolgenkonvertierung Funktionen (mit Ausnahme von der `Str` und `Val` Funktionen) Informationen zur Kultur der Anwendung verwenden, um sicherzustellen, dass die Konvertierungen und Vergleiche für die Kultur der Anwendung geeignet sind. der Benutzer.  
  
 Der Schlüssel mit zeichenfolgenkonvertierungsfunktionen erfolgreich in Anwendungen, die auf Computern mit anderen kultureinstellungen auszuführen ist, zu verstehen, welche Funktionen eine bestimmte Kultur-Einstellung verwenden, und die die aktuelle kultureinstellung verwenden. Beachten Sie, dass die Einstellungen der Kultur der Anwendung in der Standardeinstellung von den kultureinstellungen des Betriebssystems geerbt sind, aus. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, und [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Die `Str` (konvertiert Zahlen in Zeichenfolgen) und `Val` (konvertiert Zeichenfolgen in Zahlen)-Funktionen verwenden Sie nicht Informationen zur Kultur der Anwendung beim Konvertieren zwischen Zeichenfolgen und Zahlen. Stattdessen erkennen sie nur den Punkt (.) als gültige Dezimaltrennzeichen an. Die unterschiedliche Kulturen berücksichtigt analoge dieser Funktionen sind:  
  
- **Konvertierungen, die die aktuelle Kultur zu verwenden.** Die `CStr` und `Format` Funktionen konvertieren eine Zahl in eine Zeichenfolge, und die `CDbl` und `CInt` Funktionen konvertieren eine Zeichenfolge in eine Zahl.  
  
- **Konvertierungen, die eine bestimmte Kultur zu verwenden.** Jede Number-Objekt hat eine `ToString(IFormatProvider)` Methode, die eine Zahl in eine Zeichenfolge konvertiert und ein `Parse(String, IFormatProvider)` Methode, die eine Zeichenfolge in eine Zahl konvertiert. Z. B. die `Double` bietet die <xref:System.Double.ToString%28System.IFormatProvider%29> und <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> Methoden.  
  
 Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Conversion.Str%2A> und <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Eine bestimmte Kultur  
 Stellen Sie sich, dass Sie eine Anwendung, die ein Datum entwickeln (als Zeichenfolge formatiert) an einen Webdienst sendet. In diesem Fall muss die Anwendung eine bestimmte Kultur für die zeichenfolgenkonvertierung verwenden. Um daher zu veranschaulichen, betrachten Sie in das Ergebnis unter Verwendung des Datums des <xref:System.DateTime.ToString> Methode: Wenn Ihre Anwendung diese Methode verwendet, so formatieren Sie das Datum 4. Juli 2005, gibt "7/4/2005 12:00:00 Uhr" bei der Ausführung mit der Kultur Englisch für USA (En-US), gibt jedoch eine "04.07.2005 00:00:00" bei der Ausführung mit die Kultur für Deutsch (de-DE).  
  
 Wenn Sie eine zeichenfolgenkonvertierung in eine bestimmte Kulturformat ausführen müssen, sollten Sie verwenden die `CultureInfo` -Klasse, die in .NET Framework integriert ist. Sie können ein neues erstellen `CultureInfo` Objekt für eine bestimmte Kultur durch Übergabe von den Namen der Kultur, die <xref:System.Globalization.CultureInfo.%23ctor%2A> Konstruktor. Die unterstützte Kulturnamen finden Sie in der <xref:System.Globalization.CultureInfo> Hilfeseite für die Klasse.  
  
 Alternativ können Sie eine Instanz von Abrufen der *invariante Kultur* aus der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> Eigenschaft. Die invariante Kultur basiert auf der Kultur Englisch, aber es gibt einige Unterschiede. Beispielsweise gibt die invariante Kultur 24-Stunden-Format statt 12-Stunden-Format an.  
  
 Um ein Datum in der Kultur Zeichenfolge zu konvertieren, übergeben die <xref:System.Globalization.CultureInfo> Objekt, des Date-Objekts <xref:System.DateTime.ToString%28System.IFormatProvider%29> Methode. Das folgende Codebeispiel zeigt "07/04/2005 00:00:00", unabhängig von kultureinstellungen der Anwendung.  
  
 [!code-vb[VbVbalrConcepts#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#1)]  
  
> [!NOTE]
>  Datumsliterale werden immer entsprechend der Kultur Englisch interpretiert.  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 Es gibt zwei wichtige Situationen, in denen Zeichenfolgenvergleiche erforderlich sind:  
  
- **Sortieren von Daten für die Anzeige für den Benutzer.** Verwenden Sie Vorgänge, die auf der aktuellen Kultur basieren, die Zeichenfolgen ordnungsgemäß sortiert.  
  
- **Bestimmen, ob zwei anwendungsinterne Zeichenfolgen (in der Regel aus Sicherheitsgründen) genau.** Verwenden Sie die Vorgänge, die die aktuelle Kultur zu ignorieren.  
  
 Sie können beide Arten von Vergleichen mit der Visual Basic ausführen <xref:Microsoft.VisualBasic.Strings.StrComp%2A> Funktion. Geben Sie den optionalen `Compare` Argument für den Typ des Vergleichs zu steuern: `Text` für die meisten ein- und Ausgabe `Binary` für genaue Übereinstimmungen zu ermitteln.  
  
 Die `StrComp` Funktionsergebnis ist eine ganze Zahl, die die Beziehung zwischen den zwei verglichenen Zeichenfolgen basierend auf der Sortierreihenfolge angibt. Ein positiver Wert für das Ergebnis gibt an, dass die erste Zeichenfolge größer als die zweite Zeichenfolge ist. Ein negatives Ergebnis gibt an, die erste Zeichenfolge kleiner ist, und 0 (null) gibt an, die Zeichenfolgen auf Gleichheit.  
  
 [!code-vb[VbVbalrStrings#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#22)]  
  
 Sie können auch die .NET Framework-Partner, der die `StrComp` -Funktion, die <xref:System.String.Compare%2A?displayProperty=nameWithType> Methode. Dies ist eine statische, überladene Methode der Basisklasse String-Klasse. Im folgende Beispiel wird veranschaulicht, wie diese Methode verwendet wird:  
  
 [!code-vb[VbVbalrStrings#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#48)]  
  
 Für eine genauere Steuerung, wie die Vergleiche durchgeführt werden, können Sie zusätzliche Überladungen der <xref:System.String.Compare%2A> Methode. Mit der <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode, die Sie verwenden die `comparisonType` Argument, um welche Art von Vergleich so um, anzugeben.  
  
|Wert für `comparisonType` Argument|Typ des Vergleichs|Empfohlene Verwendung|  
|---|---|---|  
|`Ordinal`|Vergleich anhand der Zeichenfolgen-Komponentenbytes.|Verwenden Sie diesen Wert für den Vergleich: Groß-/Kleinschreibung von Bezeichnern, die sicherheitsbezogenen Einstellungen oder andere nicht linguistische Bezeichner, bei denen die Bytes genau übereinstimmen müssen.|  
|`OrdinalIgnoreCase`|Vergleich anhand der Zeichenfolgen-Komponentenbytes.<br /><br /> `OrdinalIgnoreCase` verwendet die Informationen für die invariante Kultur um zu ermitteln, wann die zwei Zeichen nur in Großschreibung unterscheiden.|Verwenden Sie diesen Wert für den Vergleich: Groß-/Kleinschreibung von Bezeichnern, die sicherheitsbezogenen Einstellungen und Daten in Windows.|  
|`CurrentCulture` oder `CurrentCultureIgnoreCase`|Prüfung auf Grundlage der Interpretation der Zeichenfolgen in der aktuellen Kultur.|Verwenden Sie diese Werte für den Vergleich: Daten, die angezeigt werden, um den Benutzer, die meisten Benutzereingaben und anderen Daten, die linguistische Interpretation erfordern.|  
|`InvariantCulture` oder `InvariantCultureIgnoreCase`|Prüfung auf Grundlage der Interpretation der Zeichenfolgen in der invarianten Kultur.<br /><br /> Dies unterscheidet sich die `Ordinal` und `OrdinalIgnoreCase`, da die invariante Kultur Zeichen außerhalb des zulässigen Bereichs als entsprechende invariante Zeichen behandelt.|Verwenden Sie diese Werte nur für den Vergleich dauerhafter Daten oder Anzeigen von linguistisch relevante Daten, die eine feste Sortierreihenfolge erfordern.|  
  
### <a name="security-considerations"></a>Sicherheitsüberlegungen  
 Wenn die Anwendung die Sicherheitsfragen die richtigen Entscheidungen basierend auf dem Ergebnis eines Vergleichs oder einer Änderung der Groß-/Kleinschreibung verwendet, und dann den Vorgang verwenden, sollten die <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode, und übergeben Sie `Ordinal` oder `OrdinalIgnoreCase` für die `comparisonType` Argument.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Globalization.CultureInfo>
- [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
