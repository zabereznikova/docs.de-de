---
title: Auswirkungen der Kultur auf Zeichenfolgen
ms.date: 07/20/2015
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
ms.openlocfilehash: 9cbd3a5b8685178259b76d97919ea097ae72f6ae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401965"
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Auswirkungen der Kultur auf Zeichenfolgen in Visual Basic
Auf dieser Hilfeseite wird erläutert, wie Visual Basic Kultur Informationen verwendet, um Zeichen folgen Konvertierungen und Vergleiche auszuführen.  
  
## <a name="when-to-use-culture-specific-strings"></a>Verwendungszwecke kulturspezifischer Zeichen folgen  
 In der Regel sollten Sie Kultur abhängige Zeichen folgen für alle Daten verwenden, die Benutzern angezeigt und von diesen gelesen werden, und Kultur abhängige Zeichen folgen für die internen Daten Ihrer Anwendung verwenden.  
  
 Wenn Ihre Anwendung z. b. Benutzer auffordert, ein Datum als Zeichenfolge einzugeben, sollte erwartet werden, dass Benutzer die Zeichen folgen gemäß ihrer Kultur formatieren, und die Anwendung sollte die Zeichenfolge entsprechend konvertieren. Wenn Ihre Anwendung dieses Datum dann in der Benutzeroberfläche anzeigt, sollte Sie in der Kultur des Benutzers vorhanden sein.  
  
 Wenn die Anwendung jedoch das Datum auf einen zentralen Server hochlädt, sollte Sie die Zeichenfolge entsprechend einer bestimmten Kultur formatieren, um Verwechslungen zwischen potenziell unterschiedlichen Datumsformaten zu vermeiden.  
  
## <a name="culture-sensitive-functions"></a>Kultur abhängige Funktionen  
 Alle Visual Basic Zeichen folgen Konvertierungs Funktionen (außer den `Str` `Val` Funktionen und) verwenden die Kultur Informationen der Anwendung, um sicherzustellen, dass die Konvertierungen und Vergleiche für die Kultur des Anwendungs Benutzers geeignet sind.  
  
 Der Schlüssel für die erfolgreiche Verwendung von Funktionen zur Zeichen folgen Konvertierung in Anwendungen, die auf Computern mit unterschiedlichen Kultur Einstellungen ausgeführt werden, besteht darin, zu verstehen, welche Funktionen eine bestimmte Kultur Einstellung verwenden und welche die aktuelle Kultur Einstellung verwendet. Beachten Sie, dass die Kultur Einstellungen der Anwendung standardmäßig von den Kultur Einstellungen des Betriebssystems geerbt werden. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Asc%2A> den <xref:Microsoft.VisualBasic.Strings.AscW%2A> <xref:Microsoft.VisualBasic.Strings.Chr%2A> <xref:Microsoft.VisualBasic.Strings.ChrW%2A> <xref:Microsoft.VisualBasic.Strings.Format%2A> <xref:Microsoft.VisualBasic.Conversion.Hex%2A> <xref:Microsoft.VisualBasic.Conversion.Oct%2A> [Typkonvertierungs Funktionen](../../../language-reference/functions/type-conversion-functions.md),,,,,, und.  
  
 Der `Str` (konvertiert Zahlen in Zeichen folgen) und `Val` (Konvertiert Zeichen folgen in Zahlen) Funktionen verwenden beim Konvertieren zwischen Zeichen folgen und Zahlen nicht die Kultur Informationen der Anwendung. Stattdessen wird nur der Punkt (.) als gültiges Dezimaltrennzeichen erkannt. Die Kultur abhängigen analog zu diesen Funktionen sind:  
  
- **Konvertierungen mit der aktuellen Kultur.** Die `CStr` `Format` Funktionen und konvertieren eine Zahl in eine Zeichenfolge, und die `CDbl` -und- `CInt` Funktionen konvertieren eine Zeichenfolge in eine Zahl.  
  
