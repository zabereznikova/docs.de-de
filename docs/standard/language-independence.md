---
title: Sprachunabhängigkeit und sprachunabhängige Komponenten
description: 'Erfahren Sie, wie Sie in einer der vielen in .NET unterstützten Sprachen entwickeln können: u.a. C#, C++/CLI, F#, IronPython, VB, Visual COBOL und PowerShell.'
ms.date: 07/22/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: 2dbed1bc-86f5-43cd-9a57-adbb1c5efba4
ms.openlocfilehash: e1f419dd57c1e90d7ebb57ef572f338a34d1c509
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423637"
---
# <a name="language-independence-and-language-independent-components"></a>Sprachunabhängigkeit und sprachunabhängige Komponenten

.NET ist sprachunabhängig. Dies bedeutet, dass Sie als Entwickler in einer von vielen Sprachen für die .NET-Implementierung entwickeln können, beispielsweise C#, F# und Visual Basic. Sie können auf die Typen und Member von Klassenbibliotheken zugreifen, die für die .NET-Implementierung entwickelt wurden, ohne die Sprache, in der sie ursprünglich geschrieben wurden, kennen und ohne den Konventionen der Originalsprache folgen zu müssen. Wenn Sie ein Komponentenentwickler sind, kann von allen .NET-Apps sprachunabhängig auf die Komponente zugegriffen werden.

