---
title: Konventionen für die Groß-/Kleinschreibung
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8af4a15e1e5b34c38b14c6b547cf44801bbf13e6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741762"
---
# <a name="capitalization-conventions"></a>Konventionen für die Groß-/Kleinschreibung
Die Richtlinien in diesem Kapitel stellen eine einfache Methode für den Fall dar, dass, wenn Sie konsistent angewendet wird, Bezeichner für Typen, Member und Parameter leicht lesbar werden.

## <a name="capitalization-rules-for-identifiers"></a>Regeln für die Groß Schreibung für Bezeichner
 Um Wörter in einem Bezeichner zu unterscheiden, sollten Sie den ersten Buchstaben jedes Worts im Bezeichner Großbuchstaben. Verwenden Sie keine Unterstriche zur Unterscheidung von Wörtern oder an einer beliebigen Stelle in bezeichlern. Es gibt zwei geeignete Möglichkeiten, Bezeichner in Abhängigkeit von der Verwendung des Bezeichners zu nutzen:

- Pascalschreibweise

- lowercamel

 Die pascalidentifier-Konvention, die für alle Bezeichner mit Ausnahme von Parameternamen verwendet wird, erschließt das erste Zeichen jedes Worts (einschließlich der Akronyme über zwei Buchstaben), wie in den folgenden Beispielen gezeigt:

 `PropertyDescriptor`
 `HtmlTag`

 Ein Sonderfall wird für aus zwei Buchstaben bestehende Akronyme gestellt, in denen beide Buchstaben groß geschrieben werden, wie im folgenden Bezeichner zu sehen:

 `IOStream`

 Die für Parameternamen verwendete Konvention für die Groß-/Kleinschreibung nutzt das erste Zeichen jedes Worts außer dem ersten Wort, wie in den folgenden Beispielen gezeigt. Wie das Beispiel zeigt, sind zwei Buchstaben Akronyme, die mit einem Kamel Schreib Bezeichner beginnen, in Kleinbuchstaben.

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 ✔️ für alle öffentlichen Member, Typen und Namespace Namen, die aus mehreren Wörtern bestehen, die Pass-/Schreibweise verwenden.

 ✔️ Verwenden Sie "CamelCase" für Parameternamen.

 In der folgenden Tabelle werden die Regeln für die Groß-und Kleinschreibung für verschiedene Bezeichner Typen beschrieben

|ID|He|Beispiel|
|----------------|------------|-------------|
|-Namespace|Pas|`namespace System.Security { ... }`|
|Typ|Pas|`public class StreamReader { ... }`|
|Benutzeroberfläche|Pas|`public interface IEnumerable { ... }`|
|-Methode|Pas|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|Die Eigenschaften-|Pas|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|Event|Pas|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|Field|Pas|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|Enumerationswert|Pas|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|Parameter|Erweist|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a>Groß Schreibung von zusammengesetzten Wörtern und allgemeinen Begriffen
 Die meisten zusammengesetzten Begriffe werden als einzelne Wörter für die Groß-/Kleinschreibung behandelt.

 ❌ dürfen nicht jedes Wort in so genannten zusammengesetzten Wörtern mit geschlossenen Formen Großbuchstaben.

 Dabei handelt es sich um zusammengesetzte Wörter, die als einzelnes Wort (z. b. Endpunkt) Um Richtlinien für die Groß-/Kleinschreibung zu beachten, behandeln Sie ein zusammengesetztes Wort als einzelnes Wort. Verwenden Sie ein Aktuelles Wörterbuch, um zu bestimmen, ob ein Verbund Wort in geschlossener Form geschrieben wurde.

|Pas|Erweist|not|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a>Groß- und Kleinschreibung
 Für Sprachen, die in der CLR ausgeführt werden können, ist es nicht erforderlich, die Groß-/Kleinschreibung zu unterstützen. Auch wenn Ihre Sprache Sie unterstützt, sind andere Sprachen, die möglicherweise auf Ihr Framework zugreifen, nicht. Alle APIs, die extern zugänglich sind, können sich daher nicht allein auf die Groß-/Kleinschreibung verlassen, um zwischen zwei Namen im gleichen Kontext zu unterscheiden.

 ❌ nicht davon ausgehen, dass bei allen Programmiersprachen die Groß-/Kleinschreibung beachtet wird Das sind sie nicht. Namen dürfen nicht allein durch die Groß-/Kleinschreibung abweichen

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