- **Konvertierungen, die eine bestimmte Kultur verwenden.** Jedes Number-Objekt verfügt über eine `ToString(IFormatProvider)` -Methode, die eine Zahl in eine Zeichenfolge konvertiert, und eine `Parse(String, IFormatProvider)` Methode, die eine Zeichenfolge in eine Zahl konvertiert. Der `Double` -Typ stellt beispielsweise die <xref:System.Double.ToString%28System.IFormatProvider%29> -Methode und die- <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> Methode bereit.  
  
 Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Conversion.Str%2A> und <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## <a name="using-a-specific-culture"></a>Verwenden einer bestimmten Kultur  
 Stellen Sie sich vor, dass Sie eine Anwendung entwickeln, die ein Datum (als Zeichenfolge formatiert) an einen Webdienst sendet. In diesem Fall muss die Anwendung eine bestimmte Kultur für die Zeichen folgen Konvertierung verwenden. Um dies zu veranschaulichen, sollten Sie das Ergebnis der Verwendung der Date-Methode in Erwägung gezogen haben <xref:System.DateTime.ToString> : Wenn Ihre Anwendung diese Methode verwendet, um das Datum der 4. Juli 2005 zu formatieren, wird "7/4/2005 12:00:00 am" zurückgegeben, wenn Sie mit der Kultur "USA English" (de-de) ausgeführt 00:00:00 wird.  
  
 Wenn Sie eine Zeichen folgen Konvertierung in einem bestimmten Kultur Format ausführen müssen, sollten Sie die-Klasse verwenden, die `CultureInfo` in die .NET Framework integriert ist. Sie können ein neues- `CultureInfo` Objekt für eine bestimmte Kultur erstellen, indem Sie den Namen der Kultur an den- <xref:System.Globalization.CultureInfo.%23ctor%2A> Konstruktor übergeben. Die unterstützten Kultur Namen werden auf der <xref:System.Globalization.CultureInfo> Hilfeseite der-Klasse aufgelistet.  
  
 Alternativ können Sie eine Instanz der *invarianten Kultur* aus der-Eigenschaft erhalten <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> . Die invariante Kultur basiert auf der englischen Kultur, es gibt jedoch einige Unterschiede. Die invariante Kultur gibt z. b. eine 24-Stunden-Uhrzeit anstelle eines 12-Stunden-Formats an.  
  
 Wenn Sie ein Datum in die Zeichenfolge der Kultur konvertieren möchten, übergeben Sie das <xref:System.Globalization.CultureInfo> -Objekt an die-Methode des Date-Objekts <xref:System.DateTime.ToString%28System.IFormatProvider%29> . Der folgende Code zeigt z. b. "07/04/2005 00:00:00" an, unabhängig von den Kultur Einstellungen der Anwendung.  
  
 [!code-vb[VbVbalrConcepts#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#1)]  
  
> [!NOTE]
> Datums Literale werden immer gemäß der englischen Kultur interpretiert.  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 Es gibt zwei wichtige Situationen, in denen Zeichen folgen Vergleiche erforderlich sind:  
  
- **Sortieren von Daten für die Anzeige für den Benutzer.** Verwenden Sie Vorgänge auf der Grundlage der aktuellen Kultur, damit die Zeichen folgen entsprechend sortiert werden.  
  
- **Ermitteln, ob zwei Anwendungs interne Zeichen folgen exakt übereinstimmen (in der Regel aus Sicherheitsgründen).** Verwenden Sie Vorgänge, die die aktuelle Kultur ignorieren.  
  
 Beide Arten von vergleichen können mit der Visual Basic-Funktion durchgeführt werden <xref:Microsoft.VisualBasic.Strings.StrComp%2A> . Geben Sie das optionale `Compare` Argument zum Steuern des Vergleichs Typs an: `Text` für die meisten Eingaben und Ausgaben `Binary` zum Bestimmen der exakten Übereinstimmungen.  
  
 Die- `StrComp` Funktion gibt eine ganze Zahl zurück, die die Beziehung zwischen den beiden verglichenen Zeichen folgen auf Grundlage der Sortierreihenfolge angibt Ein positiver Wert für das Ergebnis gibt an, dass die erste Zeichenfolge größer als die zweite Zeichenfolge ist. Ein negatives Ergebnis gibt an, dass die erste Zeichenfolge kleiner ist, und NULL gibt die Gleichheit zwischen den Zeichen folgen an.  
  
 [!code-vb[VbVbalrStrings#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#22)]  
  
 Sie können auch den .NET Framework Partner der- `StrComp` Funktion verwenden, die- <xref:System.String.Compare%2A?displayProperty=nameWithType> Methode. Dies ist eine statische, überladene Methode der Basis Zeichenfolgen-Klasse. Im folgenden Beispiel wird veranschaulicht, wie diese Methode verwendet wird:  
  
 [!code-vb[VbVbalrStrings#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#48)]  
  
 Um die Art und Weise zu steuern, wie die Vergleiche ausgeführt werden, können Sie zusätzliche über Ladungen der- <xref:System.String.Compare%2A> Methode verwenden. Mit der- <xref:System.String.Compare%2A?displayProperty=nameWithType> Methode können Sie das- `comparisonType` Argument verwenden, um anzugeben, welcher Vergleichstyp verwendet werden soll.  
  
|Wert für `comparisonType` Argument|Vergleichstyp|Empfohlene Verwendung|  
|---|---|---|  
|`Ordinal`|Vergleich basierend auf den Komponenten Bytes der Zeichenfolge.|Verwenden Sie diesen Wert beim vergleichen: Bezeichner für Groß-/Kleinschreibung, sicherheitsbezogene Einstellungen oder andere nicht linguistische Bezeichner, bei denen die Bytes genau übereinstimmen müssen.|  
|`OrdinalIgnoreCase`|Vergleich basierend auf den Komponenten Bytes der Zeichenfolge.<br /><br /> `OrdinalIgnoreCase`bestimmt mithilfe der invarianten Kultur Informationen, ob sich zwei Zeichen nur in der Groß-und Kleinschreibung unterscheiden.|Verwenden Sie diesen Wert beim vergleichen: Bezeichner für die Groß-/Kleinschreibung, sicherheitsbezogene Einstellungen und in Windows gespeicherte Daten.|  
|`CurrentCulture` oder `CurrentCultureIgnoreCase`|Vergleich basierend auf der Interpretation der Zeichen folgen in der aktuellen Kultur.|Verwenden Sie diese Werte, wenn Sie vergleichen: dem Benutzer angezeigte Daten, die meisten Benutzereingaben und andere Daten, die eine linguistische Interpretation erfordern.|  
|`InvariantCulture` oder `InvariantCultureIgnoreCase`|Vergleich basierend auf der Interpretation der Zeichen folgen in der invarianten Kultur.<br /><br /> Dies unterscheidet sich von `Ordinal` und `OrdinalIgnoreCase` , da die invariante Kultur Zeichen außerhalb des zulässigen Bereichs als äquivalente invariante Zeichen behandelt.|Verwenden Sie diese Werte nur, wenn Sie persistente Daten vergleichen oder linguistisch relevante Daten anzeigen, die eine festgelegte Sortierreihenfolge erfordern.|  
  
### <a name="security-considerations"></a>Überlegungen zur Sicherheit  
 Wenn Ihre Anwendung Sicherheitsentscheidungen auf Grundlage des Ergebnisses eines Vergleichs oder einer Änderung der Fall Änderung trifft, sollte der Vorgang die <xref:System.String.Compare%2A?displayProperty=nameWithType> -Methode verwenden und `Ordinal` oder `OrdinalIgnoreCase` für das- `comparisonType` Argument übergeben.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Globalization.CultureInfo>
- [Einführung in Zeichenfolgen in Visual Basic](introduction-to-strings.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
