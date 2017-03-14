---
title: "How Culture Affects Strings in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "locale, effect on strings"
  - "strings [Visual Basic], locale dependence"
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How Culture Affects Strings in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Auf dieser Hilfeseite wird erörtert, wie in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Kulturinformationen für Zeichenfolgenkonvertierungen und \-vergleiche verwendet werden.  
  
## Wann sollten kulturspezifische Zeichenfolgen verwendet werden?  
 Normalerweise empfiehlt sich die Verwendung kulturspezifischer Zeichenfolgen für alle Daten, die für Benutzer dargestellt und von Benutzern gelesen werden, während von der Kultur unabhängige Zeichenfolgen für die internen Daten der Anwendung verwendet werden sollten.  
  
 Wenn beispielsweise Benutzer von der Anwendung gebeten werden, ein Datum als Zeichenfolge einzugeben, wird erwartet, dass die Benutzer die Zeichenfolgen im Format ihrer Kultur eingeben, und die Anwendung sollte die Zeichenfolge entsprechend konvertieren.  Bei der anschließenden Darstellung dieses Datum auf der Benutzeroberfläche der Anwendung sollte es in der Kultur des Benutzers dargestellt werden.  
  
 Wenn jedoch die Anwendung das Datum auf einen zentralen Server hochlädt, sollte sie die Zeichenfolge entsprechend einer bestimmten Kultur formatieren, um Probleme durch möglicherweise unterschiedliche Datumsformate zu verhindern.  
  