> [!NOTE]
> In diesem Artikel wird das Erstellen sprachunabhängiger Komponenten erläutert. Diese Komponenten können von Apps verwendet werden, die in einer beliebigen Sprache geschrieben wurden. Sie können auch eine einzelne Komponente oder App aus Quellcode erstellen, der in mehreren Sprachen geschrieben wurde. Weitere Informationen finden Sie im zweiten Teil dieses Artikels unter [Sprachübergreifende Interoperabilität](#cross-language-interoperability).

Um vollständig mit anderen Objekten zu interagieren, die in irgendeiner Programmiersprache geschrieben wurden, müssen die Objekte den Aufrufern nur die Funktionen verfügbar machen, die allen Sprachen gemeinsam sind. Dieser gemeinsame Satz von Funktionen wird von der CLS (Common Language Specification) definiert. Das ist ein Satz von Regeln, die für generierte Assemblys gelten. Die Common Language Specification wird in der Partition I, in den Klauseln 7 bis 11 im [ECMA 335-Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm) definiert.

Wenn die Komponente der Common Language Specification entspricht, ist sichergestellt, dass sie CLS-kompatibel ist, und dass vom Code in Assemblys, die in irgendeiner CLS unterstützenden Programmiersprache geschrieben wurden, aus auf sie zugegriffen werden kann. Sie können bestimmen, ob die Komponente zur Kompilierzeit der Common Language Specification entspricht, indem Sie das [CLSCompliantAttribute](xref:System.CLSCompliantAttribute)-Attribut auf den Quellcode anwenden. Weitere Informationen finden Sie im Abschnitt zum [CLSCompliantAttribute-Attribut](#the-clscompliantattribute-attribute).

In diesem Artikel:

* [CLS-Kompatibilitätsregeln](#cls-compliance-rules)

  * [Typen und Typmembersignaturen](#types-and-type-member-signatures)

  * [Namenskonventionen](#naming-conventions)

  * [Typkonvertierung](#type-conversion)

  * [Arrays](#arrays)

  * [Schnittstellen](#interfaces)

  * [Enumerationen](#enumerations)

  * [Typmember im Allgemeinen](#type-members-in-general)

  * [Memberzugriff](#member-accessibility)

  * [Generische Typen und Member](#generic-types-and-members)

  * [Konstruktoren](#constructors)

  * [Eigenschaften](#properties)

  * [Ereignisse](#events)

  * [Überladungen](#overloads)

  * [Ausnahmen](#exceptions)

  * [Attribute](#attributes)

* [CLSCompliantAttribute-Attribut](#the-clscompliantattribute-attribute)

* [Sprachübergreifende Interoperabilität](#cross-language-interoperability)

## <a name="cls-compliance-rules"></a>CLS-Kompatibilitätsregeln

In diesem Abschnitt werden die Regeln zum Erstellen einer CLS-kompatiblen Komponente beschrieben. Eine vollständige Liste der Regeln finden Sie unter Partition I, Klausel 11 im [ECMA 335-Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

> [!NOTE]
> In der Common Language Specification wird für jede Regel der CLS-Kompatibilität erläutert, wie sie auf Consumer (Entwickler, die programmgesteuert auf eine CLS-kompatible Komponente zugreifen), Frameworks (Entwickler, die einen Sprachcompiler zum Erstellen von CLS-kompatiblen Bibliotheken verwenden) und Extender (Entwickler, die zum Erstellen CLS-kompatibler Komponenten ein Tool, wie einen Sprachcompiler oder einen Codeparser, erstellen) anzuwenden ist. In diesem Artikel wird auf die Anwendbarkeit der Regeln für Frameworks eingegangen. Beachten Sie allerdings, dass möglicherweise einige der Regeln für Extender auch auf Assemblys anwendbar sind, die mithilfe von [Reflection.Emit](xref:System.Reflection.Emit) erstellt werden.

Um eine sprachenneutrale Komponente zu entwerfen, müssen Sie nur die CLS-Kompatibilitätregeln auf die öffentliche Schnittstelle der Komponente anwenden. Die private Implementierung muss nicht mit der Spezifikation konform sein.

> [!IMPORTANT]
> Die Regeln für CLS-Kompatibilität gelten nur für die öffentlichen Schnittstelle einer Komponente, nicht für die private Implementierung.

Zum Beispiel sind ganze Zahlen ohne Vorzeichen, außer [Byte](xref:System.Byte), nicht CLS-kompatibel. Da die `Person`-Klasse im folgenden Beispiel eine `Age`-Eigenschaft des Typs [UInt16](xref:System.UInt16) verfügbar macht, zeigt der folgende Code eine Compilerwarnung an.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private UInt16 personAge = 0;

   public UInt16 Age
   { get { return personAge; } }
}
// The attempt to compile the example displays the following compiler warning:
//    Public1.cs(10,18): warning CS3003: Type of 'Person.Age' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As UInt16
      Get
         Return personAge
      End Get
   End Property
End Class
' The attempt to compile the example displays the following compiler warning:
'    Public1.vb(9) : warning BC40027: Return type of function 'Age' is not CLS-compliant.
'
'       Public ReadOnly Property Age As UInt16
'                                ~~~
```

Sie können CLS-Kompatibilität für die Person-Klasse erreichen, indem Sie den Typ der `Age`-Eigenschaft von `UInt16` in [Int16](xref:System.Int16) ändern. Dies ist eine CLS-kompatible ganze Zahl mit Vorzeichen und einer Länge von 16 Bit. Sie müssen den Typ des privaten `personAge`-Felds nicht ändern.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private Int16 personAge = 0;

   public Int16 Age
   { get { return personAge; } }
}
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As Int16
      Get
         Return CType(personAge, Int16)
      End Get
   End Property
End Class
```

Die öffentliche Schnittstelle einer Bibliothek besteht aus folgenden Elementen:

* Definitionen öffentlicher Klassen

* Definitionen öffentlicher Member von öffentlichen Klassen sowie in Definitionen von Membern, auf die abgeleitete Klassen zugreifen können (d. h. geschützte Member).

* Parameter und Rückgabetypen öffentlicher Methoden von öffentlichen Klassen sowie Parameter und Rückgabetypen von Methoden, auf die abgeleitete Klassen zugreifen können.

Die Regeln für CLS-Kompatibilität werden in der folgenden Tabelle aufgeführt. Der Text der Regeln wird in vollem Wortlaut dem [ECMA 335-Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm) entnommen. Copyright 2012 durch Ecma-International. Ausführlichere Informationen zu diesen Regeln finden Sie in den folgenden Abschnitten.

Kategorie | Siehe | Regel | Regelzahl
-------- | --- | ---- | -----------
Zugriff | [Memberzugriff](#member-accessibility) | Beim Überschreiben von geerbten Methoden darf der Zugriff nicht geändert werden, außer wenn eine Methode überschrieben wird, die von einer anderen Assembly mit `family-or-assembly`-Zugriff vererbt wurde. In diesem Fall muss für die Überschreibung `family`-Zugriff festgelegt werden. | 10
Zugriff | [Memberzugriff](#member-accessibility) | Die Sichtbarkeit und der Zugriff von Typen und Membern soll so beschaffen sein, dass Typen in der Signatur eines Members sichtbar und zugreifbar sind, wann immer der Member selbst sichtbar und zugreifbar ist. Zum Beispiel soll eine öffentliche Methode, die außerhalb der Assembly sichtbar ist, über kein Argument verfügen, dessen Typ nur innerhalb der Assembly sichtbar ist. Die Sichtbarkeit und der Zugriff von Typen, die einen instanziierten generischen Typ zusammensetzen, der in der Signatur eines beliebigen Members verwendet wird, soll sichtbar und zugreifbar sein, wenn der Member selbst sichtbar und zugreifbar ist. Zum Beispiel soll ein instanziierter generischer Typ, der in der Signatur eines außerhalb der Assembly sichtbaren Members vorhanden ist, über kein generisches Argument verfügen, dessen Typ nur innerhalb der Assembly sichtbar ist. | 12
Arrays | [Arrays](#arrays) | Arrays müssen über Elemente mit einem CLS-kompatiblen Typ verfügen, und die Untergrenze aller Dimensionen des Arrays muss Null sein. Nur der Tatsache, dass es sich bei einem Element um ein Array handelt sowie der Elementtyp des Arrays muss zur Unterscheidung zwischen Überladungen ausreichen. Wenn das Überladen auf Grundlage mindestens zweier Arraytypen erfolgt, muss es sich bei den Elementtypen um benannte Typen handeln. | 16
Attribute | [Attribute](#attributes) | Attribute müssen vom Typ [System.Attribute](xref:System.Attribute) sein oder von diesem erben. | 41
Attribute | [Attribute](#attributes) | CLS gestattet nur eine Teilmenge der Codierungen benutzerdefinierter Attribute. Die einzigen Typen, die in diesen Codierungen angezeigt werden sollen, sind (gemäß Partition IV): [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double) und jeder Enumerationstyp basierend auf einem CLS-kompatiblen ganzzahligen Basistyp. | 34
Attribute | [Attribute](#attributes) | Nach der CLS sind nicht öffentlich sichtbare erforderliche Modifizierer (`modreq`, siehe Partition II) zulässig, allerdings sind optionale Modifizierer (`modopt`, siehe Partition II), die sie nicht versteht, zulässig. | 35
Konstruktoren | [Konstruktoren](#constructors) | Ein Objektkonstruktor muss einen Instanzenkonstruktor seiner Basisklasse aufrufen, bevor ein Zugriff auf geerbte Instanzdaten erfolgt. (Dies gilt nicht für Werttypen, die über keine Konstruktoren verfügen müssen.)  | 21
Konstruktoren | [Konstruktoren](#constructors) | Ein Objektkonstruktor darf nicht aufgerufen werden, außer als Teil bei der Erstellung eines Objekts und ein Objekt darf nicht zweimal initialisiert werden. | 22
Enumerationen | [Enumerationen](#enumerations) | Der zugrunde liegende Typ einer Enumeration muss ein integrierter CLS-Ganzzahltyp sein, der Name des Felds muss "value__" lauten, und das Feld muss als `RTSpecialName` gekennzeichnet sein. |  7
Enumerationen | [Enumerationen](#enumerations) | Es gibt zwei verschiedene Arten von Enumerationen, die aufgrund des Vorhandenseins oder Fehlens des benutzerdefinierten Attributs [System.FlagsAttribute](xref:System.FlagsAttribute) (gemäß Partition IV Library) angegeben werden. Eine stellt benannte ganzzahlige Werte dar, die Andere stellt benannte Bitflags dar, die zum Generieren eines unbenannten Werts kombiniert werden können. Der Wert einer `enum` ist nicht auf die angegebenen Werte beschränkt. |  8
Enumerationen | [Enumerationen](#enumerations) | Literale statische Felder einer Enumeration müssen vom Typ der Enumeration selbst sein. |  9
Ereignisse | [Ereignisse](#events) | Die Methoden, die ein Ereignis implementieren, müssen in den Metadaten als `SpecialName` gekennzeichnet sein. |29
Ereignisse | [Ereignisse](#events) | Der Zugriff eines Ereignisses und seiner Zugriffsmethoden muss identisch sein. |30
Ereignisse | [Ereignisse](#events) | Die `add` und `remove`-Methoden eines Ereignisses müssen entweder beide vorhanden oder beide nicht vorhanden sein. |31
Ereignisse | [Ereignisse](#events) | Die `add`- und `remove`-Methoden eines Ereignisses müssen jeweils einen Parameter akzeptieren, dessen Typ den Ereignistyp definiert. Dieser Typ muss von [System.Delegate](xref:System.Delegate) abgeleitet sein. |32
Ereignisse | [Ereignisse](#events) | Ereignisse müssen einem bestimmten Benennungsschema folgen. Das SpecialName-Attribut, auf das in CLS-Regel 29 verwiesen wird, muss in den entsprechenden Namensvergleichen ignoriert werden und Bezeichnerregeln einhalten.  |33
Ausnahmen | [Ausnahmen](#exceptions) | Ausgelöste Objekte müssen vom Typ [System.Exception](xref:System.Exception) oder einem davon geerbten Typ sein. Dennoch müssen CLS-kompatible Methoden die Weitergabe anderer Ausnahmetypen nicht blockieren. | 40
Allgemein | [CLS-Kompatibilitätsregeln](#cls-compliance-rules) | CLS-Regeln gelten nur für die Teile eines Typs, die außerhalb der definierenden Assembly sichtbar sind und auf die außerhalb der definierenden Assembly zugegriffen werden kann. | 1
Allgemein | [CLS-Kompatibilitätsregeln](#cls-compliance-rules) | Member von Typen, die nicht CLS-kompatibel sind, dürfen nicht als CLS-kompatibel gekennzeichnet werden. | 2
Generics | [Generische Typen und Member](#generic-types-and-members) | Geschachtelte Typen müssen mindestens so viele generische Parameter aufweisen wie der einschließende Typ. Die Position von generischen Parametern in einem geschachtelten Typ entspricht der Position der generischen Parameter im einschließenden Typ.  | 42
Generics | [Generische Typen und Member](#generic-types-and-members) | Der Name eines generischen Typs muss die Anzahl von Typparametern, die auf dem nicht geschachtelten Typ deklariert oder neu in den Typ eingeführt werden, kodieren, wenn er entsprechend der oben definierten Regeln geschachtelt ist. | 43
Generics | [Generische Typen und Member](#generic-types-and-members) | Ein generischer Typ muss genügend Einschränkungen neu deklarieren, um zu gewährleisten, dass alle Einschränkungen des Basistyps oder der Schnittstellen durch die Einschränkungen des generischen Typs erfüllt sein würden. | 44
Generics | [Generische Typen und Member](#generic-types-and-members) | Als Einschränkungen für generische Parameter verwendete Typen müssen selbst CLS-kompatibel sein. | 45
Generics | [Generische Typen und Member](#generic-types-and-members) | Es muss davon ausgegangen werden, dass die Sichtbarkeit und der Zugriff auf Member (einschließlich geschachtelter Typen) in einem instanziierten generischen Typ sich nicht auf die gesamte Deklaration des generischen Typs bezieht, sondern auf die spezifische Instanziierung. Davon ausgehend gelten die Sichtbarkeits- und Zugriffsregeln der CLS-Regel 12 weiterhin. | 46
Generics | [Generische Typen und Member](#generic-types-and-members) | Für jede abstrakte oder virtuell generische Methode muss es eine konkrete (nicht abstrakte) Standardimplementierung geben. | 47
Schnittstellen | [Schnittstellen](#interfaces) | Zum Implementieren von CLS-kompatiblen Schnittstellen darf keine Definition von nicht CLS-kompatiblen Methoden erforderlich sein. | 18
Schnittstellen | [Schnittstellen](#interfaces) | CLS-kompatible Schnittstellen dürfen weder statische Methoden noch Felder definieren. | 19
Member | [Typmember im Allgemeinen](#type-members-in-general) | Globale static-Felder und Methoden sind nicht CLS-kompatibel. | 36
Member | -- | Der Wert eines literalen statischen Elements wird von der Verwendung von Feldinitialisierungsmetadaten angegeben. Ein CLS-kompatibles Literal muss über einen Wert verfügen, der in den Feldinitialisierungsmetadaten angegeben wird, der genau vom gleichen Typ wie das Literal ist (oder des zugrunde liegenden Typs, wenn dieses Literal `enum` ist). | 13
Member | [Typmember im Allgemeinen](#type-members-in-general) | Die vararg-Einschränkung ist nicht Teil der CLS, und die einzige Aufrufkonvention, die von der CLS unterstützt wird, ist die verwaltete Standardaufrufkonvention. | 15
Namenskonventionen | [Namenskonventionen](#naming-conventions) | Assemblys müssen Anhang 7 von Fachbericht 15 des Unicode Standard3.0 folgen, in dem der Satz von Zeichen geregelt wird, die am Anfang oder innerhalb von Bezeichnern enthalten sein dürfen. Er ist online unter [Unicode Normalization Forms](https://www.unicode.org/unicode/reports/tr15/tr15-18.html) (Unicode-Normalisierungsformen) verfügbar. Bezeichner müssen im kanonischen Format vorliegen, das durch die Unicode-Normalisierungsform C definiert wird. Im Sinne der CLS sind zwei Bezeichner gleich, wenn ihre kleingeschriebenen Zuordnungen (wie von den Gebietsschema-unabhängigen, klein geschriebenen 1:1-Unicodezuordnungen angegeben) gleich sind. Demnach müssen sich zwei Bezeichner in mehr als nur der Großschreibung unterscheiden, damit sie gemäß der CLS als unterschiedlich angesehen werden können. Um jedoch eine geerbte Definition überschreiben zu können, erfordert die CLI die genaue Codierung der ursprünglichen Deklaration. | 4
Überladen | [Namenskonventionen](#naming-conventions) | Alle Namen, die in einem CLS-kompatiblen Bereich eingeführt werden, müssen in ihrer Art eindeutig unabhängig sein, außer bei identischen Namen, die durch Überladen aufgelöst werden. Während es bei CTS möglich ist, dass ein einzelner Typ denselben Namen für eine Methode und ein Feld verwendet, ist dies bei CLS demnach unmöglich. | 5
Überladen | [Namenskonventionen](#naming-conventions) | Felder und geschachtelte Typen müssen allein durch Vergleich des Bezeichners zu unterscheiden sein, auch wenn bei CTS verschiedene Signaturen unterschieden werden können. Methoden, Eigenschaften und Ereignisse mit demselben Namen (nach Bezeichnervergleich) müssen sich durch mehr als nur den Rückgabetyp unterscheiden (außer wie in CLS-Regel 39 angegeben). | 6
Überladen | [Overloads](#overloads) | Nur Eigenschaften und Methoden können überladen werden. | 37
Überladen | [Overloads](#overloads) |Eigenschaften und Methoden können allein basierend auf der Anzahl und den Typen ihrer Parameter überladen werden, außer den Konvertierungsoperatoren `op_Implicit` und `op_Explicit`, die auch auf Grundlage des Rückgabetyps überladen werden können. | 38
Überladen | -- | Wenn mindestens zwei CLS-kompatible Methoden, die in einem Typ deklariert werden, den gleichen Namen und für einen bestimmten Satz von Typinstanziierungen die gleichen Parameter und Rückgabetypen nutzen, dann müssen alle diese Methoden bei diesen Typinstanziierungen semantisch gleichwertig sein. | 48
Eigenschaften | [Eigenschaften](#properties) | Die Methoden, mit denen die Getter- und die Setter-Methode einer Eigenschaft implementiert werden, müssen in den Metadaten mit `SpecialName` markiert werden. | 24
Eigenschaften | [Eigenschaften](#properties) | Die Zugriffsmethoden einer Eigenschaft müssen alle „static“, alle „virtual“ oder alle „instance“ sein. | 26
Eigenschaften | [Eigenschaften](#properties) | Der Typ einer Eigenschaft muss dem Rückgabetyp der Getter-Methode und dem Typ des letzten Arguments der Setter-Methode entsprechen. Die Parametertypen der Eigenschaft müssen den Parametertypen der Getter-Methode und, ausgenommen dem Letzten, allen Parametertypen der Setter-Methode entsprechen. Diese Typen müssen CLS-kompatibel sein und dürfen keine verwalteten Zeiger sein (d.h., sie dürfen nicht als Verweise übergeben werden). | 27
Eigenschaften | [Eigenschaften](#properties) | Eigenschaften müssen einem bestimmten Benennungsschema folgen. Das `SpecialName`-Attribut, auf das in CLS-Regel 24 verwiesen wird, muss in den entsprechenden Namensvergleichen ignoriert werden und Bezeichnerregeln einhalten. Eine Eigenschaft verfügt über eine Getter-Methode, eine Setter-Methode oder beide. | 28
Typkonvertierung | [Typkonvertierung](#type-conversion) | Wenn entweder op_Implicit oder op_Explicit bereitgestellt wird, muss eine alternative Möglichkeit für die Umwandlung bereitgestellt werden. | 39
Typen | [Typen und Typmembersignaturen](#types-and-type-member-signatures) | Geschachtelte Werttypen sind nicht CLS-kompatibel. | 3
Typen | [Typen und Typmembersignaturen](#types-and-type-member-signatures) | Alle Typen, die in einer Signatur erscheinen, müssen CLS-kompatibel sein. Alle Typen, die einen instanziierten generischen Typ erstellen, müssen CLS-kompatibel sein. | 11
Typen | [Typen und Typmembersignaturen](#types-and-type-member-signatures) | Typisierte Verweise sind nicht CLS-kompatibel. | 14
Typen | [Typen und Typmembersignaturen](#types-and-type-member-signatures) | Nicht verwaltete Zeigertypen sind nicht CLS-kompatibel. | 17
Typen | [Typen und Typmembersignaturen](#types-and-type-member-signatures) | CLS-kompatible Klassen, Werttypen und Schnittstellen dürfen nicht die Implementierung nicht CLS-kompatibler Member erfordern. | 20
Typen | [Typen und Typmembersignaturen](#types-and-type-member-signatures) | [System.Object](xref:System.Object) ist CLS-kompatibel. Jede andere CLS-kompatible Klasse muss von einer CLS-kompatiblen Klasse erben. | 23

### <a name="types-and-type-member-signatures"></a>Typen und Typmembersignaturen

Der [System.Object](xref:System.Object)-Typ ist CLS-kompatibel, und er ist der Basistyp aller Objekttypen im .NET Framework-Typsystem. Vererbung erfolgt im .NET Framework entweder implizit (zum Beispiel erbt die [String](xref:System.String)-Klasse implizit von der `Object`-Klasse) oder explizit (zum Beispiel erbt die [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException)-Klasse explizit von der [ArgumentException](xref:System.ArgumentException)-Klasse, die explizit von der [Exception](xref:System.Exception)-Klasse erbt). Damit ein abgeleiteter Typ CLS-kompatibel ist, muss auch der Basistyp CLS-kompatibel sein.

Im folgenden Beispiel wird ein abgeleiteter Typ veranschaulicht, dessen Basistyp nicht CLS-kompatibel ist. Es wird eine `Counter`-Basisklasse definiert, die eine ganze Zahl ohne Vorzeichen mit einer Länge von 32 Bit als Indikator verwendet. Da die Klasse Gegenfunktionalität bereitstellt, indem eine ganze Zahl ohne Vorzeichen umgebrochen wird, wird die Klasse als nicht CLS-kompatibel gekennzeichnet. Daher ist eine abgeleitete Klasse, `NonZeroCounter`, auch nicht CLS-kompatibel.

```csharp
using System;

[assembly: CLSCompliant(true)]

[CLSCompliant(false)]
public class Counter
{
   UInt32 ctr;

   public Counter()
   {
      ctr = 0;
   }

   protected Counter(UInt32 ctr)
   {
      this.ctr = ctr;
   }

   public override string ToString()
   {
      return $"{ctr}). ";
   }

   public UInt32 Value
   {
      get { return ctr; }
   }

   public void Increment()
   {
      ctr += (uint) 1;
   }
}

public class NonZeroCounter : Counter
{
   public NonZeroCounter(int startIndex) : this((uint) startIndex)
   {
   }

   private NonZeroCounter(UInt32 startIndex) : base(startIndex)
   {
   }
}
// Compilation produces a compiler warning like the following:
//    Type3.cs(37,14): warning CS3009: 'NonZeroCounter': base type 'Counter' is not
//            CLS-compliant
//    Type3.cs(7,14): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>

<CLSCompliant(False)> _
Public Class Counter
   Dim ctr As UInt32

   Public Sub New
      ctr = 0
   End Sub

   Protected Sub New(ctr As UInt32)
      ctr = ctr
   End Sub

   Public Overrides Function ToString() As String
      Return $"{ctr}). "
   End Function

   Public ReadOnly Property Value As UInt32
      Get
         Return ctr
      End Get
   End Property

   Public Sub Increment()
      ctr += CType(1, UInt32)
   End Sub
End Class

Public Class NonZeroCounter : Inherits Counter
   Public Sub New(startIndex As Integer)
      MyClass.New(CType(startIndex, UInt32))
   End Sub

   Private Sub New(startIndex As UInt32)
      MyBase.New(CType(startIndex, UInt32))
   End Sub
End Class
' Compilation produces a compiler warning like the following:
'    Type3.vb(34) : warning BC40026: 'NonZeroCounter' is not CLS-compliant
'    because it derives from 'Counter', which is not CLS-compliant.
'
'    Public Class NonZeroCounter : Inherits Counter
'                 ~~~~~~~~~~~~~~
```

Alle in den Membersignaturen angezeigten Typen, einschließlich des Rückgabetyps oder des Eigenschaftentyps einer Methode, müssen CLS-kompatibel sein. Außerdem ist für generische Typen Folgendes erforderlich:

* Alle Typen, die einen instanziierten generischen Typ zusammensetzen, müssen CLS-kompatibel sein.

* Alle als Einschränkungen für generische Parameter verwendeten Typen müssen CLS-kompatibel sein.

Das [allgemeine Typsystem](common-type-system.md) von .NET enthält verschiedene integrierte Datentypen, die direkt von der Common Language Runtime unterstützt werden und insbesondere in den Metadaten einer Assembly codiert werden. Von diesen systeminternen Typen sind die in der folgenden Tabelle aufgeführten Typen CLS-kompatibel.

CLS-kompatibler Typ | BESCHREIBUNG
------------------ | -----------
[Byte](xref:System.Byte) | Ganze 8-Bit-Zahl ohne Vorzeichen
[Int16](xref:System.Int16) | Ganze 16-Bit-Zahl mit Vorzeichen
[Int32](xref:System.Int32) | 32-Bit-Ganzzahl mit Vorzeichen
[Int64](xref:System.Int64) | 64-Bit-Ganzzahl mit Vorzeichen
[Single](xref:System.Single) | Gleitkommawert mit einfacher Genauigkeit
[Double](xref:System.Double) | Gleitkommawert mit doppelter Genauigkeit
[Boolean](xref:System.Boolean) | TRUE- oder FALSE-Werttyp
[Char](xref:System.Char) | UTF-16-codierte Codeeinheit
[Decimal](xref:System.Decimal) | Dezimalzahl ohne Gleitkomma
[IntPtr](xref:System.IntPtr) | Zeiger oder Handle einer Plattform-definierten Größe
[String](xref:System.String) | Sammlung von null, einem oder mehreren Char-Objekten

Die in der folgenden Tabelle aufgeführten systeminternen Typen sind nicht CLS-kompatibel.

Nicht kompatibler Typ | BESCHREIBUNG | CLS-kompatible Alternative
------------------ | ----------- | -------------------------
[SByte](xref:System.SByte) | Ganzzahliger 8-Bit-Datentyp mit Vorzeichen | [Int16](xref:System.Int16)
[UInt16](xref:System.UInt16) | 16-Bit-Ganzzahl ohne Vorzeichen | [Int32](xref:System.Int32)
[UInt32](xref:System.UInt32) | 32-Bit-Ganzzahl ohne Vorzeichen | [Int64](xref:System.Int64)
[UInt64](xref:System.UInt64) | 64-Bit-Ganzzahl ohne Vorzeichen | [Int64](xref:System.Int64) (kann überlaufen), [BigInteger](xref:System.Numerics.BigInteger) oder [Double](xref:System.Double)
[UIntPtr](xref:System.UIntPtr) | Zeiger ohne Vorzeichen oder Handle | [IntPtr](xref:System.IntPtr)

Die .NET Framework-Klassenbibliothek oder jede andere Klassenbibliothek schließen möglicherweise andere nicht CLS-kompatible Typen ein, zum Beispiel:

* Geschachtelte Werttypen Im folgenden C#-Beispiel wird eine Klasse erstellt, die über eine öffentliche Eigenschaft des Typs `int`* mit dem Namen `Value` verfügt. Da `int`* ein geschachtelter Werttyp ist, markiert der Compiler ihn als nicht CLS-kompatibel.

```csharp
using System;

[assembly:CLSCompliant(true)]

public unsafe class TestClass
{
   private int* val;

   public TestClass(int number)
   {
      val = (int*) number;
   }

   public int* Value {
      get { return val; }
   }
}
// The compiler generates the following output when compiling this example:
//        warning CS3003: Type of 'TestClass.Value' is not CLS-compliant
```

* Typisierte Verweise, die spezielle Konstrukte sind, in denen ein Verweis auf ein Objekt und ein Verweis auf einen Typ enthalten sind.

Wenn ein Typ nicht CLS-kompatibel ist, sollten Sie das Attribut [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) mit einem *isCompliant*-Parameter mit einem Wert von `false` anwenden. Weitere Informationen finden Sie im Abschnitt zum [CLSCompliantAttribute-Attribut](#the-clscompliantattribute-attribute).

Im folgenden Beispiel wird das Problem der CLS-Kompatibilität in einer Methodensignatur und in der Instanziierung des generischen Typs veranschaulicht. Dabei wird eine `InvoiceItem`-Klasse mit einer Eigenschaft vom Typ [UInt32](xref:System.UInt32), einer Eigenschaft vom Typ [Nullable(Of UInt32)](xref:System.Nullable%601) und einem Konstruktor mit Parametern vom Typ `UInt32` und `Nullable(Of UInt32)` definiert. Sie erhalten vier Compilerwarnungen, wenn Sie versuchen, das Beispiel zu kompilieren.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<uint> qty;

   public InvoiceItem(uint sku, Nullable<uint> quantity)
   {
      itemId = sku;
      qty = quantity;
   }

   public Nullable<uint> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public uint InvoiceId
   {
      get { return invId; }
      set { invId = value; }
   }
}
// The attempt to compile the example displays the following output:
//    Type1.cs(13,23): warning CS3001: Argument type 'uint' is not CLS-compliant
//    Type1.cs(13,33): warning CS3001: Argument type 'uint?' is not CLS-compliant
//    Type1.cs(19,26): warning CS3003: Type of 'InvoiceItem.Quantity' is not CLS-compliant
//    Type1.cs(25,16): warning CS3003: Type of 'InvoiceItem.InvoiceId' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of UInteger)

   Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
      itemId = sku
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of UInteger)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As UInteger
      Get
         Return invId
      End Get
      Set
         invId = value
      End Set
   End Property
End Class
' The attempt to compile the example displays output similar to the following:
'    Type1.vb(13) : warning BC40028: Type of parameter 'sku' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                      ~~~
'    Type1.vb(13) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                                                               ~~~~~~~~
'    Type1.vb(18) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Property Quantity As Nullable(Of UInteger)
'                                               ~~~~~~~~
'    Type1.vb(27) : warning BC40027: Return type of function 'InvoiceId' is not CLS-compliant.
'
'       Public Property InvoiceId As UInteger
```

Um die Compilerwarnungen auszuschließen, ersetzen Sie die nicht CLS-kompatiblen Typen in der öffentlichen `InvoiceItem`-Schnittstelle durch kompatible Typen:

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<int> qty;

   public InvoiceItem(int sku, Nullable<int> quantity)
   {
      if (sku <= 0)
         throw new ArgumentOutOfRangeException("The item number is zero or negative.");
      itemId = (uint) sku;

      qty = quantity;
   }

   public Nullable<int> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public int InvoiceId
   {
      get { return (int) invId; }
      set {
         if (value <= 0)
            throw new ArgumentOutOfRangeException("The invoice number is zero or negative.");
         invId = (uint) value; }
   }
}
```

```vb
Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of Integer)

   Public Sub New(sku As Integer, quantity As Nullable(Of Integer))
      If sku <= 0 Then
         Throw New ArgumentOutOfRangeException("The item number is zero or negative.")
      End If
      itemId = CUInt(sku)
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of Integer)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As Integer
      Get
         Return CInt(invId)
      End Get
      Set
         invId = CUInt(value)
      End Set
   End Property
End Class
```

Zusätzlich zu bestimmten aufgeführten Typen sind einige Typenkategorien ebenfalls nicht CLS-kompatibel. Diese schließen nicht verwaltete Zeigertypen und Funktionszeigertypen ein. Im folgenden Beispiel wird eine Compilerwarnung erzeugt, da ein Zeiger auf eine ganze Zahl verwendet wird, um ein Array ganzer Zahlen zu erstellen.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

Für CLS-kompatible abstrakte Klassen (also Klassen, die in C# als `abstract` markiert sind), müssen alle Member der Klasse auch CLS-kompatibel sein.

### <a name="naming-conventions"></a>Namenskonventionen

Da bei einigen Programmiersprachen die Groß- und Kleinschreibung nicht beachtet werden muss, müssen Bezeichner (wie die Namen von Namespaces, Typen und Membern) durch mehr als die Groß-/Kleinschreibung unterschieden werden. Zwei Bezeichner gelten als äquivalent, wenn ihre kleingeschriebenen Zuordnungen identisch sind. Im folgenden C#-Beispiel werden zwei öffentliche Klassen definiert: `Person` und `person`. Da sie sich nur durch die Groß-/Kleinschreibung unterscheiden, markiert der C#-Compiler sie als nicht CLS-kompatibel.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person : person
{

}

public class person
{

}
// Compilation produces a compiler warning like the following:
//    Naming1.cs(11,14): warning CS3005: Identifier 'person' differing
//                       only in case is not CLS-compliant
//    Naming1.cs(6,14): (Location of symbol related to previous warning)
```

Programmiersprachenbezeichner, wie die Namen von Namespaces, Typen und Membern, müssen dem [Unicode-Standard 3.0, Fachbericht 15, Anhang 7](https://www.unicode.org/reports/tr15/tr15-18.html) entsprechen. Dies bedeutet Folgendes:

* Das erste Zeichen eines Bezeichners kann jeder Unicode-Großbuchstabe, Kleinbuchstabe, großer Anfangsbuchstabe, Modifiziererbuchstabe, anderer Buchstabe oder jede Buchstabenzahl sein. Informationen zu Unicode-Zeichenkategorien finden Sie unter der [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory)-Enumeration.

* Nachfolgende Zeichen können aus einer der Kategorien wie das erste Zeichen stammen, und sie können auch Markierungen ohne Zwischenraum, Sperrmarkierungen, Dezimalwerte, Connectorinterpunktionen und Formatierungscodes umfassen.

Bevor Sie Bezeichner vergleichen, sollten Sie Formatierungscodes herausfiltern und die Bezeichner in die Unicode-Normalisierungsform C konvertieren, da ein einzelnes Zeichen durch mehrere UTF-16-codierte Codeeinheiten dargestellt werden kann. Zeichensequenzen, die die gleichen Codeeinheiten in der Unicode-Normalisierungsform C erzeugen, sind nicht CLS-kompatibel. Im folgenden Beispiel werden zwei Eigenschaften definiert: eine namens `Å`, die aus dem ÅNGSTRÖM-ZEICHEN (U+212B) besteht, und eine zweite namens `Å`, die aus dem Zeichen LATEINISCHER GROSSBUCHSTABE A MIT RING OBEN (U+00C5) besteht. Der C#-Compiler kennzeichnet den Quellcode als nicht CLS-kompatibel.

```csharp
public class Size
{
   private double a1;
   private double a2;

   public double Å
   {
       get { return a1; }
       set { a1 = value; }
   }

   public double Å
   {
       get { return a2; }
       set { a2 = value; }
   }
}
// Compilation produces a compiler warning like the following:
//    Naming2a.cs(16,18): warning CS3005: Identifier 'Size.Å' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(10,18): (Location of symbol related to previous warning)
//    Naming2a.cs(18,8): warning CS3005: Identifier 'Size.Å.get' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(12,8): (Location of symbol related to previous warning)
//    Naming2a.cs(19,8): warning CS3005: Identifier 'Size.Å.set' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(13,8): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>
Public Class Size
   Private a1 As Double
   Private a2 As Double

   Public Property Å As Double
       Get
          Return a1
       End Get
       Set
          a1 = value
       End Set
   End Property

   Public Property Å As Double
       Get
          Return a2
       End Get
       Set
          a2 = value
       End Set
   End Property
End Class
' Compilation produces a compiler warning like the following:
'    Naming1.vb(9) : error BC30269: 'Public Property Å As Double' has multiple definitions
'     with identical signatures.
'
'       Public Property Å As Double
'                       ~
```

Membernamen innerhalb eines bestimmten Bereichs (wie den Namespaces innerhalb einer Assembly, den Typen in einem Namespace oder den Membern innerhalb eines Typs) müssen eindeutig sein, abgesehen von Namen, die durch Überladen aufgelöst werden. Diese Anforderung ist zwingender als die des allgemeinen Typsystems, bei dem mehrere Member innerhalb eines Bereichs über identische Namen verfügen dürfen, solange es unterschiedliche Arten von Membern sind (zum Beispiel eine Methode und ein Feld). Insbesondere für Typmember:

* Felder und geschachtelte Typen werden allein nach Namen unterschieden.

* Methoden, Eigenschaften und Ereignisse mit demselben Namen müssen sich durch mehr als nur den Rückgabetyp unterscheiden.

Im folgenden Beispiel wird die Anforderung veranschaulicht, dass Membernamen innerhalb des Bereichs eindeutig sein müssen. Es wird eine Klasse namens `Converter` definiert, die vier Member namens `Conversion` umfasst. Drei Methoden und eine Eigenschaft. Die Methode, die einen Parameter `Int64` umfasst, hat einen eindeutigen Namen, doch die beiden Methoden mit einem `Int32`-Parameter sind nicht eindeutig, da der Rückgabewert nicht als ein Teil der Signatur eines Members gültig ist. Die `Conversion`- Eigenschaft verstößt auch gegen diese Anforderung, da Eigenschaften nicht den gleichen Namen wie überladene Methoden besitzen dürfen.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Converter
{
   public double Conversion(int number)
   {
      return (double) number;
   }

   public float Conversion(int number)
   {
      return (float) number;
   }

   public double Conversion(long number)
   {
      return (double) number;
   }

   public bool Conversion
   {
      get { return true; }
   }
}
// Compilation produces a compiler error like the following:
//    Naming3.cs(13,17): error CS0111: Type 'Converter' already defines a member called
//            'Conversion' with the same parameter types
//    Naming3.cs(8,18): (Location of symbol related to previous error)
//    Naming3.cs(23,16): error CS0102: The type 'Converter' already contains a definition for
//            'Conversion'
//    Naming3.cs(8,18): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Converter
   Public Function Conversion(number As Integer) As Double
      Return CDbl(number)
   End Function

   Public Function Conversion(number As Integer) As Single
      Return CSng(number)
   End Function

   Public Function Conversion(number As Long) As Double
      Return CDbl(number)
   End Function

   Public ReadOnly Property Conversion As Boolean
      Get
         Return True
      End Get
   End Property
End Class
' Compilation produces a compiler error like the following:
'    Naming3.vb(8) : error BC30301: 'Public Function Conversion(number As Integer) As Double'
'                    and 'Public Function Conversion(number As Integer) As Single' cannot
'                    overload each other because they differ only by return types.
'
'       Public Function Conversion(number As Integer) As Double
'                       ~~~~~~~~~~
'    Naming3.vb(20) : error BC30260: 'Conversion' is already declared as 'Public Function
'                     Conversion(number As Integer) As Single' in this class.
'
'       Public ReadOnly Property Conversion As Boolean
'                                ~~~~~~~~~~
```

Einzelne Sprachen enthalten eindeutige Schlüsselwörter, sodass Sprachen für die Common Language Runtime einen Mechanismus zum Verweisen auf Bezeichner (z. B. Typnamen) bereitstellen müssen, die mit den Schlüsselwörtern übereinstimmen. Beispielsweise ist `case` ein Schlüsselwort in C# und Visual Basic. Im folgenden Visual Basic-Beispiel wird eine Klasse namens `case` eindeutig vom `case`-Schlüsselwort unterschieden, indem öffnende und schließende geschweifte Klammern verwendet werden. Andernfalls würde in dem Beispiel die folgende Fehlermeldung erzeugt: "Das Schlüsselwort ist kein gültiger Bezeichner", und der Code könnte nicht kompiliert werden.

```vb
Public Class [case]
   Private _id As Guid
   Private name As String

   Public Sub New(name As String)
      _id = Guid.NewGuid()
      Me.name = name
   End Sub

   Public ReadOnly Property ClientName As String
      Get
         Return name
      End Get
   End Property
End Class
```

Im folgenden C#-Beispiel kann die `case`-Klasse instanziiert werden, indem das @-Symbol verwendet wird, um den Bezeichner eindeutig vom Schlüsselwort zu unterscheiden. Ohne dieses Zeichen würde der C#-Compiler zwei Fehlermeldungen anzeigen:"Typ erwartet" und "Ungültiger Ausdruck 'case'".

```csharp
using System;

public class Example
{
   public static void Main()
   {
      @case c = new @case("John");
      Console.WriteLine(c.ClientName);
   }
}
```

### <a name="type-conversion"></a>Typkonvertierung

In der Common Language Specification werden zwei Konvertierungsoperatoren definiert:

* `op_Implicit`, das für Erweiterungskonvertierungen verwendet wird, die zu keinem Datenverlust oder Genauigkeitsverlust führen. Zum Beispiel umfasst die [Decimal](xref:System.Decimal)-Struktur einen überladenen `op_Implicit`-Operator, um Werte integraler Typen und [Char](xref:System.Char)-Werte in `Decimal`-Werte zu konvertieren.

* `op_Explicit`, der für einschränkende Konvertierungen verwendet wird, die zu Größenverlusten (ein Wert wird in einen Wert konvertiert, der über einen kleineren Bereich verfügt) bzw. zu Verlusten der Genauigkeit führen können. Zum Beispiel umfasst die `Decimal`-Struktur einen überladenen `op_Explicit`-Operator, um den [Double](xref:System.Double)-Wert und den [Single](xref:System.Single)-Wert in `Decimal` zu konvertieren und die `Decimal`-Werte in integrale Werte, `Double`, `Single` und `Char` zu konvertieren.

Allerdings wird Operatorüberladung oder die Definition benutzerdefinierter Operatoren nicht von allen Sprachen unterstützt. Wenn Sie diese Konvertierungsoperatoren implementieren, sollten Sie eine alternative Methode zum Ausführen der Konvertierung bereitstellen. Es wird empfohlen, `From`Xxx- und `To`Xxx-Methoden bereitzustellen.

Im folgenden Beispiel werden CLS-kompatible implizite und explizite Konvertierungen definiert. Es wird eine `UDouble`-Klasse erstellt, die eine Gleitkommazahl mit doppelter Genauigkeit und Vorzeichen darstellt. Implizite Konvertierungen aus `UDouble` in `Double` und explizite Konvertierungen aus `UDouble` in `Single`, aus `Double` in `UDouble` und aus `Single` in `UDouble` werden bereitgestellt. Es wird auch eine `ToDouble`-Methode als Alternative zum Operator für implizite Konvertierung definiert, und die `ToSingle`, `FromDouble`-Methode sowie die `FromSingle`-Methode werden als Alternativen zu den Operatoren der expliziten Konvertierung definiert.

```csharp
using System;

public struct UDouble
{
   private double number;

   public UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public static readonly UDouble MinValue = (UDouble) 0.0;
   public static readonly UDouble MaxValue = (UDouble) Double.MaxValue;

   public static explicit operator Double(UDouble value)
   {
      return value.number;
   }

   public static implicit operator Single(UDouble value)
   {
      if (value.number > (double) Single.MaxValue)
         throw new InvalidCastException("A UDouble value is out of range of the Single type.");

      return (float) value.number;
   }

   public static explicit operator UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static implicit operator UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static Double ToDouble(UDouble value)
   {
      return (Double) value;
   }

   public static float ToSingle(UDouble value)
   {
      return (float) value;
   }

   public static UDouble FromDouble(double value)
   {
      return new UDouble(value);
   }

   public static UDouble FromSingle(float value)
   {
      return new UDouble(value);
   }
}
```

```vb
Public Structure UDouble
   Private number As Double

   Public Sub New(value As Double)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Sub New(value As Single)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Shared ReadOnly MinValue As UDouble = CType(0.0, UDouble)
   Public Shared ReadOnly MaxValue As UDouble = Double.MaxValue

   Public Shared Widening Operator CType(value As UDouble) As Double
      Return value.number
   End Operator

   Public Shared Narrowing Operator CType(value As UDouble) As Single
      If value.number > CDbl(Single.MaxValue) Then
         Throw New InvalidCastException("A UDouble value is out of range of the Single type.")
      End If
      Return CSng(value.number)
   End Operator

   Public Shared Narrowing Operator CType(value As Double) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Narrowing Operator CType(value As Single) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Function ToDouble(value As UDouble) As Double
      Return CType(value, Double)
   End Function

   Public Shared Function ToSingle(value As UDouble) As Single
      Return CType(value, Single)
   End Function

   Public Shared Function FromDouble(value As Double) As UDouble
      Return New UDouble(value)
   End Function

   Public Shared Function FromSingle(value As Single) As UDouble
      Return New UDouble(value)
   End Function
End Structure
```

### <a name="arrays"></a>Arrays

CLS-kompatible Arrays sind mit den folgenden Regeln kompatibel:

* Die unteren Begrenzungen aller Dimensionen eines Arrays müssen gleich 0 sein. Im folgenden Beispiel wird ein Array mit einer nicht CLS-kompatiblen Untergrenze von eins erstellt. Beachten Sie, dass der Compiler ungeachtet des Vorhandenseins des [CLSCompliantAttribute](xref:System.CLSCompliantAttribute)-Attributs nicht erkennt, dass das von der `Numbers.GetTenPrimes`-Methode zurückgegebene Array nicht CLS-kompatibel ist.

  ```csharp
  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static Array GetTenPrimes()
    {
        Array arr = Array.CreateInstance(typeof(Int32), new int[] {10}, new int[] {1});
        arr.SetValue(1, 1);
        arr.SetValue(2, 2);
        arr.SetValue(3, 3);
        arr.SetValue(5, 4);
        arr.SetValue(7, 5);
        arr.SetValue(11, 6);
        arr.SetValue(13, 7);
        arr.SetValue(17, 8);
        arr.SetValue(19, 9);
        arr.SetValue(23, 10);

        return arr;
    }
  }
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As Array
        Dim arr As Array = Array.CreateInstance(GetType(Int32), {10}, {1})
        arr.SetValue(1, 1)
        arr.SetValue(2, 2)
        arr.SetValue(3, 3)
        arr.SetValue(5, 4)
        arr.SetValue(7, 5)
        arr.SetValue(11, 6)
        arr.SetValue(13, 7)
        arr.SetValue(17, 8)
        arr.SetValue(19, 9)
        arr.SetValue(23, 10)
        Return arr
     End Function
  End Class
  ```

* Alle Arrayelemente müssen aus CLS-kompatiblen Typen bestehen. Im folgenden Beispiel werden zwei Methoden, die nicht CLS-kompatible Arrays zurückgeben, definiert. Die erste Methode gibt ein Array von [UInt32](xref:System.UInt32)-Werten zurück. Die zweite Methode gibt ein [Object](xref:System.Object)-Array zurück, das [Int32](xref:System.Int32)- und `UInt32`-Werte umfasst. Obwohl der Compiler das erste Array aufgrund des `UInt32`-Typs als nicht kompatibel identifiziert, wird nicht erkannt, dass das zweite Array nicht CLS-kompatible Elemente umfasst.

  ```csharp
  using System;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static UInt32[] GetTenPrimes()
    {
        uint[] arr = { 1u, 2u, 3u, 5u, 7u, 11u, 13u, 17u, 19u };
        return arr;
    }

    public static Object[] GetFivePrimes()
    {
        Object[] arr = { 1, 2, 3, 5u, 7u };
        return arr;
    }
  }
  // Compilation produces a compiler warning like the following:
  //    Array2.cs(8,27): warning CS3002: Return type of 'Numbers.GetTenPrimes()' is not
  //            CLS-compliant
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As UInt32()
        Return { 1ui, 2ui, 3ui, 5ui, 7ui, 11ui, 13ui, 17ui, 19ui }
     End Function
     Public Shared Function GetFivePrimes() As Object()
        Dim arr() As Object = { 1, 2, 3, 5ui, 7ui }
        Return arr
     End Function
  End Class
  ' Compilation produces a compiler warning like the following:
  '    warning BC40027: Return type of function 'GetTenPrimes' is not CLS-compliant.
  ```

* Die Überladungsauflösung für Methoden mit Arrayparametern basiert sowohl auf der Tatsache, dass es Arrays sind, als auch auf dem Elementtyp. Aus diesem Grund ist die folgende Definition einer überladenen `GetSquares`-Methode CLS-kompatibel.

  ```csharp
  using System;
  using System.Numerics;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static byte[] GetSquares(byte[] numbers)
    {
        byte[] numbersOut = new byte[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++) {
            int square = ((int) numbers[ctr]) * ((int) numbers[ctr]);
            if (square <= Byte.MaxValue)
                numbersOut[ctr] = (byte) square;
            // If there's an overflow, assign MaxValue to the corresponding
            // element.
            else
                numbersOut[ctr] = Byte.MaxValue;

        }
        return numbersOut;
    }

    public static BigInteger[] GetSquares(BigInteger[] numbers)
  {
        BigInteger[] numbersOut = new BigInteger[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++)
            numbersOut[ctr] = numbers[ctr] * numbers[ctr];

       return numbersOut;
    }
  }
  ```

  ```vb
  Imports System.Numerics

  <Assembly: CLSCompliant(True)>

  Public Module Numbers
     Public Function GetSquares(numbers As Byte()) As Byte()
        Dim numbersOut(numbers.Length - 1) As Byte
        For ctr As Integer = 0 To numbers.Length - 1
           Dim square As Integer = (CInt(numbers(ctr)) * CInt(numbers(ctr)))
           If square <= Byte.MaxValue Then
              numbersOut(ctr) = CByte(square)
           ' If there's an overflow, assign MaxValue to the corresponding
           ' element.
           Else
              numbersOut(ctr) = Byte.MaxValue
           End If
        Next
        Return numbersOut
     End Function

     Public Function GetSquares(numbers As BigInteger()) As BigInteger()
         Dim numbersOut(numbers.Length - 1) As BigInteger
         For ctr As Integer = 0 To numbers.Length - 1
            numbersOut(ctr) = numbers(ctr) * numbers(ctr)
         Next
         Return numbersOut
     End Function
  End Module
  ```

### <a name="interfaces"></a>Schnittstellen

CLS-kompatible Schnittstellen können Eigenschaften, Ereignisse und virtuelle Methoden (Methoden ohne Implementierung) definieren. Eine CLS-kompatible Schnittstelle kann keine der folgenden Aspekte aufweisen:

* Statische Methoden oder statische Felder Der C#-Compiler generiert Compilerfehler, wenn Sie einen statischen Member in einer Schnittstelle definieren.

* Felder Die C#-Compiler generiert Compilerfehler, wenn Sie ein Feld in einer Schnittstelle definieren.

* Methoden, die nicht CLS-kompatibel sind. Zum Beispiel umfasst die folgende Schnittstellendefinition eine Methode, `INumber.GetUnsigned`, die als nicht CLS-kompatibel gekennzeichnet wird. In diesem Beispiel wird eine Compilerwarnung generiert.

  ```csharp
  using System;

  [assembly:CLSCompliant(true)]

  public interface INumber
  {
      int Length();
      [CLSCompliant(false)] ulong GetUnsigned();
  }
  // Attempting to compile the example displays output like the following:
  //    Interface2.cs(8,32): warning CS3010: 'INumber.GetUnsigned()': CLS-compliant interfaces
  //            must have only CLS-compliant members
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Interface INumber
    Function Length As Integer
      <CLSCompliant(False)> Function GetUnsigned As ULong
    End Interface
    ' Attempting to compile the example displays output like the following:
    '    Interface2.vb(9) : warning BC40033: Non CLS-compliant 'function' is not allowed in a
    '    CLS-compliant interface.
    '
    '       <CLSCompliant(False)> Function GetUnsigned As ULong
    '                                      ~~~~~~~~~~~
  ```

  Aufgrund dieser Regel, ist es nicht erforderlich, dass CLS-kompatible Typen nicht CLS-kompatible Member implementieren. Wenn ein CLS-kompatibles Framework eine Klasse verfügbar macht, die eine nicht CLS- kompatible Schnittstelle implementiert, sollte sie konkrete Implementierungen aller nicht-CLS-kompatiblen Member angeben.

CLS-kompatible Sprachcompiler müssen einer Klasse auch ermöglichen, separate Implementierungen von Membern bereitzustellen, die in mehreren Schnittstellen über den gleichen Namen und dieselbe Signatur verfügen. C# unterstützt explizite Schnittstellenimplementierungen, um unterschiedliche Implementierungen identisch benannter Methoden bereitzustellen. Im folgenden Beispiel wird dieses Szenario veranschaulicht, indem eine `Temperature`-Klasse definiert wird, die die `ICelsius`-Schnittstelle und die `IFahrenheit`-Schnittstelle als explizite Schnittstellenimplementierungen implementiert.

```csharp
using System;

[assembly: CLSCompliant(true)]

public interface IFahrenheit
{
   decimal GetTemperature();
}

public interface ICelsius
{
   decimal GetTemperature();
}

public class Temperature : ICelsius, IFahrenheit
{
   private decimal _value;

   public Temperature(decimal value)
   {
      // We assume that this is the Celsius value.
      _value = value;
   }

   decimal IFahrenheit.GetTemperature()
   {
      return _value * 9 / 5 + 32;
   }

   decimal ICelsius.GetTemperature()
   {
      return _value;
   }
}
public class Example
{
   public static void Main()
   {
      Temperature temp = new Temperature(100.0m);
      ICelsius cTemp = temp;
      IFahrenheit fTemp = temp;
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        cTemp.GetTemperature());
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        fTemp.GetTemperature());
   }
}
// The example displays the following output:
//       Temperature in Celsius: 100.0 degrees
//       Temperature in Fahrenheit: 212.0 degrees
```

```vb
Assembly: CLSCompliant(True)>

Public Interface IFahrenheit
   Function GetTemperature() As Decimal
End Interface

Public Interface ICelsius
   Function GetTemperature() As Decimal
End Interface

Public Class Temperature : Implements ICelsius, IFahrenheit
   Private _value As Decimal

   Public Sub New(value As Decimal)
      ' We assume that this is the Celsius value.
      _value = value
   End Sub

   Public Function GetFahrenheit() As Decimal _
          Implements IFahrenheit.GetTemperature
      Return _value * 9 / 5 + 32
   End Function

   Public Function GetCelsius() As Decimal _
          Implements ICelsius.GetTemperature
      Return _value
   End Function
End Class

Module Example
   Public Sub Main()
      Dim temp As New Temperature(100.0d)
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        temp.GetCelsius())
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        temp.GetFahrenheit())
   End Sub
End Module
' The example displays the following output:
'       Temperature in Celsius: 100.0 degrees
'       Temperature in Fahrenheit: 212.0 degrees
```

### <a name="enumerations"></a>Enumerationen

Bei CLS-kompatiblen Enumerationen müssen die folgenden Regeln beachtet werden:

* Der zugrunde liegende Typ der Enumeration muss ein systeminterner CLS-kompatibler Ganzzahltyp sein ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32) oder [Int64](xref:System.Int64)). Im folgenden Code wird beispielsweise versucht, eine Enumeration zu definieren, deren zugrunde liegender Typ [UInt32](xref:System.UInt32) ist. Eine Compilerwarnung wird generiert.

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public enum Size : uint {
        Unspecified = 0,
        XSmall = 1,
        Small = 2,
        Medium = 3,
        Large = 4,
        XLarge = 5
    };

    public class Clothing
    {
        public string Name;
        public string Type;
        public string Size;
    }
    // The attempt to compile the example displays a compiler warning like the following:
    //    Enum3.cs(6,13): warning CS3009: 'Size': base type 'uint' is not CLS-compliant
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Enum Size As UInt32
       Unspecified = 0
       XSmall = 1
       Small = 2
       Medium = 3
       Large = 4
       XLarge = 5
    End Enum

    Public Class Clothing
       Public Name As String
       Public Type As String
       Public Size As Size
    End Class
    ' The attempt to compile the example displays a compiler warning like the following:
    '    Enum3.vb(6) : warning BC40032: Underlying type 'UInt32' of Enum is not CLS-compliant.
    '
    '    Public Enum Size As UInt32
    '                ~~~~
    ```

* Ein Enumerationstyp muss über ein Feld namens `Value__` mit einer einzelnen Instanz verfügen, das mit dem `FieldAttributes.RTSpecialName`-Attribut markiert ist. Damit können Sie den Feldwert implizit verweisen.

* Eine Enumeration umfasst literale statische Felder, deren Typen vom gleichen Typ wie die Enumeration selbst sein müssen. Wenn Sie zum Beispiel eine `State`-Enumeration mit den Werten aus `State.On` und `State.Off` definieren, sind `State.On` und `State.Off` literale statische Felder, deren Typ `State` ist.

* Es gibt zwei Arten von Enumerationen.

  * Eine Enumeration, die einen Satz wechselseitig exklusiver, benannter ganzzahliger Werte darstellt. Dieser Typ der Enumeration wird durch das Fehlen des benutzerdefinierten [System.FlagsAttribute](xref:System.FlagsAttribute)-Attributs angegeben.

  * Eine Enumeration, die einen Satz von Bitflags darstellt, die zum Generieren eines unbenannten Werts kombiniert werden können. Dieser Typ der Enumeration wird durch das Vorhandensein des benutzerdefinierten [System.FlagsAttribute](xref:System.FlagsAttribute)-Attributs angegeben.

Weitere Informationen finden Sie in der Dokumentation zur [Enum](xref:System.Enum)-Struktur.

* Der Wert einer Enumeration wird nicht auf den Bereich der angegebenen Werte beschränkt. Das heißt, der Wertebereich einer Enumeration ist der Bereich des zugrunde liegenden Werts. Sie können die `Enum.IsDefined`-Methode verwenden, um zu bestimmen, ob ein angegebener Wert ein Member einer Enumeration ist.

### <a name="type-members-in-general"></a>Typmember im Allgemeinen

Die Common Language Specification erfordert, dass auf alle Felder und Methoden als Member einer bestimmten Klasse zugegriffen werden. Daher sind globale statische Felder und Methoden (das heißt, statische Felder oder Methoden, die unabhängig von einem Typ definiert werden), nicht CLS-kompatibel. Wenn Sie versuchen, ein globales Feld oder eine Methode im Quellcode einzuschließen, wird vom C#-Compiler ein Compilerfehler generiert.

Die Common Language Specification unterstützt nur die verwaltete Standardaufrufkonvention. Sie unterstützt keine nicht verwalteten Aufrufkonventionen und keine Methoden mit variablen Argumentlisten, die mit dem `varargs`-Schlüsselwort gekennzeichnet werden. Verwenden Sie für Variablenargumentlisten, die mit der verwalteten Standardaufrufkonvention kompatibel sind, das [ParamArrayAttribute](xref:System.ParamArrayAttribute)-Attribut oder die Implementierung der jeweiligen Sprache, wie z.B. das `params`-Schlüsselwort in C# und das `ParamArray`-Schlüsselwort in Visual Basic.

### <a name="member-accessibility"></a>Memberzugriff

Das Überschreiben eines geerbten Members kann den Zugriff auf diesen Member nicht ändern. Beispielsweise kann eine öffentliche Methode in einer Basisklasse nicht von einer privaten Methode in einer abgeleiteten Klasse überschrieben werden. Es gibt allerdings eine Ausnahme: einen `protected internal`-Member (in C#) oder einen `Protected Friend`-Member (in Visual Basic) in einer Assembly, die von einem Typ in einer anderen Assembly überschrieben wird.  In diesem Fall ist der Zugriff auf die Überschreibung `Protected`.

Im folgenden Beispiel wird der Fehler veranschaulicht, der generiert wird, wenn das [CLSCompliantAttribute](xref:System.CLSCompliantAttribute)-Attribut auf `true` festgelegt wird und `Person`, eine von `Animal` abgeleitete Klasse, versucht, den Zugriff auf die `Species`-Eigenschaft von öffentlich in privat zu ändern. Das Beispiel wird erfolgreich kompiliert, wenn der Zugriff auf öffentlich geändert wird.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Animal
{
   private string _species;

   public Animal(string species)
   {
      _species = species;
   }

   public virtual string Species
   {
      get { return _species; }
   }

   public override string ToString()
   {
      return _species;
   }
}

public class Human : Animal
{
   private string _name;

   public Human(string name) : base("Homo Sapiens")
   {
      _name = name;
   }

   public string Name
   {
      get { return _name; }
   }

   private override string Species
   {
      get { return base.Species; }
   }

   public override string ToString()
   {
      return _name;
   }
}

public class Example
{
   public static void Main()
   {
      Human p = new Human("John");
      Console.WriteLine(p.Species);
      Console.WriteLine(p.ToString());
   }
}
// The example displays the following output:
//    error CS0621: 'Human.Species': virtual or abstract members cannot be private
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Animal
   Private _species As String

   Public Sub New(species As String)
      _species = species
   End Sub

   Public Overridable ReadOnly Property Species As String
      Get
         Return _species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _species
   End Function
End Class

Public Class Human : Inherits Animal
   Private _name As String

   Public Sub New(name As String)
      MyBase.New("Homo Sapiens")
      _name = name
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return _name
      End Get
   End Property

   Private Overrides ReadOnly Property Species As String
      Get
         Return MyBase.Species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _name
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim p As New Human("John")
      Console.WriteLine(p.Species)
      Console.WriteLine(p.ToString())
   End Sub
End Module
' The example displays the following output:
'     'Private Overrides ReadOnly Property Species As String' cannot override
'     'Public Overridable ReadOnly Property Species As String' because
'      they have different access levels.
'
'         Private Overrides ReadOnly Property Species As String
```

Der Zugriff auf Typen in der Signatur eines Members muss möglich sein, wenn auf den Member zugegriffen werden kann. Das bedeutet zum Beispiel, dass ein öffentlicher Member keinen Parameter enthalten kann, dessen Typ privat, geschützt oder intern ist. Im folgenden Beispiel wird der Compilerfehler veranschaulicht, der entsteht, wenn ein `StringWrapper`-Klassenkonstruktor einen internen `StringOperationType`-Enumerationswert verfügbar macht, der bestimmt, wie ein Zeichenfolgenwert umschlossen werden soll.

```csharp
using System;
using System.Text;

public class StringWrapper
{
   string internalString;
   StringBuilder internalSB = null;
   bool useSB = false;

   public StringWrapper(StringOperationType type)
   {
      if (type == StringOperationType.Normal) {
         useSB = false;
      }
      else {
         useSB = true;
         internalSB = new StringBuilder();
      }
   }

   // The remaining source code...
}

internal enum StringOperationType { Normal, Dynamic }
// The attempt to compile the example displays the following output:
//    error CS0051: Inconsistent accessibility: parameter type
//            'StringOperationType' is less accessible than method
//            'StringWrapper.StringWrapper(StringOperationType)'
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class StringWrapper

   Dim internalString As String
   Dim internalSB As StringBuilder = Nothing
   Dim useSB As Boolean = False

   Public Sub New(type As StringOperationType)
      If type = StringOperationType.Normal Then
         useSB = False
      Else
         internalSB = New StringBuilder()
         useSB = True
      End If
   End Sub

   ' The remaining source code...
End Class

Friend Enum StringOperationType As Integer
   Normal = 0
   Dynamic = 1
End Enum
' The attempt to compile the example displays the following output:
'    error BC30909: 'type' cannot expose type 'StringOperationType'
'     outside the project through class 'StringWrapper'.
'
'       Public Sub New(type As StringOperationType)
'                              ~~~~~~~~~~~~~~~~~~~
```

### <a name="generic-types-and-members"></a>Generische Typen und Member

Geschachtelte Typen weisen immer mindestens so viele generische Parameter auf wie der einschließende Typ. Diese entsprechen der Position nach den generischen Parametern im einschließenden Typ. Der generische Typ kann auch neue generische Parameter enthalten.

Die Beziehung zwischen generischen Typparametern eines enthaltenden Typs und den geschachtelten Typen wird möglicherweise von der Syntax der einzelnen Sprachen verdeckt. Im folgenden Beispiel enthält ein generischer Typ `Outer<T>` zwei geschachtelte Klassen: `Inner1A` und `Inner1B<U>`. Die Aufrufe der `ToString`-Methode, die jede Klasse von `Object.ToString` erbt, zeigen, dass jede geschachtelte Klasse die Typparameter der enthaltenden Klasse umfasst.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Outer<T>
{
   T value;

   public Outer(T value)
   {
      this.value = value;
   }

   public class Inner1A : Outer<T>
   {
      public Inner1A(T value) : base(value)
      {  }
   }

   public class Inner1B<U> : Outer<T>
   {
      U value2;

      public Inner1B(T value1, U value2) : base(value1)
      {
         this.value2 = value2;
      }
   }
}

public class Example
{
   public static void Main()
   {
      var inst1 = new Outer<String>("This");
      Console.WriteLine(inst1);

      var inst2 = new Outer<String>.Inner1A("Another");
      Console.WriteLine(inst2);

      var inst3 = new Outer<String>.Inner1B<int>("That", 2);
      Console.WriteLine(inst3);
   }
}
// The example displays the following output:
//       Outer`1[System.String]
//       Outer`1+Inner1A[System.String]
//       Outer`1+Inner1B`1[System.String,System.Int32]
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Outer(Of T)
   Dim value As T

   Public Sub New(value As T)
      Me.value = value
   End Sub

   Public Class Inner1A : Inherits Outer(Of T)
      Public Sub New(value As T)
         MyBase.New(value)
      End Sub
   End Class

   Public Class Inner1B(Of U) : Inherits Outer(Of T)
      Dim value2 As U

      Public Sub New(value1 As T, value2 As U)
         MyBase.New(value1)
         Me.value2 = value2
      End Sub
   End Class
End Class

Public Module Example
   Public Sub Main()
      Dim inst1 As New Outer(Of String)("This")
      Console.WriteLine(inst1)

      Dim inst2 As New Outer(Of String).Inner1A("Another")
      Console.WriteLine(inst2)

      Dim inst3 As New Outer(Of String).Inner1B(Of Integer)("That", 2)
      Console.WriteLine(inst3)
   End Sub
End Module
' The example displays the following output:
'       Outer`1[System.String]
'       Outer`1+Inner1A[System.String]
'       Outer`1+Inner1B`1[System.String,System.Int32]
```

Der Name eines generischen Typs wird in der Form *name*'*n* codiert, wobei *name* der Typname, *`* ein Zeichenliteral und *n* die Anzahl von Parametern ist, die für den Typ deklariert sind, oder, bei geschachtelten generischen Typen, die Anzahl neu eingeführter Typparameter. Diese Codierung von Namen des generischen Typs ist hauptsächlich für Entwickler relevant, die Reflexion verwenden, um auf CLS-kompatible generische Typen in einer Bibliothek zuzugreifen.

Wenn Einschränkungen auf einen generischen Typ angewendet werden, müssen alle als Einschränkungen verwendeten Typen auch CLS-kompatibel sein. Im folgenden Beispiel wird eine Klasse namens `BaseClass` definiert, die nicht CLS-kompatibel ist sowie eine generische Klasse namens `BaseCollection` deren Typparameter von `BaseClass` abgeleitet werden muss. Aber, da `BaseClass` nicht CLS-kompatibel ist, gibt der Compiler eine Warnung aus.

```csharp
using System;

[assembly:CLSCompliant(true)]

[CLSCompliant(false)] public class BaseClass
{}

public class BaseCollection<T> where T : BaseClass
{}
// Attempting to compile the example displays the following output:
//    warning CS3024: Constraint type 'BaseClass' is not CLS-compliant
```

```vb
Assembly: CLSCompliant(True)>

<CLSCompliant(False)> Public Class BaseClass
End Class

Public Class BaseCollection(Of T As BaseClass)
End Class
' Attempting to compile the example displays the following output:
'    warning BC40040: Generic parameter constraint type 'BaseClass' is not
'    CLS-compliant.
'
'    Public Class BaseCollection(Of T As BaseClass)
'                                        ~~~~~~~~~
```

Wenn ein generischer Typ von einem generischen Basistyp abgeleitet ist, muss er alle Einschränkungen erneut deklarieren, damit sichergestellt ist, dass auch die Einschränkungen des Basistyps erfüllt werden. Im folgenden Beispiel wird `Number<T>` definiert, das einen numerischen Typ darstellen kann. Es definiert auch eine `FloatingPoint<T>`-Klasse, die einen Gleitkommawert darstellt. Allerdings kann der Quellcode nicht kompiliert werden, da die Einschränkung auf `Number<T>` (dieses T muss ein Werttyp sein) nicht auf `FloatingPoint<T>` angewendet werden.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T>
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
// The attempt to compile the example displays the following output:
//       error CS0453: The type 'T' must be a non-nullable value type in
//               order to use it as parameter 'T' in the generic type or method 'Number<T>'
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
' The attempt to compile the example displays the following output:
'    error BC32105: Type argument 'T' does not satisfy the 'Structure'
'    constraint for type parameter 'T'.
'
'    Public Class FloatingPoint(Of T) : Inherits Number(Of T)
'                                                          ~
```

Das Beispiel wird erfolgreich kompiliert, wenn die Einschränkung der `FloatingPoint<T>`-Klasse hinzugefügt wird.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T> where T : struct
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T As Structure) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
```

Die Common Language Specification erzwingt ein konservatives Pro-Instanziierungsmodell für geschachtelte Typen und geschützte Member. Offene generische Typen können Felder oder Member mit Signaturen nicht verfügbar machen, die eine bestimmte Instanziierung eines geschachtelten, geschützten generischen Typs enthalten. Nicht generische Typen, die eine bestimmte Instanziierung einer generischen Basisklasse oder Schnittstelle erweitern, können Felder oder Member mit Signaturen nicht verfügbar machen, die eine andere Instanziierung eines geschachtelten, geschützten generischen Typs enthalten.

Das folgende Beispiel definiert einen generischen Typ „`C1<T>`“ und eine geschützte Klasse „`C1<T>.N`“. `C1<T>` verfügt über zwei Methoden, `M1` und `M2`. Allerdings ist `M1` nicht CLS-kompatibel, da versucht wird, ein `C1<int>.N`-Objekt von `C1<T>` zurückzugeben. Eine zweite Klasse, `C2`, wird von `C1<long>` abgeleitet. Sie verfügt über zwei Methoden, `M3` und `M4`. `M3` ist nicht CLS-kompatibel, da versucht wird, ein `C1<int>.N`-Objekt von einer Unterklasse von `C1<long>` zurückzugeben. Beachten Sie, dass Sprachcompiler sogar noch restriktiver sein können. In diesem Beispiel zeigt Visual Basic einen Fehler an, wenn versucht wird, `M4` zu kompilieren.

```csharp
using System;

[assembly:CLSCompliant(true)]

public class C1<T>
{
   protected class N { }

   protected void M1(C1<int>.N n) { } // Not CLS-compliant - C1<int>.N not
                                      // accessible from within C1<T> in all
                                      // languages
   protected void M2(C1<T>.N n) { }   // CLS-compliant – C1<T>.N accessible
                                      // inside C1<T>
}

public class C2 : C1<long>
{
   protected void M3(C1<int>.N n) { }  // Not CLS-compliant – C1<int>.N is not
                                       // accessible in C2 (extends C1<long>)

   protected void M4(C1<long>.N n) { } // CLS-compliant, C1<long>.N is
                                       // accessible in C2 (extends C1<long>)
}
// Attempting to compile the example displays output like the following:
//       Generics4.cs(9,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
//       Generics4.cs(18,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
```

```vb
<Assembly:CLSCompliant(True)>

Public Class C1(Of T)
   Protected Class N
   End Class

   Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
                                             ' accessible from within C1(Of T) in all
   End Sub                                   ' languages

   Protected Sub M2(n As C1(Of T).N)     ' CLS-compliant – C1(Of T).N accessible
   End Sub                               ' inside C1(Of T)
End Class

Public Class C2 : Inherits C1(Of Long)
   Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant – C1(Of Integer).N is not
   End Sub                                   ' accessible in C2 (extends C1(Of Long))

   Protected Sub M4(n As C1(Of Long).N)
   End Sub
End Class
' Attempting to compile the example displays output like the following:
'    error BC30508: 'n' cannot expose type 'C1(Of Integer).N' in namespace
'    '<Default>' through class 'C1'.
'
'       Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
'                             ~~~~~~~~~~~~~~~~
'    error BC30389: 'C1(Of T).N' is not accessible in this context because
'    it is 'Protected'.
'
'       Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant - C1(Of Integer).N is not
'
'                             ~~~~~~~~~~~~~~~~
'
'    error BC30389: 'C1(Of T).N' is not accessible in this context because it is 'Protected'.
'
'       Protected Sub M4(n As C1(Of Long).N)
'                             ~~~~~~~~~~~~~
```

### <a name="constructors"></a>Konstruktoren

Bei Konstruktoren in den CLS-kompatiblen Klassen und Strukturen müssen die folgenden Regeln beachtet werden:

* Der Konstruktor einer abgeleiteten Klasse muss den Instanzkonstruktor der Basisklasse aufrufen, bevor er auf geerbte Instanzdaten zugreift. Diese Anforderung basiert auf der Tatsache, dass Konstruktoren nicht nach ihren abgeleiteten Klassen geerbt werden. Diese Regel gilt nicht für Strukturen, die keine direkte Vererbung unterstützen.

  In der Regel erzwingen Compiler diese Regel unabhängig von der CLS-Kompatibilität, wie im folgenden Beispiel gezeigt. Es wird eine `Doctor`-Klasse erstellt, die von einer `Person`-Klasse abgeleitet ist. Doch die `Doctor`-Klasse kann den `Person`-Klassenkonstruktor nicht zum Initialisieren geerbter Instanzfelder aufrufen.

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public class Person
    {
    private string fName, lName, _id;

    public Person(string firstName, string lastName, string id)
    {
        if (String.IsNullOrEmpty(firstName + lastName))
            throw new ArgumentNullException("Either a first name or a last name must be provided.");

        fName = firstName;
        lName = lastName;
        _id = id;
    }

    public string FirstName
    {
        get { return fName; }
    }

    public string LastName
    {
        get { return lName; }
    }

    public string Id
    {
        get { return _id; }
    }

    public override string ToString()
    {
        return String.Format("{0}{1}{2}", fName,
                            String.IsNullOrEmpty(fName) ?  "" : " ",
                            lName);
    }
    }

    public class Doctor : Person
    {
    public Doctor(string firstName, string lastName, string id)
    {
    }

    public override string ToString()
    {
        return "Dr. " + base.ToString();
    }
    }
    // Attempting to compile the example displays output like the following:
    //    ctor1.cs(45,11): error CS1729: 'Person' does not contain a constructor that takes 0
    //            arguments
    //    ctor1.cs(10,11): (Location of symbol related to previous error)
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Class Person
       Private fName, lName, _id As String

       Public Sub New(firstName As String, lastName As String, id As String)
          If String.IsNullOrEmpty(firstName + lastName) Then
             Throw New ArgumentNullException("Either a first name or a last name must be provided.")
          End If

          fName = firstName
          lName = lastName
          _id = id
       End Sub

       Public ReadOnly Property FirstName As String
          Get
             Return fName
          End Get
       End Property

       Public ReadOnly Property LastName As String
          Get
             Return lName
          End Get
       End Property

       Public ReadOnly Property Id As String
          Get
             Return _id
          End Get
       End Property

       Public Overrides Function ToString() As String
          Return String.Format("{0}{1}{2}", fName,
                               If(String.IsNullOrEmpty(fName), "", " "),
                               lName)
       End Function
    End Class

    Public Class Doctor : Inherits Person
       Public Sub New(firstName As String, lastName As String, id As String)
       End Sub

       Public Overrides Function ToString() As String
          Return "Dr. " + MyBase.ToString()
       End Function
    End Class
    ' Attempting to compile the example displays output like the following:
    '    Ctor1.vb(46) : error BC30148: First statement of this 'Sub New' must be a call
    '    to 'MyBase.New' or 'MyClass.New' because base class 'Person' of 'Doctor' does
    '    not have an accessible 'Sub New' that can be called with no arguments.
    '
    '       Public Sub New()
    '                  ~~~
    ````

* Ein Objektkonstruktor kann nur aufgerufen werden, um ein Objekt zu erstellen. Außerdem kann ein Objekt nicht zweimal initialisiert werden. Beispielsweise bedeutet dies, dass mit `Object.MemberwiseClone` keine Konstruktoren aufgerufen werden dürfen.

### <a name="properties"></a>Eigenschaften

Eigenschaften in den CLS-kompatiblen Typen müssen die folgenden Regeln beachten:

* Eine Eigenschaft muss über einen Setter, einen Getter oder beides verfügen. In einer Assembly werden diese als spezielle Methoden implementiert, das bedeutet, dass sie als separate Methoden (der Getter hat den Namen `get`\_*propertyname* und der Setter den Namen `set`\_*propertyname*) erscheinen, die als `SpecialName` gekennzeichnet in den Metadaten der Assembly angezeigt werden. Die C#-Compiler erzwingt diese Regel automatisch, ohne das <xref:System.CLSCompliantAttribute>-Attribut anzuwenden.

* Ein Typ der Eigenschaft entspricht dem Rückgabetyp der Getter-Methode der Eigenschaft und dem letzten Argument der Setter-Methode. Diese Typen müssen CLS-kompatibel sein, und Argumente können der Eigenschaft nicht mithilfe eines Verweises zugewiesen werden (das heißt, es können keine verwalteten Zeiger sein).

* Wenn eine Eigenschaft einen Getter und einen Setter aufweist, müssen beide "virtual", "static" oder "instance" sein. Der C#-Compiler erzwingt diese Regel automatisch über die Eigenschaftendefinitionssyntax.

### <a name="events"></a>Ereignisse

Ein Ereignis wird vom Namen und dem Typ definiert. Der Ereignistyp ist ein Delegat, der zum Angeben des Ereignisses verwendet wird. Zum Beispiel hat das `DbConnection.StateChange`-Ereignis den Typ `StateChangeEventHandler`. Neben dem Ereignis selbst, stellen drei Methoden mit Namen basierend auf dem Ereignisnamen die Implementierung des Ereignisses bereit und werden in den Metadaten der Assembly als `SpecialName` gekennzeichnet:

* Eine Methode zum Hinzufügen eines Ereignishandlers namens `add`_*Ereignisname*. Die Ereignisabonnementmethode für das `DbConnection.StateChange`-Ereignis hat zum Beispiel den Namen `add_StateChange`.

* Eine Methode zum Enternen eines Ereignishandlers namens `remove`_*Ereignisname*. Die Entfernenmethode für das `DbConnection.StateChange`-Ereignis hat zum Beispiel den Namen `remove_StateChange`.

* Eine Methode für den Hinweis, dass das Ereignis namens `raise`\_*EventName* aufgetreten ist.

> [!NOTE]
> Die meisten Regeln der Common Language Specification zu Ereignissen werden von den Sprachcompilern implementiert und sind für Komponentenentwickler transparent.

Die Methoden für das Hinzufügen, Entfernen und Auslösen des Ereignisses verfügen über den gleichen Zugriff. Sie müssen zudem "static", "instance" oder "virtual" sein. Die Methoden zum Hinzufügen und Entfernen eines Ereignisses verfügen über einen Parameter, dessen Typ der Ereignisdelegattyp ist. Die Methoden zum Hinzufügen und Entfernen müssen beide vorhanden sein oder beide fehlen.

Im folgenden Beispiel wird eine CLS-kompatible Klasse namens `Temperature` definiert, die ein `TemperatureChanged`-Ereignis auslöst, wenn die Temperaturänderung zwischen zwei Messungen einem Schwellenwert entspricht oder diesen überschreitet. Die `Temperature`-Klasse definiert eine `raise_TemperatureChanged`-Methode explizit, sodass sie selektiv Ereignishandler ausführen kann.

```csharp
using System;
using System.Collections;
using System.Collections.Generic;

[assembly: CLSCompliant(true)]

public class TemperatureChangedEventArgs : EventArgs
{
   private Decimal originalTemp;
   private Decimal newTemp;
   private DateTimeOffset when;

   public TemperatureChangedEventArgs(Decimal original, Decimal @new, DateTimeOffset time)
   {
      originalTemp = original;
      newTemp = @new;
      when = time;
   }

   public Decimal OldTemperature
   {
      get { return originalTemp; }
   }

   public Decimal CurrentTemperature
   {
      get { return newTemp; }
   }

   public DateTimeOffset Time
   {
      get { return when; }
   }
}

public delegate void TemperatureChanged(Object sender, TemperatureChangedEventArgs e);

public class Temperature
{
   private struct TemperatureInfo
   {
      public Decimal Temperature;
      public DateTimeOffset Recorded;
   }

   public event TemperatureChanged TemperatureChanged;

   private Decimal previous;
   private Decimal current;
   private Decimal tolerance;
   private List<TemperatureInfo> tis = new List<TemperatureInfo>();

   public Temperature(Decimal temperature, Decimal tolerance)
   {
      current = temperature;
      TemperatureInfo ti = new TemperatureInfo();
      ti.Temperature = temperature;
      tis.Add(ti);
      ti.Recorded = DateTimeOffset.UtcNow;
      this.tolerance = tolerance;
   }

   public Decimal CurrentTemperature
   {
      get { return current; }
      set {
         TemperatureInfo ti = new TemperatureInfo();
         ti.Temperature = value;
         ti.Recorded = DateTimeOffset.UtcNow;
         previous = current;
         current = value;
         if (Math.Abs(current - previous) >= tolerance)
            raise_TemperatureChanged(new TemperatureChangedEventArgs(previous, current, ti.Recorded));
      }
   }

   public void raise_TemperatureChanged(TemperatureChangedEventArgs eventArgs)
   {
      if (TemperatureChanged == null)
         return;

      foreach (TemperatureChanged d in TemperatureChanged.GetInvocationList()) {
         if (d.Method.Name.Contains("Duplicate"))
            Console.WriteLine("Duplicate event handler; event handler not executed.");
         else
            d.Invoke(this, eventArgs);
      }
   }
}

public class Example
{
   public Temperature temp;

   public static void Main()
   {
      Example ex = new Example();
   }

   public Example()
   {
      temp = new Temperature(65, 3);
      temp.TemperatureChanged += this.TemperatureNotification;
      RecordTemperatures();
      Example ex = new Example(temp);
      ex.RecordTemperatures();
   }

   public Example(Temperature t)
   {
      temp = t;
      RecordTemperatures();
   }

   public void RecordTemperatures()
   {
      temp.TemperatureChanged += this.DuplicateTemperatureNotification;
      temp.CurrentTemperature = 66;
      temp.CurrentTemperature = 63;
   }

   internal void TemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }

   public void DuplicateTemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }
}
```

```vb
Imports System.Collections
Imports System.Collections.Generic

<Assembly: CLSCompliant(True)>

Public Class TemperatureChangedEventArgs   : Inherits EventArgs
   Private originalTemp As Decimal
   Private newTemp As Decimal
   Private [when] As DateTimeOffset

   Public Sub New(original As Decimal, [new] As Decimal, [time] As DateTimeOffset)
      originalTemp = original
      newTemp = [new]
      [when] = [time]
   End Sub

   Public ReadOnly Property OldTemperature As Decimal
      Get
         Return originalTemp
      End Get
   End Property

   Public ReadOnly Property CurrentTemperature As Decimal
      Get
         Return newTemp
      End Get
   End Property

   Public ReadOnly Property [Time] As DateTimeOffset
      Get
         Return [when]
      End Get
   End Property
End Class

Public Delegate Sub TemperatureChanged(sender As Object, e As TemperatureChangedEventArgs)

Public Class Temperature
   Private Structure TemperatureInfo
      Dim Temperature As Decimal
      Dim Recorded As DateTimeOffset
   End Structure

   Public Event TemperatureChanged As TemperatureChanged

   Private previous As Decimal
   Private current As Decimal
   Private tolerance As Decimal
   Private tis As New List(Of TemperatureInfo)

   Public Sub New(temperature As Decimal, tolerance As Decimal)
      current = temperature
      Dim ti As New TemperatureInfo()
      ti.Temperature = temperature
      ti.Recorded = DateTimeOffset.UtcNow
      tis.Add(ti)
      Me.tolerance = tolerance
   End Sub

   Public Property CurrentTemperature As Decimal
      Get
         Return current
      End Get
      Set
         Dim ti As New TemperatureInfo
         ti.Temperature = value
         ti.Recorded = DateTimeOffset.UtcNow
         previous = current
         current = value
         If Math.Abs(current - previous) >= tolerance Then
            raise_TemperatureChanged(New TemperatureChangedEventArgs(previous, current, ti.Recorded))
         End If
      End Set
   End Property

   Public Sub raise_TemperatureChanged(eventArgs As TemperatureChangedEventArgs)
      If TemperatureChangedEvent Is Nothing Then Exit Sub

      Dim ListenerList() As System.Delegate = TemperatureChangedEvent.GetInvocationList()
      For Each d As TemperatureChanged In TemperatureChangedEvent.GetInvocationList()
         If d.Method.Name.Contains("Duplicate") Then
            Console.WriteLine("Duplicate event handler; event handler not executed.")
         Else
            d.Invoke(Me, eventArgs)
         End If
      Next
   End Sub
End Class

Public Class Example
   Public WithEvents temp As Temperature

   Public Shared Sub Main()
      Dim ex As New Example()
   End Sub

   Public Sub New()
      temp = New Temperature(65, 3)
      RecordTemperatures()
      Dim ex As New Example(temp)
      ex.RecordTemperatures()
   End Sub

   Public Sub New(t As Temperature)
      temp = t
      RecordTemperatures()
   End Sub

   Public Sub RecordTemperatures()
      temp.CurrentTemperature = 66
      temp.CurrentTemperature = 63

   End Sub

   Friend Shared Sub TemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub

   Friend Shared Sub DuplicateTemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub
End Class
```

### <a name="overloads"></a>Overloads

Die Common Language Specification erzwingt die folgenden Anforderungen für überladene Member:

* Member können auf Grundlage der Anzahl und des Typs eines Parameters überladen werden. Aufrufkonvention, Rückgabetyp, die benutzerdefinierten Modifizierer, die auf die Methode oder deren Parameter angewendet werden und, ob Parameter nach Wert oder nach Verweis übergeben werden, werden bei der Unterscheidung zwischen Überladungen nicht beachtet. Ein Beispiel finden Sie im Abschnitt [Namenskonventionen](#naming-conventions) im Code für die Anforderung, dass Namen innerhalb eines Bereichs eindeutig sein müssen.

* Nur Eigenschaften und Methoden können überladen werden. Felder und Ereignisse können nicht überladen werden.

* Generische Methoden können auf Grundlage der Anzahl ihrer generischen Parameter überladen werden.

> [!NOTE]
> Der `op_Explicit`-Operator und der `op_Implicit`-Operator sind Ausnahmen von der Regel, dass Rückgabewerte nicht als Teil einer Methodensignatur für Überladungsauflösung gelten. Diese beiden Operatoren können auf Grundlage ihrer Parameter und ihrer Rückgabewerte überladen werden.

### <a name="exceptions"></a>Ausnahmen

Ausnahmeobjekte müssen von [System.Exception](xref:System.Exception) oder von einem anderen Typ abgeleitet werden, der von `System.Exception` abgeleitet wird. Im folgenden Beispiel wird der Compilerfehler veranschaulicht, der entsteht, wenn eine benutzerdefinierte Klasse namens `ErrorClass` für die Ausnahmebehandlung verwendet wird.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
// Compilation produces a compiler error like the following:
//    Exceptions1.cs(26,16): error CS0155: The type caught or thrown must be derived from
//            System.Exception
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
' Compilation produces a compiler error like the following:
'    Exceptions1.vb(27) : error BC30665: 'Throw' operand must derive from 'System.Exception'.
'
'             Throw BadIndex
'             ~~~~~~~~~~~~~~
```

Um diesen Fehler zu beheben, muss die `ErrorClass`-Klasse von `System.Exception` erben. Außerdem muss die Message-Eigenschaft außer Kraft gesetzt werden. Im folgenden Beispiel werden diese Fehler korrigiert, um eine CLS-kompatible `ErrorClass`-Klasse zu definieren.

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass : Exception
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public override string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass : Inherits Exception
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public Overrides ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
```

### <a name="attributes"></a>Attribute

In .NET-Frameworkassemblys stellen benutzerdefinierte Attribute einen erweiterbaren Mechanismus zum Speichern benutzerdefinierter Attribute und das Abrufen von Metadaten über Programmierobjekte, wie Assemblys, Typen, Member und Methodenparameter, bereit. Benutzerdefinierte Attribute müssen von [System.Attribute](xref:System.Attribute) oder einem Typ abgeleitet werden, der von `System.Attribute` abgeleitet wird.

Das folgende Beispiel verstößt gegen diese Regel. Es wird eine `NumericAttribute`-Klasse definiert, die nicht von `System.Attribute` abgeleitet ist. Beachten Sie, dass der Compilerfehler nur entsteht, wenn das nicht CLS-kompatible Attribut angewendet wird, nicht aber, wenn die Klasse definiert ist.

```csharp
using System;

[assembly: CLSCompliant(true)]

[AttributeUsageAttribute(AttributeTargets.Class | AttributeTargets.Struct)]
public class NumericAttribute
{
   private bool _isNumeric;

   public NumericAttribute(bool isNumeric)
   {
      _isNumeric = isNumeric;
   }

   public bool IsNumeric
   {
      get { return _isNumeric; }
   }
}

[Numeric(true)] public struct UDouble
{
   double Value;
}
// Compilation produces a compiler error like the following:
//    Attribute1.cs(22,2): error CS0616: 'NumericAttribute' is not an attribute class
//    Attribute1.cs(7,14): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

<AttributeUsageAttribute(AttributeTargets.Class Or AttributeTargets.Struct)> _
Public Class NumericAttribute
   Private _isNumeric As Boolean

   Public Sub New(isNumeric As Boolean)
      _isNumeric = isNumeric
   End Sub

   Public ReadOnly Property IsNumeric As Boolean
      Get
         Return _isNumeric
      End Get
   End Property
End Class

<Numeric(True)> Public Structure UDouble
   Dim Value As Double
End Structure
' Compilation produces a compiler error like the following:
'    error BC31504: 'NumericAttribute' cannot be used as an attribute because it
'    does not inherit from 'System.Attribute'.
'
'    <Numeric(True)> Public Structure UDouble
'     ~~~~~~~~~~~~~
```

Der Konstruktor oder die Eigenschaften eines CLS-kompatiblen Attributs können nur die folgenden Typen verfügbar machen:

* [Boolean](xref:System.Boolean)

* [Byte](xref:System.Byte)

* [Char](xref:System.Char)

* [Double](xref:System.Double)

* [Int16](xref:System.Int16)

* [Int32](xref:System.Int32)

* [Int64](xref:System.Int64)

* [Single](xref:System.Single)

* [String](xref:System.String)

* [Type](xref:System.Type)

* Ein Enumerationstyp, dessen zugrunde liegender Typ `Byte`, `Int16`, `Int32` oder `Int64` ist.

Im folgenden Beispiel wird eine von [Attribute](xref:System.Attribute) abgeleitete `DescriptionAttribute`-Klasse definiert. Der Klassenkonstruktor verfügt über einen Parameter des Typs `Descriptor`, sodass die Klasse nicht CLS-kompatibel ist. Beachten Sie, dass der C#-Compiler eine Warnung ausgibt, die Kompilierung aber erfolgreich durchführt.

```csharp
using System;

[assembly:CLSCompliantAttribute(true)]

public enum DescriptorType { type, member };

public class Descriptor
{
   public DescriptorType Type;
   public String Description;
}

[AttributeUsage(AttributeTargets.All)]
public class DescriptionAttribute : Attribute
{
   private Descriptor desc;

   public DescriptionAttribute(Descriptor d)
   {
      desc = d;
   }

   public Descriptor Descriptor
   { get { return desc; } }
}
// Attempting to compile the example displays output like the following:
//       warning CS3015: 'DescriptionAttribute' has no accessible
//               constructors which use only CLS-compliant types
```

```vb
<Assembly:CLSCompliantAttribute(True)>

Public Enum DescriptorType As Integer
   Type = 0
   Member = 1
End Enum

Public Class Descriptor
   Public Type As DescriptorType
   Public Description As String
End Class

<AttributeUsage(AttributeTargets.All)> _
Public Class DescriptionAttribute : Inherits Attribute
   Private desc As Descriptor

   Public Sub New(d As Descriptor)
      desc = d
   End Sub

   Public ReadOnly Property Descriptor As Descriptor
      Get
         Return desc
      End Get
   End Property
End Class
```

## <a name="the-clscompliantattribute-attribute"></a>Das CLSCompliantAttribute-Attribut

Das [CLSCompliantAttribute](xref:System.CLSCompliantAttribute)-Attribut wird verwendet, um anzugeben, ob ein Programmelement mit der Common Language Specification kompatibel ist. Der `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)`-Konstruktor enthält einen einzelnen erforderlichen Parameter, *isCompliant*, der angibt, ob das Programmelement CLS-kompatibel ist.

Zur Kompilierzeit erkennt der Compiler nicht kompatible Elemente, von denen angenommen wird, dass sie CLS-kompatibel sind, und gibt eine Warnung aus. Der Compiler gibt keine Warnungen für die Typen oder Member aus, die explizit als nicht kompatibel deklariert werden.

Komponentenentwickler können das `CLSCompliantAttribute`-Attribut auf zwei Arten verwenden:

* Um die Teile der öffentlichen Schnittstelle zu definieren, die von einer CLS-kompatiblen Komponente und den nicht CLS-kompatiblen Teilen verfügbar gemacht werden. Wenn das Attribut verwendet wird, um bestimmte Programmelemente als CLS-kompatibel zu markieren, stellt seine Verwendung sicher, dass auf diese Elemente aus allen Sprachen und Tools für das .NET Framework zugegriffen werden kann.

* Um sicherzustellen, dass die öffentliche Schnittstelle der Komponentenbibliothek nur Programmelemente verfügbar macht, die CLS-kompatibel sind. Wenn Elemente nicht CLS-kompatibel sind, geben Compiler im Allgemeinen eine Warnung aus.

> [!WARNING]
> In einigen Fällen erzwingen CLS-kompatible Sprachcompiler Regeln unabhängig davon, ob das `CLSCompliantAttribute`-Attribut verwendet wird. Das Definieren eines `*static`-Members in einer Schnittstelle verstößt zum Beispiel gegen eine CLS-Regel. Wenn Sie jedoch einen `*static`-Member in einer Schnittstelle definieren, zeigt der C#-Compiler eine Fehlermeldung an, und beim Kompilieren der App tritt ein Fehler auf.

Das `CLSCompliantAttribute`-Attribut wird mit einem [AttributeUsageAttribute](xref:System.AttributeUsageAttribute)-Attribut markiert, das einen Wert von `AttributeTargets.All` aufweist. Dieser Wert ermöglicht das Anwenden des `CLSCompliantAttribute`-Attributs auf jedem Programmelement, einschließlich Assemblys, Modulen, Typen (Klassen, Strukturen, Enumerationen, Schnittstellen und Delegaten), Typmembern (Konstruktoren, Methoden, Eigenschaften, Feldern und Ereignissen), Parametern, generischen Parametern und Rückgabewerten. In der Praxis sollten Sie das Attribut allerdings nur auf Assemblys, Typen und Typmember anwenden. Andernfalls ignorieren Compiler das Attribut und generieren weiterhin Compilerwarnungen, wenn sie einen nicht kompatiblen Parameter, einen generischen Parameter oder einen Rückgabewert in der öffentlichen Schnittstelle der Bibliothek vorfinden.

Der Wert des `CLSCompliantAttribute`-Attributs wird von enthaltenen Programmelementen geerbt. Wenn beispielsweise eine Assembly als CLS-kompatibel markiert ist, sind die Typen auch CLS-kompatibel. Wenn ein Typ als CLS-kompatibel gekennzeichnet ist, sind seine geschachtelten Typen und Member auch CLS-kompatibel.

Sie können die geerbte Kompatibilität explizit überschreiben, indem Sie das `CLSCompliantAttribute`- Attribut auf ein enthaltenes Programmelement anwenden. Beispielsweise können Sie das `CLSCompliantAttribute`-Attribut mit einem *isCompliant*-Wert von `false` verwenden, um einen inkompatiblen Typ in einer kompatiblen Assembly zu definieren, und Sie können das Attribut mit einem *isCompliant*-Wert von `true` verwenden, um einen kompatiblen Typ in einer inkompatiblen Assembly zu definieren. Sie können auch nicht kompatible Member in einem kompatiblen Typ definieren. Allerdings kann ein nicht kompatibler Typ keine kompatiblen Member aufweisen, sodass Sie das Attribut nicht mit einem *isCompliant*-Wert von `true` verwenden können, um die Vererbung eines nicht kompatiblen Typs zu überschreiben.

Wenn Sie Komponenten entwickeln, sollten Sie stets das `CLSCompliantAttribute`- Attribut verwenden, um anzugeben, ob die Assembly, die Typen und die Member CLS-kompatibel sind.

So erstellen Sie CLS-kompatible Komponenten:

1. Verwenden Sie `CLSCompliantAttribute`, um die Assembly als CLS-kompatibel zu markieren.

2. Markieren Sie jeden öffentlich verfügbar gemachten, nicht CLS-kompatiblen Typ in der Assembly als nicht kompatibel.

3. Markieren Sie alle öffentlich verfügbar gemachten Member in CLS-kompatiblen Typen als nicht kompatibel.

4. Stellen Sie eine CLS-kompatible Alternative für nicht CLS-kompatible Member bereit.

Wenn alle inkompatiblen Typen und Member erfolgreich markiert wurden, sollte der Compiler keine Kompatibilitätswarnungen ausgeben. Allerdings sollten Sie angeben, welche Member nicht CLS-kompatibel sind und ihre CLS-kompatiblen Alternativen in der Produktdokumentation aufführen.

Im folgenden Beispiel wird das `CLSCompliantAttribute`-Attribut verwendet, um eine CLS-kompatible Assembly und einen Typ, `CharacterUtilities`, zu definieren, der über zwei nicht CLS-kompatible Member verfügt. Da beide Member mit dem `CLSCompliant(false)`-Attribut markiert sind, generiert der Compiler keine Warnungen. Die Klasse stellt auch eine CLS-kompatible Alternative für beide Methoden bereit. Normalerweise würden der `ToUTF16`- Methode lediglich zwei Überladungen hinzugefügt werden, um CLS-kompatible Alternativen bereitzustellen. Da Methoden aber nicht aufgrund des Rückgabewerts überladen werden können, sind die Namen der CLS-kompatiblen Methoden von den Namen der nicht kompatiblen Methoden unterschiedlich.

```csharp
using System;
using System.Text;

[assembly:CLSCompliant(true)]

public class CharacterUtilities
{
   [CLSCompliant(false)] public static ushort ToUTF16(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return Convert.ToUInt16(s[0]);
   }

   [CLSCompliant(false)] public static ushort ToUTF16(Char ch)
   {
      return Convert.ToUInt16(ch);
   }

   // CLS-compliant alternative for ToUTF16(String).
   public static int ToUTF16CodeUnit(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return (int) Convert.ToUInt16(s[0]);
   }

   // CLS-compliant alternative for ToUTF16(Char).
   public static int ToUTF16CodeUnit(Char ch)
   {
      return Convert.ToInt32(ch);
   }

   public bool HasMultipleRepresentations(String s)
   {
      String s1 = s.Normalize(NormalizationForm.FormC);
      return s.Equals(s1);
   }

   public int GetUnicodeCodePoint(Char ch)
   {
      if (Char.IsSurrogate(ch))
         throw new ArgumentException("ch cannot be a high or low surrogate.");

      return Char.ConvertToUtf32(ch.ToString(), 0);
   }

   public int GetUnicodeCodePoint(Char[] chars)
   {
      if (chars.Length > 2)
         throw new ArgumentException("The array has too many characters.");

      if (chars.Length == 2) {
         if (! Char.IsSurrogatePair(chars[0], chars[1]))
            throw new ArgumentException("The array must contain a low and a high surrogate.");
         else
            return Char.ConvertToUtf32(chars[0], chars[1]);
      }
      else {
         return Char.ConvertToUtf32(chars.ToString(), 0);
      }
   }
}
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class CharacterUtilities
   <CLSCompliant(False)> Public Shared Function ToUTF16(s As String) As UShort
      s = s.Normalize(NormalizationForm.FormC)
      Return Convert.ToUInt16(s(0))
   End Function

   <CLSCompliant(False)> Public Shared Function ToUTF16(ch As Char) As UShort
      Return Convert.ToUInt16(ch)
   End Function

   ' CLS-compliant alternative for ToUTF16(String).
   Public Shared Function ToUTF16CodeUnit(s As String) As Integer
      s = s.Normalize(NormalizationForm.FormC)
      Return CInt(Convert.ToInt16(s(0)))
   End Function

   ' CLS-compliant alternative for ToUTF16(Char).
   Public Shared Function ToUTF16CodeUnit(ch As Char) As Integer
      Return Convert.ToInt32(ch)
   End Function

   Public Function HasMultipleRepresentations(s As String) As Boolean
      Dim s1 As String = s.Normalize(NormalizationForm.FormC)
      Return s.Equals(s1)
   End Function

   Public Function GetUnicodeCodePoint(ch As Char) As Integer
      If Char.IsSurrogate(ch) Then
         Throw New ArgumentException("ch cannot be a high or low surrogate.")
      End If
      Return Char.ConvertToUtf32(ch.ToString(), 0)
   End Function

   Public Function GetUnicodeCodePoint(chars() As Char) As Integer
      If chars.Length > 2 Then
         Throw New ArgumentException("The array has too many characters.")
      End If
      If chars.Length = 2 Then
         If Not Char.IsSurrogatePair(chars(0), chars(1)) Then
            Throw New ArgumentException("The array must contain a low and a high surrogate.")
         Else
            Return Char.ConvertToUtf32(chars(0), chars(1))
         End If
      Else
         Return Char.ConvertToUtf32(chars.ToString(), 0)
      End If
   End Function
End Class
```

Wenn Sie eine App anstelle einer Bibliothek entwickeln, (das heißt, wenn Sie keine Typen oder Member verfügbar machen, die von anderen App-Entwicklern genutzt werden können), ist die CLS-Kompatibilität der Programmelemente, die von der App genutzt werden, nur relevant, wenn sie von Ihrer Sprache nicht unterstützt werden. In diesem Fall generiert der Sprachcompiler einen Fehler, wenn Sie versuchen, ein nicht CLS-kompatibles Element zu verwenden.

## <a name="cross-language-interoperability"></a>Sprachübergreifende Interoperabilität

Der Begriff „Sprachunabhängigkeit“ kann mehrere Bedeutungen haben. Eine Bedeutung umfasst die nahtlose Nutzung von Typen, die in einer Sprache geschrieben werden, in einer App, die in einer anderen Sprache geschrieben wurde. Eine zweite Bedeutung, die in diesem Artikels hervorgehoben wird, umfasst die Kombination von Code aus mehreren Sprachen in einer einzelnen .NET Framework-Assembly.

Das folgende Beispiel veranschaulicht die sprachübergreifende Interoperabilität. Es wird die Klassenbibliothek Utilities.dll erstellt, die zwei Klassen einschließt: `NumericLib` und `StringLib`. Die `NumericLib`-Klasse wurde in C# und die `StringLib`-Klasse in Visual Basic geschrieben. Im Folgenden sehen Sie den Quellcode für `StringUtil.vb`, der in der `StringLib`-Klasse einen einzelnen Member `ToTitleCase` enthält.

```vb
Imports System.Collections.Generic
Imports System.Runtime.CompilerServices

Public Module StringLib
   Private exclusions As List(Of String)

   Sub New()
      Dim words() As String = { "a", "an", "and", "of", "the" }
      exclusions = New List(Of String)
      exclusions.AddRange(words)
   End Sub

   <Extension()> _
   Public Function ToTitleCase(title As String) As String
      Dim words() As String = title.Split()
      Dim result As String = String.Empty

      For ctr As Integer = 0 To words.Length - 1
         Dim word As String = words(ctr)
         If ctr = 0 OrElse Not exclusions.Contains(word.ToLower()) Then
            result += word.Substring(0, 1).ToUpper() + _
                      word.Substring(1).ToLower()
         Else
            result += word.ToLower()
         End If
         If ctr <= words.Length - 1 Then
            result += " "
         End If
      Next
      Return result
   End Function
End Module
```

Im Folgenden sehen Sie den Quellcode für "NumberUtil.cs", der eine `NumericLib`-Klasse mit zwei Membern definiert: `IsEven` und `NearZero`.

```csharp
using System;

public static class NumericLib
{
   public static bool IsEven(this IConvertible number)
   {
      if (number is Byte ||
          number is SByte ||
          number is Int16 ||
          number is UInt16 ||
          number is Int32 ||
          number is UInt32 ||
          number is Int64)
         return ((long) number) % 2 == 0;
      else if (number is UInt64)
         return ((ulong) number) %2 == 0;
      else
         throw new NotSupportedException("IsEven called for a non-integer value.");
   }

   public static bool NearZero(double number)
   {
      return number < .00001;
   }
}
```

Um die beiden Klassen in einer einzelnen Assembly zu verpacken, müssen Sie sie in Module kompilieren. Verwenden Sie zum Kompilieren der Visual Basic-Quellcodedatei in einem Modul folgenden Befehl:

```console
vbc /t:module StringUtil.vb
```

Verwenden Sie zum Kompilieren der C#-Quellcodedatei in einem Modul folgenden Befehl:

```console
csc /t:module NumberUtil.cs
```

Verwenden Sie dann das Linktool (Link.exe), um die beiden Module in eine Assembly zu kompilieren:

```console
link numberutil.netmodule stringutil.netmodule /out:UtilityLib.dll /dll
```

Das folgende Beispiel ruft dann die `NumericLib.NearZero`-Methode und die `StringLib.ToTitleCase`-Methode auf. Beachten Sie, dass sowohl der Visual Basic-Code als auch der C#-Code auf die Methoden in beiden Klassen zugreifen können.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double dbl = 0.0 - Double.Epsilon;
      Console.WriteLine(NumericLib.NearZero(dbl));

      string s = "war and peace";
      Console.WriteLine(s.ToTitleCase());
   }
}
// The example displays the following output:
//       True
//       War and Peace
```

```vb
Module Example
   Public Sub Main()
      Dim dbl As Double = 0.0 - Double.Epsilon
      Console.WriteLine(NumericLib.NearZero(dbl))

      Dim s As String = "war and peace"
      Console.WriteLine(s.ToTitleCase())
   End Sub
End Module
' The example displays the following output:
'       True
'       War and Peace
```

Verwenden Sie zum Kompilieren des Visual Basic-Codes folgenden Befehl:

```console
vbc example.vb /r:UtilityLib.dll
```

Zum Kompilieren mit C# ändern Sie den Namen des Compilers von vbc in csc und die Dateierweiterung von „.vb“ in „.cs“:

```console
csc example.cs /r:UtilityLib.dll
```
