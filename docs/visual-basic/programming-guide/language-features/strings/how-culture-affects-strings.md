---
title: Auswirkungen der Kultur Zeichenfolgen in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- locale, effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 63228a40897b29d0324be73ca1a17bcb19af2a16
ms.lasthandoff: 03/13/2017

---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Auswirkungen der Kultur auf Zeichenfolgen in Visual Basic
Diese Hilfeseite wird erläutert, wie [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verwendet Kultur Informationen zum zeichenfolgenkonvertierungen und Vergleiche durchführen.  
  
## <a name="when-to-use-culture-specific-strings"></a>Verwendung von kulturabhängigen Zeichenfolgen  
 Sie sollten in der Regel verwenden kulturabhängigen Zeichenfolgen für alle Daten, die angezeigt und von Benutzern gelesen und Kultur Zeichenfolgen für interne Daten für Ihre Anwendung verwenden.  
  
 Wenn Ihre Anwendung Benutzer ein Datum als Zeichenfolge eingeben anfordert, z. B. wird erwartet, dass Benutzer Zeichenfolgen gemäß ihrer Kultur zu formatieren, und die Anwendung sollte die Zeichenfolge entsprechend konvertieren. Wenn die Anwendung dann dieses Datum in der Benutzeroberfläche darstellt, sollte es in der Kultur des Benutzers vorhanden.  
  
 Wenn die Anwendung das Datum auf einen zentralen Server hochlädt, sollte sie die Zeichenfolge entsprechend einer bestimmten Kultur, um Verwechslungen zwischen möglicherweise unterschiedliche Datumsformate zu verhindern, dass formatieren.  
  
## <a name="culture-sensitive-functions"></a>Kulturabhängige Funktionen  
 Alle der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] String-Funktionen (mit Ausnahme der `Str` und `Val` Funktionen) Informationen zur Kultur der Anwendung verwenden, um sicherzustellen, dass die Konvertierungen und Vergleiche für die Kultur des Benutzers für die Anwendung geeignet sind.  
  
 Der Schlüssel erfolgreich mit String-Funktionen in Clientanwendungen, die auf Computern mit anderen Kultur ausgeführt ist, zu verstehen, welche Funktionen die Einstellung einer bestimmten Kultur verwenden und mit der aktuellen kultureinstellung. Beachten Sie, dass die Einstellungen der Anwendung Kultur werden standardmäßig aus den Einstellungen der Kultur des Betriebssystems geerbt werden, ein. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, und [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</xref:Microsoft.VisualBasic.Conversion.Oct%2A> </xref:Microsoft.VisualBasic.Conversion.Hex%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A> </xref:Microsoft.VisualBasic.Strings.ChrW%2A> </xref:Microsoft.VisualBasic.Strings.Chr%2A> </xref:Microsoft.VisualBasic.Strings.AscW%2A> </xref:Microsoft.VisualBasic.Strings.Asc%2A>  
  
 Die `Str` (konvertiert Zahlen in Zeichenfolgen) und `Val` (konvertiert Zeichenfolgen in Zahlen) Funktionen verwenden Sie nicht die Anwendung Informationen zur Kultur beim Konvertieren zwischen Zeichenfolgen und Zahlen. Stattdessen erkennen sie nur den Punkt (.) als gültiges Dezimaltrennzeichen. Die unterschiedliche Kulturen berücksichtigt analoge dieser Funktionen sind:  
  
-   **Konvertierungen, die die aktuelle Kultur verwendet.** Die `CStr` und `Format` Funktionen konvertieren eine Zahl in eine Zeichenfolge, und die `CDbl` und `CInt` Funktionen konvertieren eine Zeichenfolge in eine Zahl.  
  
-   **Konvertierungen, die eine bestimmte Kultur zu verwenden.** Number-Objekt hat eine `ToString(IFormatProvider)` -Methode, die eine Zahl in eine Zeichenfolge konvertiert und ein `Parse(String, IFormatProvider)` -Methode, die eine Zeichenfolge in eine Zahl konvertiert. Zum Beispiel die `Double` bietet die <xref:System.Double.ToString%28System.IFormatProvider%29>und <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29>Methoden.</xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> </xref:System.Double.ToString%28System.IFormatProvider%29>  
  
 Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Conversion.Str%2A>und <xref:Microsoft.VisualBasic.Conversion.Val%2A>.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Conversion.Str%2A>  
  
## <a name="using-a-specific-culture"></a>Eine bestimmte Kultur  
 Angenommen Sie, Sie eine Anwendung, die ein Datum entwickeln (als Zeichenfolge formatiert) an einen Webdienst sendet. In diesem Fall muss die Anwendung eine bestimmte Kultur für die zeichenfolgenkonvertierung verwenden. Um daher zu veranschaulichen, betrachten Sie das Ergebnis unter Verwendung des Datums <xref:System.DateTime.ToString>Methode: Wenn Ihre Anwendung diese Methode zum Formatieren des Datums am 4. Juli 2005 verwendet gibt "7/4/2005 12:00:00 Uhr" bei der Ausführung mit der Kultur Englisch-USA (En-US), es gibt jedoch "04.07.2005 00:00:00" bei der Ausführung mit der Kultur für Deutsch (de-DE).</xref:System.DateTime.ToString>  
  
 Wenn Sie die zeichenfolgenkonvertierung einer in einem kulturspezifischen Format durchführen müssen, verwenden Sie die `CultureInfo` -Klasse, die in integriert ist die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Sie können eine neue erstellen `CultureInfo` Objekt für eine bestimmte Kultur übergeben den Namen der Kultur, die <xref:System.Globalization.CultureInfo.%23ctor%2A>Konstruktor.</xref:System.Globalization.CultureInfo.%23ctor%2A> Die Namen der unterstützten Kulturen werden aufgelistet, der <xref:System.Globalization.CultureInfo>Klasse Hilfeseite.</xref:System.Globalization.CultureInfo>  
  
 Alternativ können Sie eine Instanz von Abrufen der *invarianten Kultur* aus der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>-Eigenschaft.</xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> Die invariante Kultur basiert auf der Kultur Englisch, aber es gibt einige Unterschiede. Beispielsweise gibt die invariante Kultur ein 24-Stunden statt 12-Stunden-Format an.  
  
 Um ein Datum in die Zeichenfolge der Kultur zu konvertieren, übergeben Sie das <xref:System.Globalization.CultureInfo>-Objekt, des Date-Objekts <xref:System.DateTime.ToString%28System.IFormatProvider%29>-Methode.</xref:System.DateTime.ToString%28System.IFormatProvider%29> </xref:System.Globalization.CultureInfo> Der folgende code z. B. zeigt "07/04/2005 00:00:00", unabhängig von kultureinstellungen für die Anwendung.  
  
 [!code-vb[VbVbalrConcepts&#1;](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  Datumsliterale werden immer entsprechend der Kultur Englisch interpretiert.  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 Es gibt zwei wichtige Situationen sind Zeichenfolgenvergleiche erforderlich:  
  
-   **Sortieren von Daten für die Anzeige für den Benutzer.** Verwenden Sie die Vorgänge auf Grundlage der aktuellen Kultur, damit die Zeichenfolgen ordnungsgemäß sortiert.  
  
-   **Bestimmen, ob zwei anwendungsinterne Zeichenfolgen (i. d. r. für Sicherheitszwecke) genau übereinstimmen.** Verwenden Sie die Vorgänge, die die aktuelle Kultur zu ignorieren.  
  
 Sie können beide Arten von Vergleichen mit Ausführen der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Strings.StrComp%2A>Funktion.</xref:Microsoft.VisualBasic.Strings.StrComp%2A> Geben Sie den optionalen `Compare` Argument den Typ des Vergleichs zu steuern: `Text` für die meisten ein- und Ausgaben `Binary` zur Bestimmung der genauen Treffer.  
  
 Die `StrComp` -Funktion gibt eine ganze Zahl, die die Beziehung zwischen den zwei verglichenen Zeichenfolgen basierend auf der Sortierreihenfolge angibt. Ein positiver Wert für das Ergebnis gibt an, dass die erste Zeichenfolge größer als die zweite Zeichenfolge ist. Ein negatives Ergebnis zeigt die erste Zeichenfolge kleiner ist, und&0; (null) gibt an, die Zeichenfolgen auf Gleichheit.  
  
 [!code-vb[VbVbalrStrings&#22;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 Können Sie auch die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Partner die `StrComp` -Funktion, die <xref:System.String.Compare%2A?displayProperty=fullName>-Methode.</xref:System.String.Compare%2A?displayProperty=fullName> Dies ist eine statische, überladene Methode der Basisklasse String-Klasse. Im folgende Beispiel wird veranschaulicht, wie diese Methode verwendet wird:  
  
 [!code-vb[VbVbalrStrings&#48;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 Für eine genauere Steuerung, wie Vergleiche ausgeführt werden, können Sie zusätzliche Überladungen der <xref:System.String.Compare%2A>-Methode.</xref:System.String.Compare%2A> Mit der <xref:System.String.Compare%2A?displayProperty=fullName>-Methode können Sie die `comparisonType` Argument angeben, welche Vergleichsart verwendet werden soll.</xref:System.String.Compare%2A?displayProperty=fullName>  
  
|Wert für `comparisonType` Argument|Typ des Vergleichs|Empfohlene Verwendung|  
|---|---|---|  
|`Ordinal`|Vergleich basierend auf Zeichenfolgen Komponentenbytes.|Verwenden Sie diesen Wert, wenn vergleichen: Bezeichner Groß-/Kleinschreibung beachtet, sicherheitsbezogene Einstellungen oder andere nicht linguistische Bezeichner, bei denen die Bytes genau übereinstimmen müssen.|  
|`OrdinalIgnoreCase`|Vergleich basierend auf Zeichenfolgen Komponentenbytes.<br /><br /> `OrdinalIgnoreCase`verwendet die invariante kulturinformationen um zu bestimmen, wann zwei Zeichen nur in Großschreibung unterscheiden.|Verwenden Sie diesen Wert beim Vergleich von: Groß-/Kleinschreibung von Bezeichnern, sicherheitsbezogene Einstellungen und Daten in Windows.|  
|`CurrentCulture` oder `CurrentCultureIgnoreCase`|Vergleich auf der Grundlage der Interpretation der Zeichenfolgen in der aktuellen Kultur.|Verwenden Sie diese Werte beim Vergleichen von: Daten, die angezeigt werden, der Benutzer, die meisten Benutzereingaben und anderen Daten, die linguistische Interpretation erfordern.|  
|`InvariantCulture` oder `InvariantCultureIgnoreCase`|Vergleich auf der Grundlage der Interpretation der Zeichenfolgen in der invarianten Kultur.<br /><br /> Dies unterscheidet sich von der `Ordinal` und `OrdinalIgnoreCase`, da die invariante Kultur Zeichen außerhalb des akzeptierten Bereichs als entsprechende invariante Zeichen behandelt.|Verwenden Sie diese Werte nur beim Vergleichen von Daten beibehalten oder anzeigen linguistisch relevanter Daten, die eine feste Sortierreihenfolge erfordern.|  
  
### <a name="security-considerations"></a>Sicherheitsüberlegungen  
 Wenn Ihre Anwendung Sicherheit abhängig vom Ergebnis eines Vergleichs oder einer Änderung der Groß-/Kleinschreibung entscheidet, und klicken Sie dann den Vorgang verwenden sollten die <xref:System.String.Compare%2A?displayProperty=fullName>-Methode, und übergeben Sie `Ordinal` oder `OrdinalIgnoreCase` für die `comparisonType` Argument.</xref:System.String.Compare%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Globalization.CultureInfo></xref:System.Globalization.CultureInfo>   
 [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
