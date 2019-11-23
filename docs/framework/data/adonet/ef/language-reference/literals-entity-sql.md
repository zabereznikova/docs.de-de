---
title: Literale (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 092ef693-6e5f-41b4-b868-5b9e82928abf
ms.openlocfilehash: e07dd3217e133fff98beb11ecad47e1474e4974a
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319661"
---
# <a name="literals-entity-sql"></a>Literale (Entity SQL)
In diesem Thema wird die [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Unterstützung für Literale beschrieben.  
  
## <a name="null"></a>Null  
 Das NULL-Literal wird verwendet, um für einen beliebigen Typ den Wert Null darzustellen. Das NULL-Literal ist mit jedem Typ kompatibel.  
  
 Typisierte Nullen können durch Umwandlung eines NULL-Literals erstellt werden. Weitere Informationen finden Sie unter [Cast](cast-entity-sql.md).  
  
 Regeln für die Verwendung von freien Gleit Komma-null-literalen finden Sie unter [NULL-Literale und Typrückschluss](null-literals-and-type-inference-entity-sql.md).  
  
## <a name="boolean"></a>Boolesch  
 Boolesche Literale werden durch die Schlüsselwörter `true` und `false` dargestellt.  
  
## <a name="integer"></a>Ganze Zahl  
 Ganzzahlliterale können vom Typ <xref:System.Int32> oder <xref:System.Int64> sein. Ein <xref:System.Int32>-Literal ist eine Folge numerischer Zeichen. Ein <xref:System.Int64>-Literal ist eine Folge numerischer Zeichen, auf die der Großbuchstabe "L" folgt.  
  
## <a name="decimal"></a>Decimal  
 Eine Festkommazahl (dezimal) besteht aus einer Reihe von numerischen Zeichen, einem Punkt (.) und einer weiteren Folge numerischer Zeichen, auf die der Großbuchstabe "M" folgt.  
  
## <a name="float-double"></a>Float, Double  
 Eine Gleitkommazahl mit doppelter Genauigkeit ist eine Reihe von numerischen Zeichen, einem Punkt (.) und einer weiteren Folge numerischer Zeichen, auf die ein Exponent folgen kann. Eine Gleitkommazahl mit einfacher Genauigkeit (oder "Float") besteht aus einer Gleitkommazahlensyntax mit doppelter Genauigkeit, auf die der Kleinbuchstabe "f" folgt.  
  
## <a name="string"></a>String  
 Ein String ist eine in Anführungszeichen eingeschlossene Zeichenfolge. Die Zeichenfolge kann entweder in einfache (`'`) oder doppelte (") Anführungszeichen eingeschlossen sein. Zeichenfolgenliterale sind entweder Unicode oder Nicht-Unicode. Stellen Sie dem Literal ein groß geschriebenes "N" voran, um ein Zeichenfolgeliteral als Unicode zu deklarieren. Standardmäßig werden Nicht-Unicode-Zeichenfolgenliterale verwendet. Zwischen "N" und dem Inhalt des Zeichenfolgenliterals dürfen keine Leerzeichen stehen, und "N" muss ein Großbuchstabe sein.  
  
```sql  
'hello' -- non-Unicode character string literal  
N'hello' -- Unicode character string literal  
"x"  
N"This is a string!"  
'so is THIS'  
```  
  
## <a name="datetime"></a>DateTime  
 Ein datetime-Literal ist unabhängig vom Gebietsschema und besteht aus einem Datums- und einem Uhrzeitteil. Datums- und einem Uhrzeitteile sind obligatorisch, und es gibt keine Standardwerte.  
  
 Der Datums Teil muss folgendes Format aufweisen: `YYYY`-`MM`-`DD`, wobei `YYYY` ein vierstelliger Jahreswert zwischen 0001 und 9999 ist, `MM` der Monat zwischen 1 und 12 und `DD` der Wert für den Tag ist, der für den angegebenen Monat `MM`gültig ist.  
  
 Der Zeitteil muss folgendes Format aufweisen: `HH`:`MM`[:`SS`[.fffffff]], wobei `HH` ein Stundenwert zwischen 0 und 23, `MM` ein Minutenwert zwischen 0 und einschließlich 59, `SS` ein Sekundenwert zwischen 0 und einschließlich 59 und fffffff der Wert für die Sekundenbruchteile zwischen 0 und 9999999 ist. Alle Wertbereiche sind inklusive. Der Wert für die Sekundenbruchteile ist optional. Der Wert für die Sekunden ist optional, außer wenn Sekundenbruchteile angegeben werden. In diesem Fall ist der Sekundenwert erforderlich. Werden keine Werte für Sekunden oder Sekundenbruchteile angegeben, wird als Standardwert 0 verwendet.  
  
 Zwischen dem DATETIME-Symbol und dem Inhalt des Literals darf eine beliebige Anzahl von Leerzeichen, aber keine neue Zeile enthalten sein.  
  
```sql  
DATETIME'2006-10-1 23:11'  
DATETIME'2006-12-25 01:01:00.0000000' -- same as DATETIME'2006-12-25 01:01'  
```  
  
## <a name="time"></a>Zeit  
 Das time-Literal ist unabhängig vom Gebietsschema und besteht ausschließlich aus einem Uhrzeitteil. Der Uhrzeitteil ist zwingend erforderlich, und hierfür ist kein Standardwert vorhanden. Der Uhrzeitteil muss folgendes Format aufweisen: HH:MM[:SS[.fffffff]], wobei "HH" ein Stundenwert zwischen 0 und 23, "MM" ein Minutenwert zwischen 0 und 59, "SS" ein Sekundenwert zwischen 0 und einschließlich 59 und "fffffff" der Wert für die Sekundenbruchteile zwischen 0 und 9999999 ist. Alle Wertbereiche sind inklusive. Der Wert für die Sekundenbruchteile ist optional. Der Wert für die Sekunden ist optional, außer wenn Sekundenbruchteile angegeben werden. In diesem Fall ist der Sekundenwert erforderlich. Werden keine Werte für Sekunden oder Sekundenbruchteile angegeben, wird als Standardwert 0 verwendet.  
  
 Zwischen dem TIME-Symbol und dem Inhalt des Literals darf eine beliebige Anzahl von Leerzeichen, aber keine neue Zeile enthalten sein.  
  
```sql  
TIME‘23:11’  
TIME‘01:01:00.1234567’  
```  
  
## <a name="datetimeoffset"></a>DateTimeOffset  
 Ein datetimeoffset-Literal ist unabhängig vom Gebietsschema und besteht aus einem Datums-, einem Uhrzeit- und einem Offsetteil. Alle Datums-, Uhrzeit- und Offsetteile sind obligatorisch, und es gibt keine Standardwerte. Der Datumsteil muss folgendes Format aufweisen: JJJJ-MM-TT, wobei "JJJJ" eine Jahresangabe mit vier Ziffern zwischen 0001 und 9999, "MM" der Wert für den Monat zwischen 1 und 12 und "DD" der Wert für den Tag ist, der für den gegebenen Monat gültig ist. Der Uhrzeitteil muss folgendes Format aufweisen: HH:MM[:SS[.fffffff]], wobei "HH" ein Stundenwert zwischen 0 und 23, "MM" ein Minutenwert zwischen 0 und 59, "SS" ein Sekundenwert zwischen 0 und 59 und "fffffff" ein Wert für die Sekundenbruchteile zwischen 0 und 9999999 ist. Alle Wertbereiche sind inklusive. Der Wert für die Sekundenbruchteile ist optional. Der Wert für die Sekunden ist optional, außer wenn Sekundenbruchteile angegeben werden. In diesem Fall ist der Sekundenwert erforderlich. Werden keine Werte für Sekunden oder Sekundenbruchteile angegeben, wird als Standardwert 0 verwendet. Der Offset Teil muss das Format {+&#124;-} hh: mm aufweisen, wobei HH und mm die gleiche Bedeutung wie im Zeit Teil haben. Der Wert für den Offsetbereich muss jedoch zwischen -14:00 und +14:00 liegen.  
  
 Zwischen dem DATETIMEOFFSET-Symbol und dem Inhalt des Literals darf eine beliebige Anzahl von Leerzeichen, aber keine neue Zeile enthalten sein.  
  
```sql  
DATETIMEOFFSET‘2006-10-1 23:11 +02:00’  
DATETIMEOFFSET‘2006-12-25 01:01:00.0000000 -08:30’  
```  
  
> [!NOTE]
> Ein gültiger Entity SQL-Literalwert kann aus den unterstützten Bereichen für CLR oder die Datenquelle herausfallen. Dies könnte zu einer Ausnahme führen.  
  
## <a name="binary"></a>Binary  
 Ein binäres Zeichenfolgenliteral ist eine in einfache Anführungszeichen eingeschlossene Folge von Hexadezimalziffern, die auf das Binary-Schlüsselwort oder das Symbol `X` oder `x` folgt. Beim Symbol `X`wird die Groß- und Kleinschreibung nicht berücksichtigt. Zwischen dem `binary`-Schlüsselwort und dem binären Zeichenfolgenwert können null oder mehr Leerzeichen stehen.  
  
 Bei den Hexadezimalzeichen wird außerdem die Groß-/Kleinschreibung nicht berücksichtigt. Wenn das Literal aus einer ungeraden Anzahl von Hexadezimalziffern zusammengesetzt ist, wird das Literal zu einer geraden Anzahl von Hexadezimalziffern aufgefüllt, indem dem Literal die Hexadezimalziffer 0 vorangestellt wird. Für die Größe von binären Zeichenfolgen gibt es keine formale Beschränkung.  
  
```sql  
Binary'00ffaabb'  
X'ABCabc'  
BINARY    '0f0f0f0F0F0F0F0F0F0F'  
X'' –- empty binary string  
```  
  
## <a name="guid"></a>Guid  
 Ein `GUID`-Literal stellt einen global eindeutigen Bezeichner dar. Es handelt sich um eine Sequenz, die durch das-Schlüsselwort gebildet wird `GUID` gefolgt von hexadezimalen Ziffern in dem Format, das als *Registrierungs* Format bezeichnet wird: 8-4-4-4-12 in einfache Anführungszeichen Bei den Hexadezimalzeichen wird die Groß/- Kleinschreibung nicht berücksichtigt.  
  
 Zwischen dem GUID-Symbol und dem Inhalt des Literals darf eine beliebige Anzahl von Leerzeichen, aber keine neue Zeile enthalten sein.  
  
```sql  
Guid'1afc7f5c-ffa0-4741-81cf-f12eAAb822bf'  
GUID  '1AFC7F5C-FFA0-4741-81CF-F12EAAB822BF'  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](entity-sql-overview.md)
