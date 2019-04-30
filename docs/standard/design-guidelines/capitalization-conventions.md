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
author: KrzysztofCwalina
ms.openlocfilehash: 9a4cf94ca7fcada7dfc0886422b373abc807a0fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966477"
---
# <a name="capitalization-conventions"></a>Konventionen für die Groß-/Kleinschreibung
Die Richtlinien in diesem Kapitel Layout, eine einfache Methode für die Verwendung von Fall, wenn stellen-IDs für Typen, Member und Parameter, die leicht lesbar konsistent angewendet.  
  
## <a name="capitalization-rules-for-identifiers"></a>Regeln der Groß-/Kleinschreibung für Bezeichner  
 Profitieren Sie um Wörter in einem Bezeichner zu unterscheiden, die den ersten Buchstaben jedes Worts in den Bezeichner. Verwenden Sie keine Unterstriche um Wörter zu unterscheiden oder einfach eine beliebige Stelle in Bezeichnern. Es gibt zwei geeignete Möglichkeiten, die Bezeichner, abhängig von der Verwendung des Bezeichners zu profitieren:  
  
- PascalCasing  
  
- camelCasing  
  
 Die PascalCasing-Konvention für alle Bezeichner, mit Ausnahme von Parameternamen, nutzt das erste Zeichen jedes Worts (einschließlich Akronyme über zwei Buchstaben), wie in den folgenden Beispielen gezeigt:  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 Ein besonderer Fall besteht für zwei Buchstaben bestehenden Akronyme, die in denen beiden Buchstaben in Großbuchstaben angegeben werden, wie in der folgenden Bezeichner dargestellt:  
  
 `IOStream`  
  
 Die CamelCasing-Konvention, die nur für Parameternamen verwendet nutzt das erste Zeichen jedes Worts mit Ausnahme des ersten Worts, wie in den folgenden Beispielen gezeigt. Wie das Beispiel auch zeigt, sind zwei Buchstaben bestehenden Akronyme, die einen Bezeichner in Kamel-Schreibweise beginnen Kleinbuchstaben.  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 **✓ DO** verwenden Sie PascalCasing für alle öffentlichen Member, Typnamen und Namespacenamen Namen aus mehreren Wörtern bestehen.  
  
 **✓ DO** CamelCasing für Parameternamen verwenden.  
  
 Die folgende Tabelle beschreibt die Regeln der Groß-/Kleinschreibung für verschiedene Arten von Bezeichnern.  
  
|ID|Schreibweise|Beispiel|  
|----------------|------------|-------------|  
|Namespace|Pascal-Schreibweise|`namespace System.Security { ... }`|  
|Typ|Pascal-Schreibweise|`public class StreamReader { ... }`|  
|Interface|Pascal-Schreibweise|`public interface IEnumerable { ... }`|  
|Methode|Pascal-Schreibweise|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|Eigenschaft|Pascal-Schreibweise|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|event|Pascal-Schreibweise|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|Feld|Pascal-Schreibweise|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|Enum-Wert|Pascal-Schreibweise|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|Parameter|Camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a>Profitieren Sie von einer zusammengesetzten Wörter und Begriffe  
 Die meisten zusammengesetzten Wörter werden als einzelne Wörter für Zwecke der Groß-/Kleinschreibung behandelt.  
  
 **X DO NOT** jedes Wort in so genannten geschlossener Form zusammengesetzte Wörter profitieren.  
  
 Hierbei handelt es sich um zusammengesetzte Wörter, die als einzelnes Wort, z. B. Endpunkt geschrieben. Behandeln Sie ein zusammengesetztes Wort in geschlossener Form als einzelnes Wort, für die Richtlinien zur Groß-und Kleinschreibung. Verwenden Sie einen aktuellen Wörterbuch, um zu bestimmen, ob ein zusammengesetztes Wort in geschlossene Form geschrieben ist.  
  
|Pascal-Schreibweise|Camel|Not|  
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
 Sprachen, die in der CLR ausgeführt werden können sind zur Unterstützung der Instanzenmethode, nicht erforderlich, obwohl einige führen. Auch wenn Ihre Sprache unterstützt wird, werden nicht anderen Sprachen, die Ihr Framework zugreifen können. Alle APIs, die extern zugegriffen werden kann, werden verlässlich nicht aus diesem Grund Fall allein, zur Unterscheidung zwischen zwei Namen im selben Kontext.  
  
 **X DO NOT** wird davon ausgegangen, dass alle Programmiersprachen die Groß-/Kleinschreibung beachtet werden. Das sind sie nicht. Namen dürfen sich nicht allein Groß-/Kleinschreibung unterscheiden.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