## Kulturabhängige Funktionen  
 In allen Zeichenfolgenkonvertierungsfunktionen von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] \(mit Ausnahme der `Str`\-Funktion und der `Val`\-Funktion\) werden die Kulturinformationen der Anwendung verwendet, um sicherzustellen, dass die Konvertierungen und Vergleiche der Kultur des Anwendungsbenutzers entsprechen.  
  
 Um Zeichenfolgenkonvertierungsfunktionen in Anwendungen erfolgreich zu verwenden, die auf Computern mit unterschiedlichen Kultureinstellungen ausgeführt werden, müssen Sie wissen, welche Funktionen eine bestimmte Kultureinstellung verwenden und welche Funktionen die aktuelle Kultureinstellung verwenden.  Beachten Sie, dass die Kultureinstellungen einer Anwendung standardmäßig von den Kultureinstellungen des Betriebssystems geerbt werden.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A> und [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Die `Str`\-Funktion \(konvertiert Zahlen in Zeichenfolgen\) und die `Val`\-Funktion \(konvertiert Zeichenfolgen in Zahlen\) verwenden beim Konvertieren zwischen Zeichenfolgen und Zahlen nicht die Kulturinformationen der Anwendung.  Stattdessen erkennen sie nur den Punkt \(.\) als gültiges Dezimaltrennzeichen.  Diese Funktionen verfügen über folgende kulturabhängige Entsprechungen:  
  
-   **Konvertierungen, für die die aktuelle Kultur verwendet wird.** Die `CStr`\-Funktion und die `Format`\-Funktion konvertieren eine Zahl in eine Zeichenfolge, und die `CDbl`\-Funktion sowie die `CInt`\-Funktion konvertieren eine Zeichenfolge in eine Zahl.  
  
-   **Konvertierungen, für die eine bestimmte Kultur verwendet wird.** Jedes Zahlobjekt verfügt über eine `ToString(IFormatProvider)`\-Methode, die eine Zahl in eine Zeichenfolge konvertiert, und über eine `Parse(String, IFormatProvider)`\-Methode, die eine Zeichenfolge in eine Zahl konvertiert.  Beispielsweise stellt der `Double`\-Typ die <xref:System.Double.ToString%28System.IFormatProvider%29>\-Methode und die <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29>\-Methode bereit.  
  
 Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Conversion.Str%2A> und unter <xref:Microsoft.VisualBasic.Conversion.Val%2A>.  
  
## Verwenden einer bestimmten Kultur  
 Angenommen, Sie entwickeln eine Anwendung, die ein Datum \(als Zeichenfolge formatiert\) an einen Webdienst sendet.  In diesem Fall muss die Anwendung eine bestimmte Kultur für die Zeichenfolgenkonvertierung verwenden.  Um zu veranschaulichen, warum dies erforderlich ist, betrachten wir das Ergebnis der Verwendung der <xref:System.DateTime.ToString>\-Methode für das Datum. Wenn die Anwendung das Datum July 4, 2005 mit dieser Methode formatiert, gibt sie "7\/4\/2005 12:00:00 AM" zurück, wenn sie mit der Kultur Englisch \(USA\) ausgeführt wird, doch sie gibt "04.07.2005 00:00:00" zurück, wenn sie mit der Kultur Deutsch \(Deutschland\) ausgeführt wird.  
  
 Wenn Sie eine Zeichenfolgenkonvertierung in einem bestimmten Kulturformat ausführen müssen, sollten Sie die `CultureInfo`\-Klasse verwenden, die in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] integriert ist.  Sie können ein neues `CultureInfo`\-Objekt für eine bestimmte Kultur erstellen, indem Sie den Namen der Kultur an den <xref:System.Globalization.CultureInfo.%23ctor%2A>\-Konstruktor übergeben.  Die Namen der unterstützten Kulturen werden auf der Hilfeseite für die <xref:System.Globalization.CultureInfo>\-Klasse aufgelistet.  
  
 Stattdessen können Sie auch von der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>\-Eigenschaft eine Instanz der *invarianten Kultur* abrufen.  Die invariante Kultur basiert auf der englischen Kultur, allerdings mit einigen Unterschieden.  Beispielsweise verwendet die invariante Kultur ein 24\-Stunden\-Format statt eines 12\-Stunden\-Formats.  
  
 Um ein Datum in die Zeichenfolge der Kultur zu konvertieren, übergeben Sie das <xref:System.Globalization.CultureInfo>\-Objekt an die <xref:System.DateTime.ToString%28System.IFormatProvider%29>\-Methode des Datumsobjekts.  Beispielsweise wird im folgenden Code unabhängig von den Kultureinstellungen der Anwendung "07\/04\/2005 00:00:00" angezeigt.  
  
 [!code-vb[VbVbalrConcepts#1](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  Datumsliterale werden immer entsprechend der Kultur Englisch interpretiert.  
  
## Vergleichen von Zeichenfolgen  
 In zwei wichtigen Situationen sind Zeichenfolgenvergleiche erforderlich:  
  
-   **Das Sortieren von Daten, um sie für den Benutzer anzuzeigen.** Verwenden Sie auf der aktuellen Kultur basierende Operationen, damit die Zeichenfolgen ordnungsgemäß sortiert werden.  
  
-   **Bestimmen, ob zwei anwendungsinterne Zeichenfolgen genau übereinstimmen \(i. d. R. für Sicherheitszwecke\).** Verwenden Sie Operationen, die von der aktuellen Kultur unabhängig sind.  
  
 Sie können beide Arten von Vergleichen mit der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Strings.StrComp%2A>\-Funktion ausführen.  Geben Sie das optionale `Compare`\-Argument an, um den Vergleichstyp zu bestimmen: `Text` für die meisten Ein\- und Ausgaben und `Binary` für genaue Übereinstimmungen.  
  
 Die `StrComp`\-Funktion gibt eine ganze Zahl zurück, die die Beziehung zwischen den zwei verglichenen Zeichenfolgen auf der Grundlage der Sortierreihenfolge angibt.  Ein positiver Ergebniswert weist darauf hin, dass die erste Zeichenfolge größer als die zweite ist.  Ein negatives Ergebnis zeigt an, dass die erste Zeichenfolge kleiner ist. 0 bedeutet, das beide Zeichenfolgen übereinstimmen.  
  
 [!code-vb[VbVbalrStrings#22](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 Sie können auch die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]\-Entsprechung der `StrComp`\-Funktion, die <xref:System.String.Compare%2A?displayProperty=fullName>\-Methode, verwenden.  Dabei handelt es sich um eine statische, überladene Methode der Basiszeichenfolgenklasse.  Das folgende Beispiel demonstriert die Verwendung der Methode:  
  
 [!code-vb[VbVbalrStrings#48](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 Um die Ausführung der Vergleiche genauer zu steuern, können Sie zusätzliche Überladungen der <xref:System.String.Compare%2A>\-Methode verwenden.  Bei der <xref:System.String.Compare%2A?displayProperty=fullName>\-Methode können Sie mit dem `comparisonType`\-Argument angeben, welche Vergleichsart verwendet werden soll.  
  
||||  
|-|-|-|  
|Wert für `comparisonType`\-Argument|Art des Vergleichs|Empfohlene Verwendung|  
|`Ordinal`|Vergleich auf der Grundlage der Komponentenbytes der Zeichenfolgen|Mit diesem Wert können Sie Folgendes vergleichen: Bezeichner ohne Berücksichtigung der Groß\-\/Kleinschreibung, Sicherheitseinstellungen oder andere nicht linguistische Bezeichner, deren Bytes genau übereinstimmen müssen.|  
|`OrdinalIgnoreCase`|Vergleich auf der Grundlage der Komponentenbytes der Zeichenfolgen<br /><br /> `OrdinalIgnoreCase` verwendet die kulturinvarianten Informationen, um zu bestimmen, ob sich zwei Zeichen nur in der Groß\-\/Kleinschreibung unterscheiden.|Mit diesem Wert können Sie Folgendes vergleichen: Bezeichner ohne Berücksichtigung der Groß\-\/Kleinschreibung, Sicherheitseinstellungen und in Windows gespeicherte Daten|  
|`CurrentCulture` oder `CurrentCultureIgnoreCase`|Vergleich auf der Grundlage der Interpretation der Zeichenfolgen in der aktuellen Kultur.|Mit diesen Werten können Sie Folgendes vergleichen: für den Benutzer angezeigte Daten, die meisten Benutzereingaben und weitere Daten, die eine linguistische Interpretation erfordern.|  
|`InvariantCulture` oder `InvariantCultureIgnoreCase`|Vergleich auf der Grundlage der Interpretation der Zeichenfolgen in der invarianten Kultur.<br /><br /> Dies unterscheidet sich von `Ordinal` und `OrdinalIgnoreCase`, weil die invariante Kultur Zeichen außerhalb des akzeptierten Bereichs als entsprechende kulturinvariante Zeichen behandelt.|Verwenden Sie diese Werte nur für den Vergleich dauerhafter Daten oder zum Anzeigen linguistisch relevanter Daten, die eine feste Sortierreihenfolge erfordern.|  
  
### Sicherheitsüberlegungen  
 Wenn die Anwendung Sicherheitsentscheidungen aufgrund der Ergebnisse einer Vergleichsoperation oder einer Operation zum Ändern der Groß\-\/Kleinschreibung durchführt, sollte die Operation die <xref:System.String.Compare%2A?displayProperty=fullName>\-Methode verwenden und als `comparisonType`\-Argument `Ordinal` oder `OrdinalIgnoreCase` übergeben.  
  
## Siehe auch  
 <xref:System.Globalization.CultureInfo>   
 [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)