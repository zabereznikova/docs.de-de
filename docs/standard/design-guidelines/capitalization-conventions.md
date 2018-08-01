---
title: Konventionen für die Groß-/Kleinschreibung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ef7913a2601c3a791cb028b4074ce37b9e9421b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575283"
---
# <a name="capitalization-conventions"></a>Konventionen für die Groß-/Kleinschreibung
Die Richtlinien in diesem Kapitel Layout, eine einfache Methode für die Verwendung von Fall, dass beim stellen-IDs für Typen, Member und Parameter, die leicht zu lesen konsistent angewendet.  
  
## <a name="capitalization-rules-for-identifiers"></a>Regeln für Groß-/Kleinschreibung für Bezeichner  
 Um Wörter in einem Bezeichner zu unterscheiden, profitieren Sie den ersten Buchstaben jedes Worts im Bezeichner. Verwenden Sie Unterstriche nicht zur Unterscheidung von Wörtern oder darum geht, eine beliebige Stelle in Bezeichnern. Es gibt zwei geeignete Möglichkeiten für die Großschreibung von Bezeichnern, abhängig von der Verwendung des Bezeichners ein:  
  
-   PascalCasing  
  
-   camelCasing  
  
 Die PascalCasing-Konvention für alle Bezeichner mit Ausnahme von Parameternamen, nutzt das erste Zeichen jedes Worts (einschließlich Akronyme über zwei Buchstaben), wie in den folgenden Beispielen gezeigt:  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 Ein besonderer Fall erfolgt für zwei Buchstaben bestehende Akronyme, die in denen beide Buchstaben groß geschrieben werden, wie in der folgende Bezeichner angezeigt:  
  
 `IOStream`  
  
 Die CamelCasing Konvention wird nur für Parameternamen, nutzt das erste Zeichen jedes Worts außer das erste Wort an, wie in den folgenden Beispielen gezeigt. Wie im Beispiel wird auch gezeigt, sind zwei Buchstaben bestehende Akronyme, die einen Bezeichner in Kamel-Schreibweise beginnen beide Kleinbuchstaben.  
  
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
  
## <a name="capitalizing-compound-words-and-common-terms"></a>Großschreibung zusammengesetzte Wörter und häufig verwendete Begriffe  
 Die meisten zusammengesetzten Wörter werden als einzelne Wörter für Zwecke der Groß-/Kleinschreibung behandelt.  
  
 **X DO NOT** jedes Wort in so genannten geschlossener Form zusammengesetzte Wörter profitieren.  
  
 Hierbei handelt es sich um zusammengesetzte Wörter, die als ein einzelnes Wort, wie z. B. Endpunkt geschrieben. Für die Richtlinien zur Groß-und Kleinschreibung behandeln Sie ein zusammengesetztes Wort in geschlossener Form als einzelnes Wort. Verwenden Sie eine aktuelle Wörterbuch, um zu bestimmen, ob ein zusammengesetztes Wort in geschlossener Form geschrieben wird.  
  
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
 Sprachen, die in der CLR ausgeführt werden können sind nicht erforderlich, um die Unterscheidung, zu unterstützen, obwohl Teils häufiger erledigen. Auch wenn Ihre Sprache unterstützt wird, nicht anderen Sprachen, die möglicherweise Ihr Framework zugegriffen wird. Keine APIs, die extern zugegriffen werden kann nicht auf Fall allein zu Unterschieden zwischen den zwei Namen in demselben Kontext aus diesem Grund verlassen.  
  
 **X DO NOT** wird davon ausgegangen, dass alle Programmiersprachen die Groß-/Kleinschreibung beachtet werden. Das sind sie nicht. Namen dürfen sich nicht nach Groß-/Kleinschreibung allein unterscheiden.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
