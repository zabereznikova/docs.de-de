---
title: "Operator&#252;berladungen | Microsoft Docs"
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
  - "Overloads-Operatoren [[.NET Framework]"
  - "[Namen [.NET Framework], überladene Operatoren"
  - "Entwurfsrichtlinien für Member, Operatoren"
  - "Überladene Operatoren"
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Operator&#252;berladungen
Framework\-Typen, die angezeigt werden, als wären es integrierte Sprachprimitive zulassen überladenen Operatoren  
  
 Jedoch zulässige und in manchen Situationen hilfreich, sollte mit Vorsicht überladenen Operatoren verwendet werden. Es gibt viele Fälle, in welcher, die, die Operator überladen missbräuchlich verwendet wurde z. B. beim Start die Framework\-Entwickler zur Verwendung von Operatoren für Vorgänge, die einfache Verfahren werden soll, ein. Die folgenden Richtlinien helfen Ihnen die Entscheidung, wann und wie Sie Operatoren überladen.  
  
 **X vermeiden** Definieren von überladenen Operatoren, außer in Typen, die \(integrierten\) Primitivtypen Meinung nach sollte.  
  
 **✓ ggf.** überladenen Operatoren in einen Typ, der funktioniert wie ein primitiver Typ definieren.  
  
 Zum Beispiel <xref:System.String?displayProperty=fullName> hat `operator==` und `operator!=` definiert.  
  
 **✓ führen** Definieren von überladenen Operatoren in Strukturen, die Zahlen darstellen \(z. B. <xref:System.Decimal?displayProperty=fullName>\).  
  
 **X nicht** nette sein, beim Definieren von überladenen Operatoren.  
  
 Operatoren überladen ist hilfreich in Fällen, in denen es sofort offensichtlich ist welcher das Ergebnis des Vorgangs verwendet werden. Beispielsweise ist es sinnvoll, eine subtrahieren können <xref:System.DateTime> von einem anderen `DateTime` und eine <xref:System.TimeSpan>. Es ist jedoch nicht sinnvoll, mit dem logischen union\-Operator auf Vereinigung zweier Datenbankabfragen oder mithilfe des Schiebeoperators in einen Stream geschrieben.  
  
 **X nicht** geben überlädt, wenn mindestens einer der Operanden vom Typ definieren die Überladung ist.  
  
 **✓ führen** Überladen von Operatoren symmetrisch.  
  
 Wenn Sie überladen, z. B. die `operator==`, überladen Sie auch die `operator!=`. Auf ähnliche Weise, wenn Sie überladen der `operator<`, überladen Sie auch die `operator>`, und so weiter.  
  
 **✓ ggf.** Methoden mit Anzeigenamen, die entsprechen, die jeweils den überladenen Operatoren bereitstellt.  
  
 Überladen von unterstützt vielen Sprachen nicht. Aus diesem Grund empfiehlt es sich, dass Typen, die Operatoren überladen, eine zweite Methode mit einem entsprechenden domänenspezifischen Namen enthalten, die entsprechende Funktionalität bietet.  
  
 Die folgende Tabelle enthält eine Liste von Operatoren und die entsprechenden Anzeigenamen Methodennamen.  
  
|C\#\-Operatorsymbol|Metadatenname|Angezeigter Name|  
|-------------------------|-------------------|----------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|`&#124;`|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|`&#124;&#124;`|`op_LogicalOr`|`Or`|  
|`=`|`op_Assign`|`Assign`|  
|`<<`|`op_LeftShift`|`LeftShift`|  
|`>>`|`op_RightShift`|`RightShift`|  
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|  
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|  
|`==`|`op_Equality`|`Equals`|  
|`!=`|`op_Inequality`|`Equals`|  
|`>`|`op_GreaterThan`|`CompareTo`|  
|`<`|`op_LessThan`|`CompareTo`|  
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|  
|`<=`|`op_LessThanOrEqual`|`CompareTo`|  
|`*=`|`op_MultiplicationAssignment`|`Multiply`|  
|`-=`|`op_SubtractionAssignment`|`Subtract`|  
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|  
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|  
|`%=`|`op_ModulusAssignment`|`Mod`|  
|`+=`|`op_AdditionAssignment`|`Add`|  
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|  
|`&#124;=`|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### Operator überladen \=\=  
 Überladen von `operator ==` ist ziemlich kompliziert. Die Semantik des Operators müssen für die Kompatibilität mit mehreren anderen Membern wie z. B. <xref:System.Object.Equals%2A?displayProperty=fullName>.  
  
### Konvertierungsoperatoren  
 Konvertierungsoperatoren sind unäre Operatoren, die Konvertierung von einem Typ in einen anderen zu ermöglichen. Die Operatoren müssen als statische Member des Operanden oder der Rückgabetyp definiert werden. Es gibt zwei Typen von Konvertierungsoperatoren: implizite und explizite.  
  
 **X nicht** Geben Sie einen Konvertierungsoperator, wenn eine solche Konvertierung nicht eindeutig von den Endbenutzern erwartet wird.  
  
 **X nicht** Konvertierungsoperatoren außerhalb der Domäne des Typs definiert.  
  
 Z. B. <xref:System.Int32>, <xref:System.Double>, und <xref:System.Decimal> sind alle numerische Typen, während <xref:System.DateTime> nicht. Daher dürfte kein Konvertierungsoperator konvertiert eine `Double(long)` auf eine `DateTime`. In diesem Fall wird ein Konstruktor bevorzugt.  
  
 **X nicht** Geben Sie einen impliziten Konvertierungsoperator, wenn die Konvertierung Datenverlust auftreten kann.  
  
 Beispielsweise gibt es keine muss eine implizite Konvertierung von `Double` zu `Int32` da `Double` hat einen größeren Bereich als `Int32`. Ein expliziter Konvertierungsoperator kann bereitgestellt werden, selbst wenn die Konvertierung Datenverlust auftreten kann.  
  
 **X nicht** lösen Ausnahmen aus impliziten Umwandlungen.  
  
 Es ist sehr schwierig für Endbenutzer zu verstehen, was geschieht, sie kennen möglicherweise nicht, dass eine Konvertierung stattfindet.  
  
 **✓ führen** auslösen <xref:System.InvalidCastException?displayProperty=fullName> Wenn ein Aufruf eines Umwandlungsoperators zu eine verlustbehaftete Konvertierung führt und der Vertrag des Operators Konvertierungen mit Datenverlust nicht zulässt.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)