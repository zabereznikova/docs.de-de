---
title: Sprachenunabhängigkeit und sprachunabhängige Komponenten
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- language interoperability
- Common Language Specification
- cross-language interoperability
- CLS
- runtime, language interoperability
- common language runtime, language interoperability
ms.assetid: 4f0b77d0-4844-464f-af73-6e06bedeafc6
ms.openlocfilehash: 689ca9f7278dcf91b12bc62b5255a968388bb9f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120754"
---
# <a name="language-independence-and-language-independent-components"></a>Sprachenunabhängigkeit und sprachunabhängige Komponenten

Das .NET Framework ist sprachneutral. Das bedeutet, dass ein Entwickler in einer der zahlreichen Sprachen entwickeln kann, die auf .NET Framework ausgerichtet sind, z. B. C#, C++/CLI, Eiffel, F#, IronPython, IronRuby, PowerBuilder, Visual Basic, Visual COBOL und Windows PowerShell. Sie können auf die Typen und Member von Klassenbibliotheken, die für .NET Framework entwickelt wurden, zugreifen, ohne die Sprache, in der sie ursprünglich geschrieben wurden, kennen zu müssen und ohne den Konventionen der Originalsprache folgen zu müssen. Wenn Sie ein Komponentenentwickler sind, kann von allen .NET Framework-Apps sprachenunabhängig auf die Komponente zugegriffen werden.

