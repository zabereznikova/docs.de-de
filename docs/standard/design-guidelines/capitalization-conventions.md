---
title: "Gro&#223;schreibung Konventionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Höckerschreibweise für Namen [.NET Framework]"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Großschreibung"
  - "Pascal-Schreibweise für Namen [.NET Framework]"
  - "Groß-/Kleinschreibung, Großschreibung Konventionen"
  - "[Namen [.NET Framework], Großschreibung"
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Gro&#223;schreibung Konventionen
Die Richtlinien in diesem Kapitel Layout, eine einfache Methode für die Verwendung von Fall, dass bei konsistent stellen\-IDs für Typen, Member und Parameter, die leicht zu lesen.  
  
## Regeln für Groß\-\/Kleinschreibung für Bezeichner  
 Um Wörter in einem Bezeichner zu unterscheiden, nutzen Sie den ersten Buchstaben jedes Worts im Bezeichner. Verwenden Sie keine Unterstriche zur Unterscheidung von Wörtern oder darum geht, eine beliebige Stelle im Bezeichner. Es gibt zwei entsprechende Weise Bezeichner, abhängig von der Verwendung des Bezeichners in Großbuchstaben umwandelt:  
  
-   PascalCasing  
  
-   camelCasing  
  
 Die PascalCasing\-Konvention für alle Bezeichner, abgesehen von Parameternamen, ist das erste Zeichen jedes Worts \(einschließlich Akronyme über zwei Buchstaben\), wie in den folgenden Beispielen gezeigt:  
  
 `PropertyDescriptor`   
 `HtmlTag`  
  
 Ein besonderer Fall besteht für zweibuchstabige Akronyme, in denen sowohl Buchstaben groß geschrieben werden, wie in der folgenden Bezeichner dargestellt:  
  
 `IOStream`  
  
 Der Konvention CamelCasing nur für Parameternamen verwendet nutzt das erste Zeichen jedes Worts mit Ausnahme der ersten Wort wie in den folgenden Beispielen gezeigt. Wie das Beispiel auch zeigt, sind zwei Buchstaben bestehende Akronyme, die einen Bezeichner in Kamel\-Schreibweise beginnen Kleinbuchstaben.  
  
 `propertyDescriptor`   
 `ioStream`   
 `htmlTag`  
  
 **✓ führen** verwenden Sie PascalCasing für alle öffentlichen Member, Typen und Namespaces aus mehreren Wörtern bestehen.  
  
 **✓ führen** CamelCasing für Parameternamen verwenden.  
  
 Die folgende Tabelle beschreibt die Regeln der Groß\-\/Kleinschreibung für unterschiedliche Typen von Bezeichnern.  
  
|ID|Schreibweise|Beispiel|  
|--------|------------------|--------------|  
|Namespace|Pascal\-Schreibweise|`namespace System.Security { ... }`|  
|Typ|Pascal\-Schreibweise|`public class StreamReader { ... }`|  
|Schnittstelle|Pascal\-Schreibweise|`public interface IEnumerable { ... }`|  
|Methode|Pascal\-Schreibweise|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|Eigenschaft|Pascal\-Schreibweise|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|Ereignis|Pascal\-Schreibweise|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|Feld|Pascal\-Schreibweise|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|Enum\-Wert|Pascal\-Schreibweise|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|Parameter|Camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## Zusammengesetzte Wörter Großschreibung und häufig verwendete Begriffe  
 Die meisten zusammengesetzten Wörter werden als einzelne Wörter für Zwecke der Groß\-\/Kleinschreibung behandelt.  
  
 **X nicht** Großbuchstaben jedes Worts im so genannten geschlossener Form zusammengesetzte Wörter.  
  
 Hierbei handelt es sich um zusammengesetzte Wörter, die als ein einzelnes Wort, wie z. B. Endpunkt geschrieben. Behandeln Sie ein zusammengesetztes Wort in geschlossener Form als einzelnes Wort, für die Richtlinien zur Groß\-und Kleinschreibung. Verwenden Sie eine aktuelle Wörterbuch, um zu bestimmen, ob ein zusammengesetztes Wort in geschlossener Form geschrieben ist.  
  
|Pascal\-Schreibweise|Camel|Not|  
|--------------------------|-----------|---------|  
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
  
## Groß\- und Kleinschreibung  
 Sprachen, die in der CLR ausgeführt werden können sind nicht erforderlich, um die Instanzenmethode, unterstützen, obwohl einige führen. Selbst wenn Ihre Sprache unterstützt wird, werden nicht anderen Sprachen, die Ihr Framework zugreifen können. Alle APIs, die extern zugegriffen werden kann nicht allein zu unterscheiden, zwei Namen im selben Kontext daher abhängig.  
  
 **X nicht** wird davon ausgegangen, dass alle Programmiersprachen die Groß\-\/Kleinschreibung. Sie sind nicht. Namen dürfen sich nicht allein Groß\-\/Kleinschreibung unterscheiden.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)