> [!NOTE]
> In diesem Artikel wird das Erstellen sprachunabhängiger Komponenten erläutert. Diese Komponenten können von Apps verwendet werden, die in einer beliebigen Sprache geschrieben wurden. Sie können auch eine einzelne Komponente oder App aus Quellcode erstellen, der in mehreren Sprachen geschrieben wurde. Weitere Informationen finden Sie im zweiten Teil dieses Artikels unter [Sprachübergreifende Interoperabilität](#CrossLang).

Um vollständig mit anderen Objekten zu interagieren, die in irgendeiner Programmiersprache geschrieben wurden, müssen die Objekte den Aufrufern nur die Funktionen verfügbar machen, die allen Sprachen gemeinsam sind. Dieser gemeinsame Satz von Funktionen wird von der CLS (Common Language Specification) definiert. Das ist ein Satz von Regeln, die für generierte Assemblys gelten. Die Common Language Specification wird in der Partition I, in den Klauseln 7 bis 11 im [ECMA 335-Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm) definiert.

Wenn die Komponente der Common Language Specification entspricht, ist sichergestellt, dass sie CLS-kompatibel ist, und dass vom Code in Assemblys, die in irgendeiner CLS unterstützenden Programmiersprache geschrieben wurden, aus auf sie zugegriffen werden kann. Sie können bestimmen, ob die Komponente zur Kompilierzeit der Common Language Specification entspricht, indem Sie das <xref:System.CLSCompliantAttribute>-Attribut auf den Quellcode anwenden. Weitere Informationen finden Sie im Abschnitt zum [CLSCompliantAttribute-Attribut](#CLSAttribute).

In diesem Artikel:

- [CLS-Kompatibilitätsregeln](#Rules)

  - [Typen und Typmembersignaturen](#Types)

  - [Namenskonventionen](#naming)

  - [Typkonvertierung](#conversion)

  - [Arrays](#arrays)

  - [Schnittstellen](#Interfaces)

  - [Enumerationen](#enums)

  - [Typmember im Allgemeinen](#members)

  - [Memberzugriff](#MemberAccess)

  - [Generische Typen und Member](#Generics)

  - [Konstruktoren](#ctors)

  - [Eigenschaften](#properties)

  - [Ereignisse](#events)

  - [Überladungen](#overloads)

  - [Ausnahmen](#exceptions)

  - [Attribute](#attributes)

- [Das CLSCompliantAttribute-Attribut](#CLSAttribute)

- [Sprachübergreifende Interoperabilität](#CrossLang)

<a name="Rules"></a>

## <a name="cls-compliance-rules"></a>CLS-Kompatibilitätsregeln

In diesem Abschnitt werden die Regeln zum Erstellen einer CLS-kompatiblen Komponente beschrieben. Eine vollständige Liste der Regeln finden Sie unter Partition I, Klausel 11 im [ECMA 335-Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

> [!NOTE]
> In der Common Language Specification wird für jede Regel der CLS-Kompatibilität erläutert, wie sie auf Consumer (Entwickler, die programmgesteuert auf eine CLS-kompatible Komponente zugreifen), Frameworks (Entwickler, die einen Sprachcompiler zum Erstellen von CLS-kompatiblen Bibliotheken verwenden) und Extender (Entwickler, die zum Erstellen CLS-kompatibler Komponenten ein Tool, wie einen Sprachcompiler oder einen Codeparser, erstellen) anzuwenden ist. In diesem Artikel wird auf die Anwendbarkeit der Regeln für Frameworks eingegangen. Beachten Sie allerdings, dass möglicherweise einige der Regeln für Extender auch auf Assemblys anwendbar sind, die mithilfe von "Reflection.Emit" erstellt werden.

Um eine sprachenneutrale Komponente zu entwerfen, müssen Sie nur die CLS-Kompatibilitätregeln auf die öffentliche Schnittstelle der Komponente anwenden. Die private Implementierung muss nicht mit der Spezifikation konform sein.

> [!IMPORTANT]
> Die Regeln für CLS-Kompatibilität gelten nur für die öffentlichen Schnittstelle einer Komponente, nicht für die private Implementierung.

Zum Beispiel sind ganze Zahlen ohne Vorzeichen, außer <xref:System.Byte>, nicht CLS-kompatibel. Da die `Person`-Klasse im folgenden Beispiel eine `Age`-Eigenschaft des Typs <xref:System.UInt16> verfügbar macht, zeigt der folgende Code eine Compilerwarnung an.

[!code-csharp[Conceptual.CLSCompliant#1](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/public1.cs#1)]
[!code-vb[Conceptual.CLSCompliant#1](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/public1.vb#1)]

Sie können CLS-Kompatibilität für die `Person`-Klasse erreichen, indem Sie den Typ der `Age`-Eigenschaft von <xref:System.UInt16> auf <xref:System.Int16> ändern. Das ist eine CLS-kompatible ganze Zahl mit Vorzeichen und einer Länge von 16 Bit. Sie müssen den Typ des privaten `personAge`-Felds nicht ändern.

[!code-csharp[Conceptual.CLSCompliant#2](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/public2.cs#2)]
[!code-vb[Conceptual.CLSCompliant#2](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/public2.vb#2)]

Die öffentliche Schnittstelle einer Bibliothek besteht aus folgenden Elementen:

- Definitionen öffentlicher Klassen

- Definitionen öffentlicher Member von öffentlichen Klassen sowie in Definitionen von Membern, auf die abgeleitete Klassen zugreifen können (d. h. geschützte Member).

- Parameter und Rückgabetypen öffentlicher Methoden von öffentlichen Klassen sowie Parameter und Rückgabetypen von Methoden, auf die abgeleitete Klassen zugreifen können.

Die Regeln für CLS-Kompatibilität werden in der folgenden Tabelle aufgeführt. Der Text der Regeln wird in vollem Wortlaut dem [ECMA 335-Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm) entnommen. Copyright 2012 durch Ecma-International. Ausführlichere Informationen zu diesen Regeln finden Sie in den folgenden Abschnitten.

|Kategorie|Siehe|Regel|Regelzahl|
|--------------|---------|----------|-----------------|
|Zugriff|[Memberzugriff](#MemberAccess)|Beim Überschreiben von geerbten Methoden darf der Zugriff nicht geändert werden, außer wenn eine Methode überschrieben wird, die von einer anderen Assembly mit `family-or-assembly`-Zugriff vererbt wurde. In diesem Fall muss für die Überschreibung `family`-Zugriff festgelegt werden.|10|
|Zugriff|[Memberzugriff](#MemberAccess)|Die Sichtbarkeit und der Zugriff von Typen und Membern soll so beschaffen sein, dass Typen in der Signatur eines Members sichtbar und zugreifbar sind, wann immer der Member selbst sichtbar und zugreifbar ist. Zum Beispiel soll eine öffentliche Methode, die außerhalb der Assembly sichtbar ist, über kein Argument verfügen, dessen Typ nur innerhalb der Assembly sichtbar ist. Die Sichtbarkeit und der Zugriff von Typen, die einen instanziierten generischen Typ zusammensetzen, der in der Signatur eines beliebigen Members verwendet wird, soll sichtbar und zugreifbar sein, wenn der Member selbst sichtbar und zugreifbar ist. Zum Beispiel soll ein instanziierter generischer Typ, der in der Signatur eines außerhalb der Assembly sichtbaren Members vorhanden ist, über kein generisches Argument verfügen, dessen Typ nur innerhalb der Assembly sichtbar ist.|12|
|Arrays|[Arrays](#arrays)|Arrays müssen über Elemente mit einem CLS-kompatiblen Typ verfügen, und die Untergrenze aller Dimensionen des Arrays muss Null sein. Nur der Tatsache, dass es sich bei einem Element um ein Array handelt sowie der Elementtyp des Arrays muss zur Unterscheidung zwischen Überladungen ausreichen. Wenn das Überladen auf Grundlage mindestens zweier Arraytypen erfolgt, muss es sich bei den Elementtypen um benannte Typen handeln.|16|
|Attribute|[Attribute](#attributes)|Attribute müssen vom Typ <xref:System.Attribute?displayProperty=nameWithType> oder eines davon geerbten Typs sein.|41|
|Attribute|[Attribute](#attributes)|CLS gestattet nur eine Teilmenge der Codierungen benutzerdefinierter Attribute. Die einzigen in diesen Codierungen zulässigen Typen sind (siehe Partition IV): <xref:System.Type?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Char?displayProperty=nameWithType>, <xref:System.Boolean?displayProperty=nameWithType>, <xref:System.Byte?displayProperty=nameWithType>, <xref:System.Int16?displayProperty=nameWithType>, <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.Single?displayProperty=nameWithType>, <xref:System.Double?displayProperty=nameWithType> sowie alle Enumerationstypen, die auf einem CLS-kompatiblen ganzzahligen Basistyp beruhen.|34|
|Attribute|[Attribute](#attributes)|Nach der CLS sind nicht öffentlich sichtbare erforderliche Modifizierer (`modreq`, siehe Partition II) zulässig, allerdings sind optionale Modifizierer (`modopt`, siehe Partition II), die sie nicht versteht, zulässig.|35|
|Konstruktoren|[Konstruktoren](#ctors)|Ein Objektkonstruktor muss einen Instanzenkonstruktor seiner Basisklasse aufrufen, bevor ein Zugriff auf geerbte Instanzdaten erfolgt. (Dies gilt nicht für Werttypen, die über keine Konstruktoren verfügen müssen.)|21|
|Konstruktoren|[Konstruktoren](#ctors)|Ein Objektkonstruktor darf nicht aufgerufen werden, außer als Teil bei der Erstellung eines Objekts und ein Objekt darf nicht zweimal initialisiert werden.|22|
|Enumerationen|[Enumerationen](#enums)|Der zugrunde liegende Typ einer Enumeration muss ein integrierter CLS-Ganzzahltyp sein, der Name des Felds muss "value__" lauten, und das Feld muss als `RTSpecialName` gekennzeichnet sein.|7|
|Enumerationen|[Enumerationen](#enums)|Es bestehen zwei verschiedene Arten von Enumerationen, die aufgrund des Vorhandenseins oder Fehlens des benutzerdefinierten Attributs <xref:System.FlagsAttribute?displayProperty=nameWithType> (siehe Partition IV Library) angegeben werden. Eine stellt benannte ganzzahlige Werte dar, die Andere stellt benannte Bitflags dar, die zum Generieren eines unbenannten Werts kombiniert werden können. Der Wert einer `enum` ist nicht auf die angegebenen Werte beschränkt.|8|
|Enumerationen|[Enumerationen](#enums)|Literale statische Felder einer Enumeration müssen vom Typ der Enumeration selbst sein.|9|
|Ereignisse|[Ereignisse](#events)|Die Methoden, die ein Ereignis implementieren, müssen in den Metadaten als `SpecialName` gekennzeichnet sein.|29|
|Ereignisse|[Ereignisse](#events)|Der Zugriff eines Ereignisses und seiner Zugriffsmethoden muss identisch sein.|30|
|Ereignisse|[Ereignisse](#events)|Die `add` und `remove`-Methoden eines Ereignisses müssen entweder beide vorhanden oder beide nicht vorhanden sein.|31|
|Ereignisse|[Ereignisse](#events)|Die `add` und `remove`-Methoden eines Ereignisses müssen jeweils einen Parameter erhalten, dessen Typ den Ereignistyp definiert. Dieser Typ muss von <xref:System.Delegate?displayProperty=nameWithType> abgeleitet sein.|32|
|Ereignisse|[Ereignisse](#events)|Ereignisse müssen einem bestimmten Benennungsschema folgen. Das `SpecialName`-Attribut, auf das in CLS-Regel 29 verwiesen wird, muss in den entsprechenden Namensvergleichen ignoriert werden und Bezeichnerregeln befolgen.|33|
|Ausnahmen|[Ausnahmen](#exceptions)|Ausgelöste Objekte müssen vom Typ <xref:System.Exception?displayProperty=nameWithType> oder eines davon geerbten Typs sein. Dennoch müssen CLS-kompatible Methoden die Weitergabe anderer Ausnahmetypen nicht blockieren.|40|
|Allgemein|[CLS-Kompatibilität: die Regeln](#Rules)|CLS-Regeln gelten nur für die Teile eines Typs, die außerhalb der definierenden Assembly sichtbar sind und auf die außerhalb der definierenden Assembly zugegriffen werden kann.|1|
|Allgemein|[CLS-Kompatibilität: die Regeln](#Rules)|Member von Typen, die nicht CLS-kompatibel sind, dürfen nicht als CLS-kompatibel gekennzeichnet werden.|2|
|Generics|[Generische Typen und Member](#Generics)|Geschachtelte Typen müssen mindestens so viele generische Parameter aufweisen wie der einschließende Typ. Die Position von generischen Parametern in einem geschachtelten Typ entspricht der Position der generischen Parameter im einschließenden Typ.|42|
|Generics|[Generische Typen und Member](#Generics)|Der Name eines generischen Typs muss die Anzahl von Typparametern, die auf dem nicht geschachtelten Typ deklariert oder neu in den Typ eingeführt werden, kodieren, wenn er entsprechend der oben definierten Regeln geschachtelt ist.|43|
|Generics|[Generische Typen und Member](#Generics)|Ein generischer Typ muss genügend Einschränkungen neu deklarieren, um zu gewährleisten, dass alle Einschränkungen des Basistyps oder der Schnittstellen durch die Einschränkungen des generischen Typs erfüllt sein würden.|4444|
|Generics|[Generische Typen und Member](#Generics)|Als Einschränkungen für generische Parameter verwendete Typen müssen selbst CLS-kompatibel sein.|45|
|Generics|[Generische Typen und Member](#Generics)|Es muss davon ausgegangen werden, dass die Sichtbarkeit und der Zugriff auf Member (einschließlich geschachtelter Typen) in einem instanziierten generischen Typ sich nicht auf die gesamte Deklaration des generischen Typs bezieht, sondern auf die spezifische Instanziierung. Davon ausgehend gelten die Sichtbarkeits- und Zugriffsregeln der CLS-Regel 12 weiterhin.|46|
|Generics|[Generische Typen und Member](#Generics)|Für jede abstrakte oder virtuelle generische Methode muss es eine konkrete (nicht abstrakte) Standardimplementierung geben.|47|
|Schnittstellen|[Schnittstellen](#Interfaces)|Zum Implementieren von CLS-kompatiblen Schnittstellen darf keine Definition von nicht CLS-kompatiblen Methoden erforderlich sein.|18|
|Schnittstellen|[Schnittstellen](#Interfaces)|CLS-kompatible Schnittstellen dürfen weder statische Methoden noch Felder definieren.|19|
|Member|[Typmember im Allgemeinen](#members)|Globale static-Felder und Methoden sind nicht CLS-kompatibel.|36|
|Member|--|Der Wert eines literalen statischen Elements wird von der Verwendung von Feldinitialisierungsmetadaten angegeben. Ein CLS-kompatibles Literal muss über einen Wert verfügen, der in den Feldinitialisierungsmetadaten angegeben wird, der genau vom gleichen Typ wie das Literal ist (oder des zugrunde liegenden Typs, wenn dieses Literal `enum` ist).|13|
|Member|[Typmember im Allgemeinen](#members)|Die vararg-Einschränkung ist nicht Teil der CLS, und die einzige Aufrufkonvention, die von der CLS unterstützt wird, ist die verwaltete Standardaufrufkonvention.|15|
|Namenskonventionen|[Namenskonventionen](#naming)|Assemblys müssen Anhang 7 des technischen Berichts 15 von Unicode Standard 3.0 befolgen, in dem Zeichen geregelt werden, die am Anfang oder innerhalb von Bezeichnern enthalten sein dürfen. Er ist online unter <https://www.unicode.org/unicode/reports/tr15/tr15-18.html> verfügbar. Bezeichner müssen im kanonischen Format vorliegen, das durch die Unicode-Normalisierungsform C definiert wird. Im Sinne der CLS sind zwei Bezeichner gleich, wenn ihre kleingeschriebenen Zuordnungen (wie von den Gebietsschema-unabhängigen, klein geschriebenen 1:1-Unicodezuordnungen angegeben) gleich sind. Demnach müssen sich zwei Bezeichner in mehr als nur der Großschreibung unterscheiden, damit sie gemäß der CLS als unterschiedlich angesehen werden können. Um jedoch eine geerbte Definition überschreiben zu können, erfordert die CLI die genaue Codierung der ursprünglichen Deklaration.|4|
|Überladen|[Namenskonventionen](#naming)|Alle Namen, die in einem CLS-kompatiblen Bereich eingeführt werden, müssen in ihrer Art eindeutig unabhängig sein, außer bei identischen Namen, die durch Überladen aufgelöst werden. Während es bei CTS möglich ist, dass ein einzelner Typ denselben Namen für eine Methode und ein Feld verwendet, ist dies bei CLS demnach unmöglich.|5|
|Überladen|[Namenskonventionen](#naming)|Felder und geschachtelte Typen müssen allein durch Vergleich des Bezeichners zu unterscheiden sein, auch wenn bei CTS verschiedene Signaturen unterschieden werden können. Methoden, Eigenschaften und Ereignisse mit demselben Namen (gemäß Bezeichnervergleich) müssen sich durch mehr als nur den Rückgabetyp unterscheiden (außer wie in CLS-Regel 39 angegeben).|6|
|Überladen|[Overloads](#overloads)|Nur Eigenschaften und Methoden können überladen werden.|37|
|Überladen|[Overloads](#overloads)|Eigenschaften und Methoden können allein basierend auf der Anzahl und den Typen ihrer Parameter überladen werden, außer den Konvertierungsoperatoren `op_Implicit` und `op_Explicit`, die auch auf Grundlage des Rückgabetyps überladen werden können.|38|
|Überladen|--|Wenn mindestens zwei CLS-kompatible Methoden, die in einem Typ deklariert werden, den gleichen Namen und für einen bestimmten Satz von Typinstanziierungen die gleichen Parameter und Rückgabetypen nutzen, dann müssen alle diese Methoden bei diesen Typinstanziierungen semantisch gleichwertig sein.|48|
|Typen|[Typ und Typmembersignaturen](#Types)|<xref:System.Object?displayProperty=nameWithType> ist CLS-kompatibel. Jede andere CLS-kompatible Klasse muss von einer CLS-kompatiblen Klasse erben.|23|
|Eigenschaften|[Eigenschaften](#properties)|Die Methoden, mit denen die Getter- und die Setter-Methode einer Eigenschaft implementiert werden, müssen in den Metadaten mit `SpecialName` markiert werden.|24|
|Eigenschaften|[Eigenschaften](#properties)|Die Zugriffsmethoden einer Eigenschaft müssen alle „static“, alle „virtual“ oder alle „instance“ sein.|26|
|Eigenschaften|[Eigenschaften](#properties)|Der Typ einer Eigenschaft muss dem Rückgabetyp der Getter-Methode und dem Typ des letzten Arguments der Setter-Methode entsprechen. Die Parametertypen der Eigenschaft müssen den Parametertypen der Getter-Methode und, ausgenommen dem Letzten, allen Parametertypen der Setter-Methode entsprechen. Diese Typen müssen CLS-kompatibel sein und dürfen keine verwalteten Zeiger sein (d. h., sie dürfen nicht als Verweise übergeben werden).|27|
|Eigenschaften|[Eigenschaften](#properties)|Eigenschaften müssen einem bestimmten Benennungsschema folgen. Das `SpecialName`-Attribut, auf das in CLS-Regel 24 verwiesen wird, muss in den entsprechenden Namensvergleichen ignoriert werden und Bezeichnerregeln einhalten. Eine Eigenschaft verfügt über eine Getter-Methode, eine Setter-Methode oder beide.|28|
|Typkonvertierung|[Typkonvertierung](#conversion)|Wenn entweder `op_Implicit` oder `op_Explicit` bereitgestellt werden, muss eine alternative Möglichkeit für die Umwandlung bereitgestellt werden.|39|
|Typen|[Typ und Typmembersignaturen](#Types)|Geschachtelte Werttypen sind nicht CLS-kompatibel.|3|
|Typen|[Typ und Typmembersignaturen](#Types)|Alle Typen, die in einer Signatur erscheinen, müssen CLS-kompatibel sein. Alle Typen, die einen instanziierten generischen Typ erstellen, müssen CLS-kompatibel sein.|11|
|Typen|[Typ und Typmembersignaturen](#Types)|Typisierte Verweise sind nicht CLS-kompatibel.|14|
|Typen|[Typ und Typmembersignaturen](#Types)|Nicht verwaltete Zeigertypen sind nicht CLS-kompatibel.|17|
|Typen|[Typ und Typmembersignaturen](#Types)|CLS-kompatible Klassen, Werttypen und Schnittstellen dürfen die Implementierung von nicht CLS-kompatiblen Membern nicht erfordern.|20|

<a name="Types"></a>

### <a name="types-and-type-member-signatures"></a>Typen und Typmembersignaturen

Der <xref:System.Object?displayProperty=nameWithType>-Typ ist CLS-kompatibel, und er ist der Basistyp aller Objekttypen im .NET Framework-Typsystem. Vererbung erfolgt im .NET Framework entweder implizit (zum Beispiel erbt die <xref:System.String>-Klasse implizit von der <xref:System.Object>-Klasse) oder explizit (zum Beispiel erbt die <xref:System.Globalization.CultureNotFoundException>-Klasse explizit von der <xref:System.ArgumentException>-Klasse, die explizit von der <xref:System.SystemException>-Klasse erbt, die explizit von der <xref:System.Exception>-Klasse erbt). Damit ein abgeleiteter Typ CLS-kompatibel ist, muss auch der Basistyp CLS-kompatibel sein.

Im folgenden Beispiel wird ein abgeleiteter Typ veranschaulicht, dessen Basistyp nicht CLS-kompatibel ist. Es wird eine `Counter`-Basisklasse definiert, die eine ganze Zahl ohne Vorzeichen mit einer Länge von 32 Bit als Indikator verwendet. Da die Klasse Gegenfunktionalität bereitstellt, indem eine ganze Zahl ohne Vorzeichen umgebrochen wird, wird die Klasse als nicht CLS-kompatibel gekennzeichnet. Daher ist eine abgeleitete Klasse, `NonZeroCounter`, auch nicht CLS-kompatibel.

[!code-csharp[Conceptual.CLSCompliant#12](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/type3.cs#12)]
[!code-vb[Conceptual.CLSCompliant#12](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/type3.vb#12)]

Alle in den Membersignaturen angezeigten Typen, einschließlich des Rückgabetyps oder des Eigenschaftentyps einer Methode, müssen CLS-kompatibel sein. Außerdem ist für generische Typen Folgendes erforderlich:

- Alle Typen, die einen instanziierten generischen Typ zusammensetzen, müssen CLS-kompatibel sein.

- Alle als Einschränkungen für generische Parameter verwendeten Typen müssen CLS-kompatibel sein.

Das [allgemeine Typsystem](../../docs/standard/base-types/common-type-system.md) von .NET Framework enthält verschiedene integrierte Datentypen, die direkt von der Common Language Runtime unterstützt werden und insbesondere in den Metadaten einer Assembly codiert werden. Von diesen systeminternen Typen sind die in der folgenden Tabelle aufgeführten Typen CLS-kompatibel.

|CLS-kompatibler Typ|BESCHREIBUNG|
|-------------------------|-----------------|
|<xref:System.Byte>|Ganze 8-Bit-Zahl ohne Vorzeichen|
|<xref:System.Int16>|Ganze 16-Bit-Zahl mit Vorzeichen|
|<xref:System.Int32>|32-Bit-Ganzzahl mit Vorzeichen|
|<xref:System.Int64>|64-Bit-Ganzzahl mit Vorzeichen|
|<xref:System.Single>|Gleitkommawert mit einfacher Genauigkeit|
|<xref:System.Double>|Gleitkommawert mit doppelter Genauigkeit|
|<xref:System.Boolean>|`true` oder `false` value_type|
|<xref:System.Char>|UTF-16-codierte Codeeinheit|
|<xref:System.Decimal>|Dezimalzahl ohne Gleitkomma|
|<xref:System.IntPtr>|Zeiger oder Handle einer Plattform-definierten Größe|
|<xref:System.String>|Auflistung von keinem, einem oder mehreren <xref:System.Char>-Objekten|

Die in der folgenden Tabelle aufgeführten systeminternen Typen sind nicht CLS-kompatibel.

|Nicht kompatibler Typ|BESCHREIBUNG|CLS-kompatible Alternative|
|-------------------------|-----------------|--------------------------------|
|<xref:System.SByte>|Ganzzahliger 8-Bit-Datentyp mit Vorzeichen|<xref:System.Int16>|
|<xref:System.TypedReference>|Zeiger auf ein Objekt und den Laufzeittyp|Keine|
|<xref:System.UInt16>|16-Bit-Ganzzahl ohne Vorzeichen|<xref:System.Int32>|
|<xref:System.UInt32>|32-Bit-Ganzzahl ohne Vorzeichen|<xref:System.Int64>|
|<xref:System.UInt64>|64-Bit-Ganzzahl ohne Vorzeichen|<xref:System.Int64> (kann überlaufen), <xref:System.Numerics.BigInteger> oder <xref:System.Double>|
|<xref:System.UIntPtr>|Zeiger ohne Vorzeichen oder Handle|<xref:System.IntPtr>|

Die .NET Framework-Klassenbibliothek oder jede andere Klassenbibliothek schließen möglicherweise andere nicht CLS-kompatible Typen ein, zum Beispiel:

- Geschachtelte Werttypen Im folgenden C#-Beispiel wird eine Klasse erstellt, die über eine öffentliche Eigenschaft des Typs `int*` namens `Value` verfügt. Da `int*` ein geschachtelter Werttyp ist, markiert der Compiler ihn als nicht CLS-kompatibel.

  [!code-csharp[Conceptual.CLSCompliant#26](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/box2.cs#26)]

- Typisierte Verweise, die spezielle Konstrukte sind, in denen ein Verweis auf ein Objekt und ein Verweis auf einen Typ enthalten sind. Typisierte Verweise werden in .NET Framework von der <xref:System.TypedReference>-Klasse dargestellt.

Wenn ein Typ nicht CLS-kompatibel ist, sollten Sie das <xref:System.CLSCompliantAttribute>-Attribut mit einem Wert von `isCompliant``false` darauf anwenden. Weitere Informationen finden Sie im Abschnitt zum [CLSCompliantAttribute-Attribut](#CLSAttribute).

Im folgenden Beispiel wird das Problem der CLS-Kompatibilität in einer Methodensignatur und in der Instanziierung des generischen Typs veranschaulicht. Dabei wird eine `InvoiceItem`-Klasse mit einer Eigenschaft vom Typ <xref:System.UInt32>, einer Eigenschaft vom Typ `Nullable(Of UInt32)` und einem Konstruktor mit Parametern vom Typ <xref:System.UInt32> sowie `Nullable(Of UInt32)` definiert. Sie erhalten vier Compilerwarnungen, wenn Sie versuchen, das Beispiel zu kompilieren.

[!code-csharp[Conceptual.CLSCompliant#3](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/type1.cs#3)]
[!code-vb[Conceptual.CLSCompliant#3](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/type1.vb#3)]

Um die Compilerwarnungen auszuschließen, ersetzen Sie die nicht CLS-kompatiblen Typen in der öffentlichen `InvoiceItem`-Schnittstelle durch kompatible Typen:

[!code-csharp[Conceptual.CLSCompliant#4](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/type2.cs#4)]
[!code-vb[Conceptual.CLSCompliant#4](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/type2.vb#4)]

Zusätzlich zu bestimmten aufgeführten Typen sind einige Typenkategorien ebenfalls nicht CLS-kompatibel. Diese schließen nicht verwaltete Zeigertypen und Funktionszeigertypen ein. Im folgenden Beispiel wird eine Compilerwarnung erzeugt, da ein Zeiger auf eine ganze Zahl verwendet wird, um ein Array ganzer Zahlen zu erstellen.

[!code-csharp[Conceptual.CLSCompliant#5](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/unmanagedptr1.cs#5)]

Für CLS-kompatible abstrakte Klassen (das heißt, Klassen, die als `abstract` in C# oder als `MustInherit` in Visual Basic markiert sind), müssen alle Member der Klasse auch CLS-kompatibel sein.

<a name="naming"></a>

### <a name="naming-conventions"></a>Namenskonventionen

Da bei einigen Programmiersprachen die Groß- und Kleinschreibung nicht beachtet werden muss, müssen Bezeichner (wie die Namen von Namespaces, Typen und Membern) durch mehr als die Groß-/Kleinschreibung unterschieden werden. Zwei Bezeichner gelten als äquivalent, wenn ihre kleingeschriebenen Zuordnungen identisch sind. Im folgenden C#-Beispiel werden zwei öffentliche Klassen definiert: `Person` und `person`. Da sie sich nur durch die Groß-/Kleinschreibung unterscheiden, markiert der C#-Compiler sie als nicht CLS-kompatibel.

[!code-csharp[Conceptual.CLSCompliant#16](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/naming1.cs#16)]

Programmiersprachenbezeichner, wie die Namen von Namespaces, Typen und Membern, müssen dem [Unicode-Standard 3.0, Fachbericht 15, Anhang 7](https://www.unicode.org/reports/tr15/tr15-18.html) entsprechen. Dies bedeutet Folgendes:

- Das erste Zeichen eines Bezeichners kann jeder Unicode-Großbuchstabe, Kleinbuchstabe, großer Anfangsbuchstabe, Modifiziererbuchstabe, anderer Buchstabe oder jede Buchstabenzahl sein. Informationen zu Unicode-Zeichenkategorien finden Sie unter der <xref:System.Globalization.UnicodeCategory?displayProperty=nameWithType>-Enumeration.

- Nachfolgende Zeichen können aus einer der Kategorien wie das erste Zeichen stammen, und sie können auch Markierungen ohne Zwischenraum, Sperrmarkierungen, Dezimalwerte, Connectorinterpunktionen und Formatierungscodes umfassen.

Bevor Sie Bezeichner vergleichen, sollten Sie Formatierungscodes herausfiltern und die Bezeichner in die Unicode-Normalisierungsform C konvertieren, da ein einzelnes Zeichen durch mehrere UTF-16-codierte Codeeinheiten dargestellt werden kann. Zeichensequenzen, die die gleichen Codeeinheiten in der Unicode-Normalisierungsform C erzeugen, sind nicht CLS-kompatibel. Im folgenden Beispiel werden zwei Eigenschaften definiert: eine namens `Å`, die aus dem Zeichen ÅNGSTRÖM-ZEICHEN (U+212B) besteht, und eine zweite namens `Å`, die aus dem Zeichen LATEINISCHER GROSSBUCHSTABE A MIT RING OBEN (U+00C5) besteht. Die Compiler von C#- und Visual Basic kennzeichnen den Quellcode als nicht CLS-kompatibel.

[!code-csharp[Conceptual.CLSCompliant#17](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/naming1.cs#17)]
[!code-vb[Conceptual.CLSCompliant#17](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/naming1.vb#17)]

Membernamen innerhalb eines bestimmten Bereichs (wie den Namespaces innerhalb einer Assembly, den Typen in einem Namespace oder den Membern innerhalb eines Typs) müssen eindeutig sein, abgesehen von Namen, die durch Überladen aufgelöst werden. Diese Anforderung ist zwingender als die des allgemeinen Typsystems, bei dem mehrere Member innerhalb eines Bereichs über identische Namen verfügen dürfen, solange es unterschiedliche Arten von Membern sind (zum Beispiel eine Methode und ein Feld). Insbesondere für Typmember:

- Felder und geschachtelte Typen werden allein nach Namen unterschieden.

- Methoden, Eigenschaften und Ereignisse mit demselben Namen müssen sich durch mehr als nur den Rückgabetyp unterscheiden.

Im folgenden Beispiel wird die Anforderung veranschaulicht, dass Membernamen innerhalb des Bereichs eindeutig sein müssen. Es wird eine Klasse namens `Converter` definiert, die vier Member namens `Conversion` umfasst. Drei Methoden und eine Eigenschaft. Die Methode, die einen Parameter <xref:System.Int64> umfasst, hat einen eindeutigen Namen, doch die beiden Methoden mit einem <xref:System.Int32>-Parameter sind nicht eindeutig, da der Rückgabewert nicht als ein Teil der Signatur eines Members gültig ist. Die `Conversion`- Eigenschaft verstößt auch gegen diese Anforderung, da Eigenschaften nicht den gleichen Namen wie überladene Methoden besitzen dürfen.

[!code-csharp[Conceptual.CLSCompliant#19](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/naming3.cs#19)]
[!code-vb[Conceptual.CLSCompliant#19](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/naming3.vb#19)]

Einzelne Sprachen enthalten eindeutige Schlüsselwörter, sodass Sprachen für die Common Language Runtime einen Mechanismus zum Verweisen auf Bezeichner (z. B. Typnamen) bereitstellen müssen, die mit den Schlüsselwörtern übereinstimmen. Beispielsweise ist `case` ein Schlüsselwort in C# und Visual Basic. Im folgenden Visual Basic-Beispiel wird eine Klasse namens `case` eindeutig vom `case`-Schlüsselwort unterschieden, indem öffnende und schließende geschweifte Klammern verwendet werden. Andernfalls würde in dem Beispiel die folgende Fehlermeldung erzeugt: "Das Schlüsselwort ist kein gültiger Bezeichner", und der Code könnte nicht kompiliert werden.

[!code-vb[Conceptual.CLSCompliant#22](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/keyword1.vb#22)]

Im folgenden C#-Beispiel kann die `case`-Klasse instanziiert werden, indem das `@` Symbol verwendet wird, um den Bezeichner eindeutig vom Schlüsselwort zu unterscheiden. Ohne dieses Zeichen würde der C#-Compiler zwei Fehlermeldungen anzeigen:"Typ erwartet" und "Ungültiger Ausdruck 'case'".

[!code-csharp[Conceptual.CLSCompliant#23](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/keyword2.cs#23)]

<a name="conversion"></a>

### <a name="type-conversion"></a>Typkonvertierung

In der Common Language Specification werden zwei Konvertierungsoperatoren definiert:

- `op_Implicit`, das für Erweiterungskonvertierungen verwendet wird, die zu keinem Datenverlust oder Genauigkeitsverlust führen. Zum Beispiel umfasst die <xref:System.Decimal>-Struktur einen überladenen `op_Implicit`-Operator, um Werte ganzzahliger Typen und <xref:System.Char>-Werte in <xref:System.Decimal>-Werte zu konvertieren.

- `op_Explicit`, der für einschränkende Konvertierungen verwendet wird, die zu Größenverlusten (ein Wert wird in einen Wert konvertiert, der über einen kleineren Bereich verfügt) bzw. zu Verlusten der Genauigkeit führen können. Zum Beispiel umfasst die <xref:System.Decimal>-Struktur einen überladenen `op_Explicit`-Operator, um den <xref:System.Double>-Wert und den <xref:System.Single>-Wert in <xref:System.Decimal> zu konvertieren und die <xref:System.Decimal>-Werte in die ganzzahligen Werte <xref:System.Double>, <xref:System.Single> und <xref:System.Char> zu konvertieren.

Allerdings wird Operatorüberladung oder die Definition benutzerdefinierter Operatoren nicht von allen Sprachen unterstützt. Wenn Sie diese Konvertierungsoperatoren implementieren, sollten Sie eine alternative Methode zum Ausführen der Konvertierung bereitstellen. Es wird empfohlen, `From`*Xxx*- und `To`*Xxx*-Methoden bereitzustellen.

Im folgenden Beispiel werden CLS-kompatible implizite und explizite Konvertierungen definiert. Es wird eine `UDouble`-Klasse erstellt, die eine Gleitkommazahl mit doppelter Genauigkeit und Vorzeichen darstellt. Implizite Konvertierungen aus `UDouble` in <xref:System.Double> und explizite Konvertierungen aus `UDouble` in <xref:System.Single>, aus <xref:System.Double> in `UDouble` und aus <xref:System.Single> in `UDouble` werden bereitgestellt. Es wird auch eine `ToDouble`-Methode als Alternative zum Operator für implizite Konvertierung definiert, und die `ToSingle`, `FromDouble`-Methode sowie die `FromSingle`-Methode werden als Alternativen zu den Operatoren der expliziten Konvertierung definiert.

[!code-csharp[Conceptual.CLSCompliant#15](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/convert1.cs#15)]
[!code-vb[Conceptual.CLSCompliant#15](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/convert1.vb#15)]

<a name="arrays"></a>

### <a name="arrays"></a>Arrays

CLS-kompatible Arrays sind mit den folgenden Regeln kompatibel:

- Die unteren Begrenzungen aller Dimensionen eines Arrays müssen gleich 0 sein. Im folgenden Beispiel wird ein Array mit einer nicht CLS-kompatiblen Untergrenze von eins erstellt. Beachten Sie, dass vom Compiler ungeachtet des Vorhandenseins des <xref:System.CLSCompliantAttribute>-Attributs nicht erkannt wird, dass das von der `Numbers.GetTenPrimes`-Methode zurückgegebene Array nicht CLS-kompatibel ist.

  [!code-csharp[Conceptual.CLSCompliant#8](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/array1.cs#8)]
  [!code-vb[Conceptual.CLSCompliant#8](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/array1.vb#8)]

- Alle Arrayelemente müssen aus CLS-kompatiblen Typen bestehen. Im folgenden Beispiel werden zwei Methoden, die nicht CLS-kompatible Arrays zurückgeben, definiert. Die erste Methode gibt ein Array von <xref:System.UInt32>-Werten zurück. Die zweite Methode gibt ein <xref:System.Object>-Array zurück, das den <xref:System.Int32>-Wert und den <xref:System.UInt32>-Wert umfasst. Obwohl der Compiler das erste Array aufgrund des <xref:System.UInt32>-Typs als nicht kompatibel identifiziert, wird nicht erkannt, dass das zweite Array nicht CLS-kompatible Elemente umfasst.

  [!code-csharp[Conceptual.CLSCompliant#9](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/array2.cs#9)]
  [!code-vb[Conceptual.CLSCompliant#9](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/array2.vb#9)]

- Die Überladungsauflösung für Methoden mit Arrayparametern basiert sowohl auf der Tatsache, dass es Arrays sind, als auch auf dem Elementtyp. Aus diesem Grund ist die folgende Definition einer überladenen `GetSquares`-Methode CLS-kompatibel.

  [!code-csharp[Conceptual.CLSCompliant#10](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/array3.cs#10)]
  [!code-vb[Conceptual.CLSCompliant#10](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/array3.vb#10)]

<a name="Interfaces"></a>

### <a name="interfaces"></a>Schnittstellen

CLS-kompatible Schnittstellen können Eigenschaften, Ereignisse und virtuelle Methoden (Methoden ohne Implementierung) definieren. Eine CLS-kompatible Schnittstelle kann keine der folgenden Aspekte aufweisen:

- Statische Methoden oder statische Felder Der C#- und der Visual Basic-Compiler erstellen Compilerfehler, wenn Sie einen statischen Member in einer Schnittstelle definieren.

- Felder Die Compiler von C# und Visual Basic generieren Compilerfehler, wenn Sie ein Feld in einer Schnittstelle definieren.

- Methoden, die nicht CLS-kompatibel sind. Zum Beispiel umfasst die folgende Schnittstellendefinition eine Methode, `INumber.GetUnsigned`, die als nicht CLS-kompatibel gekennzeichnet wird. In diesem Beispiel wird eine Compilerwarnung generiert.

  [!code-csharp[Conceptual.CLSCompliant#6](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/interface2.cs#6)]
  [!code-vb[Conceptual.CLSCompliant#6](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/interface2.vb#6)]

  Aufgrund dieser Regel, ist es nicht erforderlich, dass CLS-kompatible Typen nicht CLS-kompatible Member implementieren. Wenn ein CLS-kompatibles Framework eine Klasse verfügbar macht, die eine nicht CLS- kompatible Schnittstelle implementiert, sollte sie konkrete Implementierungen aller nicht-CLS-kompatiblen Member angeben.

CLS-kompatible Sprachcompiler müssen einer Klasse auch ermöglichen, separate Implementierungen von Membern bereitzustellen, die in mehreren Schnittstellen über den gleichen Namen und dieselbe Signatur verfügen.  C# und Visual Basic unterstützen [explizite Schnittstellenimplementierungen](../csharp/programming-guide/interfaces/explicit-interface-implementation.md), um unterschiedliche Implementierungen identisch benannter Methoden bereitzustellen. Visual Basic unterstützt darüber hinaus das `Implements`-Schlüsselwort, mit dem Sie explizit festlegen können, welche Schnittstelle und welcher Member von einem bestimmten Member implementiert werden. Im folgenden Beispiel wird dieses Szenario veranschaulicht, indem eine `Temperature`-Klasse definiert wird, die die `ICelsius`-Schnittstelle und die `IFahrenheit`-Schnittstelle als explizite Schnittstellenimplementierungen implementiert.

[!code-csharp[Conceptual.CLSCompliant#24](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/eii1.cs#24)]
[!code-vb[Conceptual.CLSCompliant#24](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/eii1.vb#24)]

<a name="enums"></a>

### <a name="enumerations"></a>Enumerationen

Bei CLS-kompatiblen Enumerationen müssen die folgenden Regeln beachtet werden:

- Der zugrunde liegende Typ der Enumeration muss ein systeminterner CLS-kompatibler Ganzzahltyp sein (<xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32> oder <xref:System.Int64>). Im folgenden Code wird beispielsweise versucht, eine Enumeration zu definieren, deren zugrunde liegender Typ <xref:System.UInt32> ist. Es wird eine Compilerwarnung generiert.

  [!code-csharp[Conceptual.CLSCompliant#7](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/enum3.cs#7)]
  [!code-vb[Conceptual.CLSCompliant#7](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/enum3.vb#7)]

- Ein Enumerationstyp muss über ein Feld namens `Value__` mit einer einzelnen Instanz verfügen, das mit dem <xref:System.Reflection.FieldAttributes.RTSpecialName?displayProperty=nameWithType>-Attribut markiert ist. Damit können Sie den Feldwert implizit verweisen.

- Eine Enumeration umfasst literale statische Felder, deren Typen vom gleichen Typ wie die Enumeration selbst sein müssen. Wenn Sie zum Beispiel eine `State`-Enumeration mit den Werten aus `State.On` und `State.Off` definieren, sind `State.On` und `State.Off` literale statische Felder, deren Typ `State` ist.

- Es gibt zwei Arten von Enumerationen.

  - Eine Enumeration, die einen Satz wechselseitig exklusiver, benannter ganzzahliger Werte darstellt. Dieser Typ der Enumeration wird durch das Fehlen des benutzerdefinierten <xref:System.FlagsAttribute?displayProperty=nameWithType>-Attributs angegeben.

  - Eine Enumeration, die einen Satz von Bitflags darstellt, die zum Generieren eines unbenannten Werts kombiniert werden können. Dieser Typ der Enumeration wird durch das Vorhandensein des benutzerdefinierten <xref:System.FlagsAttribute?displayProperty=nameWithType>-Attributs angegeben.

  Weitere Informationen finden Sie in der Dokumentation zur <xref:System.Enum>-Struktur.

- Der Wert einer Enumeration wird nicht auf den Bereich der angegebenen Werte beschränkt. Das heißt, der Wertebereich einer Enumeration ist der Bereich des zugrunde liegenden Werts. Sie können die <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>-Methode verwenden, um zu bestimmen, ob ein angegebener Wert ein Member einer Enumeration ist.

<a name="members"></a>

### <a name="type-members-in-general"></a>Typmember im Allgemeinen

Die Common Language Specification erfordert, dass auf alle Felder und Methoden als Member einer bestimmten Klasse zugegriffen werden. Daher sind globale statische Felder und Methoden (das heißt, statische Felder oder Methoden, die unabhängig von einem Typ definiert werden), nicht CLS-kompatibel. Wenn Sie versuchen, ein globales Feld oder eine Methode im Quellcode einzuschließen, wird vom C#-Compiler und vom Visual Basic-Compiler ein Compilerfehler generiert.

Die Common Language Specification unterstützt nur die verwaltete Standardaufrufkonvention. Sie unterstützt keine nicht verwalteten Aufrufkonventionen und keine Methoden mit variablen Argumentlisten, die mit dem `varargs`-Schlüsselwort gekennzeichnet werden. Verwenden Sie für Variablenargumentlisten, die mit der verwalteten Standardaufrufkonvention kompatibel sind, das <xref:System.ParamArrayAttribute>-Attribut oder die einzelne Implementierung der Sprache, wie z. B. das `params`-Schlüsselwort in C# und das `ParamArray`-Schlüsselwort in Visual Basic.

<a name="MemberAccess"></a>

### <a name="member-accessibility"></a>Memberzugriff

Das Überschreiben eines geerbten Members kann den Zugriff auf diesen Member nicht ändern. Beispielsweise kann eine öffentliche Methode in einer Basisklasse nicht von einer privaten Methode in einer abgeleiteten Klasse überschrieben werden. Es gibt allerdings eine Ausnahme: einen `protected internal`-Member (in C#) oder einen `Protected Friend`-Member (in Visual Basic) in einer Assembly, die von einem Typ in einer anderen Assembly überschrieben wird. In diesem Fall ist der Zugriff auf die Überschreibung `Protected`.

Im folgenden Beispiel wird der Fehler veranschaulicht, der generiert wird, wenn das <xref:System.CLSCompliantAttribute>-Attribut auf `true` festgelegt wird und `Human` , eine von `Animal` abgeleitete Klasse, versucht den Zugriff auf die `Species`-Eigenschaft von öffentlich auf privat zu ändern. Das Beispiel wird erfolgreich kompiliert, wenn der Zugriff auf öffentlich geändert wird.

[!code-csharp[Conceptual.CLSCompliant#28](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/accessibility1.cs#28)]
[!code-vb[Conceptual.CLSCompliant#28](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/accessibility1.vb#28)]

Der Zugriff auf Typen in der Signatur eines Members muss möglich sein, wenn auf den Member zugegriffen werden kann. Das bedeutet zum Beispiel, dass ein öffentlicher Member keinen Parameter enthalten kann, dessen Typ privat, geschützt oder intern ist. Im folgenden Beispiel wird der Compilerfehler veranschaulicht, der entsteht, wenn ein `StringWrapper`-Klassenkonstruktor einen internen `StringOperationType`-Enumerationswert verfügbar macht, der bestimmt, wie ein Zeichenfolgenwert umschlossen werden soll.

[!code-csharp[Conceptual.CLSCompliant#27](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/accessibility3.cs#27)]
[!code-vb[Conceptual.CLSCompliant#27](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/accessibility3.vb#27)]

<a name="Generics"></a>

### <a name="generic-types-and-members"></a>Generische Typen und Member

Geschachtelte Typen weisen immer mindestens so viele generische Parameter auf wie der einschließende Typ. Diese entsprechen der Position nach den generischen Parametern im einschließenden Typ. Der generische Typ kann auch neue generische Parameter enthalten.

Die Beziehung zwischen generischen Typparametern eines enthaltenden Typs und den geschachtelten Typen wird möglicherweise von der Syntax der einzelnen Sprachen verdeckt. Im folgenden Beispiel enthält ein generischer Typ `Outer<T>` zwei geschachtelte Klassen: `Inner1A` und `Inner1B<U>`. Die Aufrufe der `ToString`-Methode, die jede Klasse von <xref:System.Object.ToString%2A?displayProperty=nameWithType> erbt, zeigen, dass jede geschachtelte Klasse die Typparameter der enthaltenden Klasse umfasst.

[!code-csharp[Conceptual.CLSCompliant#29](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/nestedgenerics2.cs#29)]
[!code-vb[Conceptual.CLSCompliant#29](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/nestedgenerics2.vb#29)]

Namen generischer Typen werden in der Form *Name\`n* codiert. Dabei entspricht *Name* dem Namen des Typs, \` ist ein Zeichenliteral und *n* ist die Anzahl der Parameter, die für den Typ deklariert sind, oder die Anzahl der neu eingeführten Typparameter, wenn es sich um geschachtelte generische Typen handelt. Diese Codierung von Namen des generischen Typs ist hauptsächlich für Entwickler relevant, die Reflexion verwenden, um auf CLS-kompatible generische Typen in einer Bibliothek zuzugreifen.

Wenn Einschränkungen auf einen generischen Typ angewendet werden, müssen alle als Einschränkungen verwendeten Typen auch CLS-kompatibel sein. Im folgenden Beispiel wird eine Klasse namens `BaseClass` definiert, die nicht CLS-kompatibel ist sowie eine generische Klasse namens `BaseCollection` deren Typparameter von `BaseClass` abgeleitet werden muss. Aber, da `BaseClass` nicht CLS-kompatibel ist, gibt der Compiler eine Warnung aus.

[!code-csharp[Conceptual.CLSCompliant#34](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/generics5.cs#34)]
[!code-vb[Conceptual.CLSCompliant#34](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/generics5.vb#34)]

Wenn ein generischer Typ von einem generischen Basistyp abgeleitet ist, muss er alle Einschränkungen erneut deklarieren, damit sichergestellt ist, dass auch die Einschränkungen des Basistyps erfüllt werden. Im folgenden Beispiel wird `Number<T>` definiert, das einen numerischen Typ darstellen kann. Es definiert auch eine `FloatingPoint<T>`-Klasse, die einen Gleitkommawert darstellt. Allerdings kann der Quellcode nicht kompiliert werden, da die Einschränkung auf `Number<T>` (dieses T muss ein Werttyp sein) nicht auf `FloatingPoint<T>` angewendet werden.

[!code-csharp[Conceptual.CLSCompliant#30](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/generics2a.cs#30)]
[!code-vb[Conceptual.CLSCompliant#30](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/generics2a.vb#30)]

Das Beispiel wird erfolgreich kompiliert, wenn die Einschränkung der `FloatingPoint<T>`-Klasse hinzugefügt wird.

[!code-csharp[Conceptual.CLSCompliant#31](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/generics2.cs#31)]
[!code-vb[Conceptual.CLSCompliant#31](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/generics2.vb#31)]

Die Common Language Specification erzwingt ein konservatives Pro-Instanziierungsmodell für geschachtelte Typen und geschützte Member. Offene generische Typen können Felder oder Member mit Signaturen nicht verfügbar machen, die eine bestimmte Instanziierung eines geschachtelten, geschützten generischen Typs enthalten. Nicht generische Typen, die eine bestimmte Instanziierung einer generischen Basisklasse oder Schnittstelle erweitern, können Felder oder Member mit Signaturen nicht verfügbar machen, die eine andere Instanziierung eines geschachtelten, geschützten generischen Typs enthalten.

Im folgenden Beispiel wird ein generischer Typ, `C1<T>` (oder `C1(Of T)` in Visual Basic) und eine geschützte Klasse, `C1<T>.N` (oder `C1(Of T).N` in Visual Basic) definiert. `C1<T>` verfügt über zwei Methoden, `M1` und `M2`. Allerdings ist `M1` nicht CLS-kompatibel, da versucht wird, ein `C1<int>.N`-Objekt (oder `C1(Of Integer).N`)-Objekt von C1\<T> (oder `C1(Of T)`) zurückzugeben. Eine zweite Klasse, `C2`, ist von `C1<long>` abgeleitet (oder von `C1(Of Long)`). Sie verfügt über zwei Methoden, `M3` und `M4`. `M3` ist nicht CLS-kompatibel, da versucht wird, ein `C1<int>.N`-Objekt (oder `C1(Of Integer).N`) einer Unterklasse von `C1<long>` zurückzugeben. Beachten Sie, dass Sprachcompiler sogar noch restriktiver sein können. In diesem Beispiel zeigt Visual Basic einen Fehler an, wenn versucht wird, `M4` zu kompilieren.

[!code-csharp[Conceptual.CLSCompliant#32](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/generics4.cs#32)]
[!code-vb[Conceptual.CLSCompliant#32](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/generics4.vb#32)]

<a name="ctors"></a>

### <a name="constructors"></a>Konstruktoren

Bei Konstruktoren in den CLS-kompatiblen Klassen und Strukturen müssen die folgenden Regeln beachtet werden:

- Der Konstruktor einer abgeleiteten Klasse muss den Instanzkonstruktor der Basisklasse aufrufen, bevor er auf geerbte Instanzdaten zugreift. Diese Anforderung basiert auf der Tatsache, dass Konstruktoren nicht nach ihren abgeleiteten Klassen geerbt werden. Diese Regel gilt nicht für Strukturen, die keine direkte Vererbung unterstützen.

  In der Regel erzwingen Compiler diese Regel unabhängig von der CLS-Kompatibilität, wie im folgenden Beispiel gezeigt. Es wird eine `Doctor`-Klasse erstellt, die von einer `Person`-Klasse abgeleitet ist. Doch die `Doctor`-Klasse kann den `Person`-Klassenkonstruktor nicht zum Initialisieren geerbter Instanzfelder aufrufen.

  [!code-csharp[Conceptual.CLSCompliant#11](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/ctor1.cs#11)]
  [!code-vb[Conceptual.CLSCompliant#11](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/ctor1.vb#11)]

- Ein Objektkonstruktor kann nur aufgerufen werden, um ein Objekt zu erstellen. Außerdem kann ein Objekt nicht zweimal initialisiert werden. Das bedeutet zum Beispiel, dass <xref:System.Object.MemberwiseClone%2A?displayProperty=nameWithType> und solche Deserialisierungsmethoden wie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> keine Konstruktoren aufrufen dürfen.

<a name="properties"></a>

### <a name="properties"></a>Eigenschaften

Eigenschaften in den CLS-kompatiblen Typen müssen die folgenden Regeln beachten:

- Eine Eigenschaft muss über einen Setter, einen Getter oder beides verfügen. In einer Assembly werden diese als spezielle Methoden implementiert, das bedeutet, dass sie als separate Methoden (der Getter hat den Namen `get_`*Eigenschaftsname* und der Setter den Namen `set_`*Eigenschaftsname*) erscheinen, die als `SpecialName` gekennzeichnet in den Metadaten der Assembly angezeigt werden. Die Compiler von C# und Visual Basic erzwingen diese Regel automatisch, ohne das <xref:System.CLSCompliantAttribute>-Attribut anzuwenden.

- Ein Typ der Eigenschaft entspricht dem Rückgabetyp der Getter-Methode der Eigenschaft und dem letzten Argument der Setter-Methode. Diese Typen müssen CLS-kompatibel sein, und Argumente können der Eigenschaft nicht mithilfe eines Verweises zugewiesen werden (das heißt, es können keine verwalteten Zeiger sein).

- Wenn eine Eigenschaft einen Getter und einen Setter aufweist, müssen beide "virtual", "static" oder "instance" sein. Die Compiler von C#- und Visual Basic erzwingen diese Regel automatisch mithilfe der Eigenschaftendefinitionssyntax.

<a name="events"></a>

### <a name="events"></a>Ereignisse

Ein Ereignis wird vom Namen und dem Typ definiert. Der Ereignistyp ist ein Delegat, der zum Angeben des Ereignisses verwendet wird. Zum Beispiel hat das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignis den Typ <xref:System.ResolveEventHandler>. Neben dem Ereignis selbst, stellen drei Methoden mit Namen basierend auf dem Ereignisnamen die Implementierung des Ereignisses bereit und werden in den Metadaten der Assembly als `SpecialName` gekennzeichnet:

- Eine Methode zum Hinzufügen eines Ereignishandlers namens `add_`*Ereignisname*. Die Ereignisabonnementmethode für das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignis hat zum Beispiel den Namen `add_AssemblyResolve`.

- Eine Methode zum Entfernen eines Ereignishandlers namens `remove_`*Ereignisname*. Die Entfernenmethode für das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignis hat zum Beispiel den Namen `remove_AssemblyResolve`.

- Eine Methode für den Hinweis, dass das Ereignis namens `raise_`*Ereignisname* aufgetreten ist.

> [!NOTE]
> Die meisten Regeln der Common Language Specification zu Ereignissen werden von den Sprachcompilern implementiert und sind für Komponentenentwickler transparent.

Die Methoden für das Hinzufügen, Entfernen und Auslösen des Ereignisses verfügen über den gleichen Zugriff. Sie müssen zudem "static", "instance" oder "virtual" sein. Die Methoden zum Hinzufügen und Entfernen eines Ereignisses verfügen über einen Parameter, dessen Typ der Ereignisdelegattyp ist. Die Methoden zum Hinzufügen und Entfernen müssen beide vorhanden sein oder beide fehlen.

Im folgenden Beispiel wird eine CLS-kompatible Klasse namens `Temperature` definiert, die ein `TemperatureChanged`-Ereignis auslöst, wenn die Temperaturänderung zwischen zwei Messungen einem Schwellenwert entspricht oder diesen überschreitet. Die `Temperature`-Klasse definiert eine `raise_TemperatureChanged`-Methode explizit, sodass sie selektiv Ereignishandler ausführen kann.

[!code-csharp[Conceptual.CLSCompliant#20](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/event1.cs#20)]
[!code-vb[Conceptual.CLSCompliant#20](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/event1.vb#20)]

<a name="overloads"></a>

### <a name="overloads"></a>Overloads

Die Common Language Specification erzwingt die folgenden Anforderungen für überladene Member:

- Member können auf Grundlage der Anzahl und des Typs eines Parameters überladen werden. Aufrufkonvention, Rückgabetyp, die benutzerdefinierten Modifizierer, die auf die Methode oder deren Parameter angewendet werden und, ob Parameter nach Wert oder nach Verweis übergeben werden, werden bei der Unterscheidung zwischen Überladungen nicht beachtet. Ein Beispiel finden Sie im Abschnitt [Namenskonventionen](#naming) im Code für die Anforderung, dass Namen innerhalb eines Bereichs eindeutig sein müssen.

- Nur Eigenschaften und Methoden können überladen werden. Felder und Ereignisse können nicht überladen werden.

- Generische Methoden können auf Grundlage der Anzahl ihrer generischen Parameter überladen werden.

> [!NOTE]
> Der `op_Explicit`-Operator und der `op_Implicit`-Operator sind Ausnahmen von der Regel, dass Rückgabewerte nicht als Teil einer Methodensignatur für Überladungsauflösung gelten. Diese beiden Operatoren können auf Grundlage ihrer Parameter und ihrer Rückgabewerte überladen werden.

<a name="exceptions"></a>

### <a name="exceptions"></a>Ausnahmen

Ausnahmeobjekte müssen von <xref:System.Exception?displayProperty=nameWithType> oder von einem anderen Typ abgeleitet werden, der von <xref:System.Exception?displayProperty=nameWithType> abgeleitet wird. Im folgenden Beispiel wird der Compilerfehler veranschaulicht, der entsteht, wenn eine benutzerdefinierte Klasse namens `ErrorClass` für die Ausnahmebehandlung verwendet wird.

[!code-csharp[Conceptual.CLSCompliant#13](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/exceptions1.cs#13)]
[!code-vb[Conceptual.CLSCompliant#13](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/exceptions1.vb#13)]

Um diesen Fehler zu beheben, muss die `ErrorClass`-Klasse von <xref:System.Exception?displayProperty=nameWithType> erben. Außerdem muss die `Message`- Eigenschaft überschrieben werden. Im folgenden Beispiel werden diese Fehler korrigiert, um eine CLS-kompatible `ErrorClass`-Klasse zu definieren.

[!code-csharp[Conceptual.CLSCompliant#14](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/exceptions2.cs#14)]
[!code-vb[Conceptual.CLSCompliant#14](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/exceptions2.vb#14)]

<a name="attributes"></a>

### <a name="attributes"></a>Attribute

In .NET-Frameworkassemblys stellen benutzerdefinierte Attribute einen erweiterbaren Mechanismus zum Speichern benutzerdefinierter Attribute und das Abrufen von Metadaten über Programmierobjekte, wie Assemblys, Typen, Member und Methodenparameter, bereit. Benutzerdefinierte Attribute müssen von <xref:System.Attribute?displayProperty=nameWithType> oder einem Typ abgeleitet werden, der von <xref:System.Attribute?displayProperty=nameWithType> abgeleitet wird.

Das folgende Beispiel verstößt gegen diese Regel. Es wird eine `NumericAttribute`-Klasse definiert, die nicht von <xref:System.Attribute?displayProperty=nameWithType> abgeleitet ist. Beachten Sie, dass der Compilerfehler nur entsteht, wenn das nicht CLS-kompatible Attribut angewendet wird, nicht aber, wenn die Klasse definiert ist.

[!code-csharp[Conceptual.CLSCompliant#18](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/attribute1.cs#18)]
[!code-vb[Conceptual.CLSCompliant#18](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/attribute1.vb#18)]

Der Konstruktor oder die Eigenschaften eines CLS-kompatiblen Attributs können nur die folgenden Typen verfügbar machen:

- <xref:System.Boolean>

- <xref:System.Byte>

- <xref:System.Char>

- <xref:System.Double>

- <xref:System.Int16>

- <xref:System.Int32>

- <xref:System.Int64>

- <xref:System.Single>

- <xref:System.String>

- <xref:System.Type>

- Ein Enumerationstyp, dessen zugrunde liegender Typ <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32> oder <xref:System.Int64> ist.

Im folgenden Beispiel wird eine von `DescriptionAttribute` abgeleitete <xref:System.Attribute>-Klasse definiert. Der Klassenkonstruktor verfügt über einen Parameter des Typs `Descriptor`, sodass die Klasse nicht CLS-kompatibel ist. Beachten Sie, dass der C#-Compiler eine Warnung ausgibt, aber erfolgreich kompiliert, während der Visual Basic-Compiler weder eine Warnung noch einen Fehler ausgibt.

[!code-csharp[Conceptual.CLSCompliant#33](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/attribute2.cs#33)]
[!code-vb[Conceptual.CLSCompliant#33](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/attribute2.vb#33)]

<a name="CLSAttribute"></a>

## <a name="the-clscompliantattribute-attribute"></a>Das CLSCompliantAttribute-Attribut

Das <xref:System.CLSCompliantAttribute>-Attribut wird verwendet, um anzugeben, ob ein Programmelement mit der Common Language Specification kompatibel ist. Der <xref:System.CLSCompliantAttribute.%23ctor%28System.Boolean%29?displayProperty=nameWithType>-Konstruktor enthält einen einzelnen erforderlichen Parameter, `isCompliant`, der angibt, ob das Programmelement CLS-kompatibel ist.

Zur Kompilierzeit erkennt der Compiler nicht kompatible Elemente, von denen angenommen wird, dass sie CLS-kompatibel sind, und gibt eine Warnung aus. Der Compiler gibt keine Warnungen für die Typen oder Member aus, die explizit als nicht kompatibel deklariert werden.

Komponentenentwickler können das <xref:System.CLSCompliantAttribute>-Attribut auf zwei Arten verwenden:

- Um die Teile der öffentlichen Schnittstelle zu definieren, die von einer CLS-kompatiblen Komponente und den nicht CLS-kompatiblen Teilen verfügbar gemacht werden. Wenn das Attribut verwendet wird, um bestimmte Programmelemente als CLS-kompatibel zu markieren, stellt seine Verwendung sicher, dass auf diese Elemente aus allen Sprachen und Tools für das .NET Framework zugegriffen werden kann.

- Um sicherzustellen, dass die öffentliche Schnittstelle der Komponentenbibliothek nur Programmelemente verfügbar macht, die CLS-kompatibel sind. Wenn Elemente nicht CLS-kompatibel sind, geben Compiler im Allgemeinen eine Warnung aus.

> [!WARNING]
> In einigen Fällen erzwingen CLS-kompatible Sprachcompiler Regeln unabhängig davon, ob das <xref:System.CLSCompliantAttribute>-Attribut verwendet wird. Das Definieren eines statischen Members in einer Schnittstelle verstößt zum Beispiel gegen eine CLS-Regel. In dieser Hinsicht zeigen die Compiler von C# und Visual Basic eine Fehlermeldung an und können die App nicht kompilieren, wenn Sie einen `static`-Member (in C#) oder einen `Shared`-Member (in Visual Basic) in einer Schnittstelle definieren.

Das <xref:System.CLSCompliantAttribute>-Attribut wird mit einem <xref:System.AttributeUsageAttribute>-Attribut markiert, das über einen Wert von <xref:System.AttributeTargets.All?displayProperty=nameWithType> verfügt. Dieser Wert ermöglicht das Anwenden des <xref:System.CLSCompliantAttribute>-Attributs auf jedem Programmelement, einschließlich Assemblys, Modulen, Typen (Klassen, Strukturen, Enumerationen, Schnittstellen und Delegaten), Typmembern (Konstruktoren, Methoden, Eigenschaften, Feldern und Ereignissen), Parametern, generischen Parametern und Rückgabewerten. In der Praxis sollten Sie das Attribut allerdings nur auf Assemblys, Typen und Typmember anwenden. Andernfalls ignorieren Compiler das Attribut und generieren weiterhin Compilerwarnungen, wenn sie einen nicht kompatiblen Parameter, einen generischen Parameter oder einen Rückgabewert in der öffentlichen Schnittstelle der Bibliothek vorfinden.

Der Wert des <xref:System.CLSCompliantAttribute>-Attributs wird von enthaltenen Programmelementen geerbt. Wenn beispielsweise eine Assembly als CLS-kompatibel markiert ist, sind die Typen auch CLS-kompatibel. Wenn ein Typ als CLS-kompatibel gekennzeichnet ist, sind seine geschachtelten Typen und Member auch CLS-kompatibel.

Sie können die geerbte Kompatibilität explizit überschreiben, indem Sie das <xref:System.CLSCompliantAttribute>- Attribut auf ein enthaltenes Programmelement anwenden. Beispielsweise können Sie das <xref:System.CLSCompliantAttribute>-Attribut mit einem Wert von `isCompliant``false` verwenden, um einen inkompatiblen Typ in einer kompatiblen Assembly zu definieren, und Sie können das Attribut mit einem Wert von `isCompliant``true` verwenden, um einen kompatiblen Typ in einer inkompatiblen Assembly zu definieren. Sie können auch nicht kompatible Member in einem kompatiblen Typ definieren. Allerdings kann ein nicht kompatibler Typ keine kompatiblen Member aufweisen, sodass Sie das Attribut nicht mit einem Wert von `isCompliant``true` verwenden können, um die Vererbung eines nicht kompatiblen Typs zu überschreiben.

Wenn Sie Komponenten entwickeln, sollten Sie stets das <xref:System.CLSCompliantAttribute>- Attribut verwenden, um anzugeben, ob die Assembly, die Typen und die Member CLS-kompatibel sind.

So erstellen Sie CLS-kompatible Komponenten:

1. Verwenden Sie <xref:System.CLSCompliantAttribute>, um die Assembly als CLS-kompatibel zu markieren.

2. Markieren Sie jeden öffentlich verfügbar gemachten, nicht CLS-kompatiblen Typ in der Assembly als nicht kompatibel.

3. Markieren Sie alle öffentlich verfügbar gemachten Member in CLS-kompatiblen Typen als nicht kompatibel.

4. Stellen Sie eine CLS-kompatible Alternative für nicht CLS-kompatible Member bereit.

Wenn alle inkompatiblen Typen und Member erfolgreich markiert wurden, sollte der Compiler keine Kompatibilitätswarnungen ausgeben. Allerdings sollten Sie angeben, welche Member nicht CLS-kompatibel sind und ihre CLS-kompatiblen Alternativen in der Produktdokumentation aufführen.

Im folgenden Beispiel wird das <xref:System.CLSCompliantAttribute>-Attribut verwendet, um eine CLS-kompatible Assembly und einen Typ, `CharacterUtilities`, zu definieren, der über zwei nicht CLS-kompatible Member verfügt. Da beide Member mit dem `CLSCompliant(false)`-Attribut markiert sind, generiert der Compiler keine Warnungen. Die Klasse stellt auch eine CLS-kompatible Alternative für beide Methoden bereit. Normalerweise würden der `ToUTF16`- Methode lediglich zwei Überladungen hinzugefügt werden, um CLS-kompatible Alternativen bereitzustellen. Da Methoden aber nicht aufgrund des Rückgabewerts überladen werden können, sind die Namen der CLS-kompatiblen Methoden von den Namen der nicht kompatiblen Methoden unterschiedlich.

[!code-csharp[Conceptual.CLSCompliant#35](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.clscompliant/cs/indicator3.cs#35)]
[!code-vb[Conceptual.CLSCompliant#35](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.clscompliant/vb/indicator3.vb#35)]

Wenn Sie eine App anstelle einer Bibliothek entwickeln, (das heißt, wenn Sie keine Typen oder Member verfügbar machen, die von anderen App-Entwicklern genutzt werden können), ist die CLS-Kompatibilität der Programmelemente, die von der App genutzt werden, nur relevant, wenn sie von Ihrer Sprache nicht unterstützt werden. In diesem Fall generiert der Sprachcompiler einen Fehler, wenn Sie versuchen, ein nicht CLS-kompatibles Element zu verwenden.

<a name="CrossLang"></a>

## <a name="cross-language-interoperability"></a>Sprachübergreifende Interoperabilität

Der Begriff „Sprachunabhängigkeit“ kann mehrere Bedeutungen haben. Eine Bedeutung, die im Artikel [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../docs/standard/language-independence-and-language-independent-components.md) erläutert wird, bezeichnet die nahtlose Nutzung von Typen, die in einer Sprache geschrieben wurden, durch eine App, die in einer anderen Sprache geschrieben wurde. Eine zweite Bedeutung, die in diesem Artikels hervorgehoben wird, umfasst die Kombination von Code aus mehreren Sprachen in einer einzelnen .NET Framework-Assembly.

Das folgende Beispiel veranschaulicht die sprachübergreifende Interoperabilität. Es wird die Klassenbibliothek Utilities.dll erstellt, die zwei Klassen einschließt: `NumericLib` und `StringLib`. Die `NumericLib`-Klasse wurde in C# und die `StringLib`-Klasse in Visual Basic geschrieben. Im Folgenden sehen Sie den Quellcode für "StringUtil.vb", der in der `ToTitleCase`-Klasse einen einzelnen Member enthält, `StringLib`.

[!code-vb[Conceptual.CrossLanguage#1](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.crosslanguage/vb/stringutil.vb#1)]

Im Folgenden sehen Sie den Quellcode für "NumberUtil.cs", der eine `NumericLib`-Klasse mit zwei Membern definiert: `IsEven` und `NearZero`.

[!code-csharp[Conceptual.CrossLanguage#2](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.crosslanguage/cs/numberutil.cs#2)]

Um die beiden Klassen in einer einzelnen Assembly zu verpacken, müssen Sie sie in Module kompilieren. Verwenden Sie zum Kompilieren der Visual Basic-Quellcodedatei in einem Modul folgenden Befehl:

```console
vbc /t:module StringUtil.vb
```

Weitere Informationen zur Befehlszeilensyntax des Visual Basic-Compilers finden Sie unter [Erstellen von der Befehlszeile aus](../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).

Verwenden Sie zum Kompilieren der C#-Quellcodedatei in einem Modul folgenden Befehl:

```console
csc /t:module NumberUtil.cs
```

Weitere Informationen zur Befehlszeilensyntax des C#-Compilers finden Sie unter [Erstellen über die Befehlszeile mit csc.exe](../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).

Verwenden Sie dann die [Linker-Optionen](/cpp/build/reference/linker-options), um die beiden Module in eine Assembly zu kompilieren:

```console
link numberutil.netmodule stringutil.netmodule /out:UtilityLib.dll /dll
```

Das folgende Beispiel ruft dann die `NumericLib.NearZero`-Methode und die `StringLib.ToTitleCase`-Methode auf. Beachten Sie, dass sowohl der Visual Basic-Code als auch der C#-Code auf die Methoden in beiden Klassen zugreifen können.

[!code-csharp[Conceptual.CrossLanguage#3](../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.crosslanguage/cs/useutilities1.cs#3)]
[!code-vb[Conceptual.CrossLanguage#3](../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.crosslanguage/vb/useutilities1.vb#3)]

Verwenden Sie zum Kompilieren des Visual Basic-Codes folgenden Befehl:

```console
vbc example.vb /r:UtilityLib.dll
```

Zum Kompilieren mit C# ändern Sie den Namen des Compilers von **vbc** in **csc** und die Dateierweiterung von „.vb“ in „.cs“:

```console
csc example.cs /r:UtilityLib.dll
```

## <a name="see-also"></a>Siehe auch

- <xref:System.CLSCompliantAttribute>
