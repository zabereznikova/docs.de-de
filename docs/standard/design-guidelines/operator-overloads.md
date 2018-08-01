---
title: Operatorüberladungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 747fc21aceae60e362c72391ae265e45d6f8445f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579307"
---
# <a name="operator-overloads"></a>Operatorüberladungen
Framework-Typen, die angezeigt werden, als wären sie integrierte Sprachprimitive zulassen operatorüberladungen  
  
 Obwohl zulässige als auch in einigen Situationen nützlich, sollte mit Vorsicht operatorüberladungen verwendet werden. Es gibt viele Fälle, in welcher, die, die Operator überladen missbräuchlich verwendet wurde z. B. beim Start die Framework-Entwickler von Operatoren für Vorgänge, die einfache Methoden werden sollen, aus. Die folgenden Richtlinien sollten Sie entscheiden, wann und wie mit operatorüberladung helfen.  
  
 **X AVOID** definieren operatorüberladungen, außer in Typen, die z. B. primitive (integrierte) Typen können sollten.  
  
 **✓ CONSIDER** operatorüberladungen in einen Typ, der wie ein primitiver Typ denken sollten definieren.  
  
 Beispielsweise <xref:System.String?displayProperty=nameWithType> hat `operator==` und `operator!=` definiert.  
  
 **✓ DO** operatorüberladungen in Strukturen, die Zahlen darstellen definieren (z. B. <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X DO NOT** beim Definieren von operatorüberladungen nette sein.  
  
 Operatoren überladen ist hilfreich in Fällen, in denen es sofort offensichtlich ist wie das Ergebnis des Vorgangs werden. Beispielsweise ist es sinnvoll, eine subtrahieren können <xref:System.DateTime> von einem anderen `DateTime` und erhalten einen <xref:System.TimeSpan>. Allerdings ist es nicht sinnvoll, zum Verwenden des logischen union-Operators auf zwei-union-Datenbankabfragen oder mithilfe des Schiebeoperators in einen Stream schreiben.  
  
 **X DO NOT** bieten überlädt, wenn mindestens einer der Operanden den Typ definieren die Überladung aufweist.  
  
 **✓ DO** Überladen von Operatoren symmetrisch.  
  
 Wenn Sie überladen z. B. die `operator==`, überladen Sie auch die `operator!=`. Auf ähnliche Weise, wenn Sie überladen der `operator<`, überladen Sie auch die `operator>`und so weiter.  
  
 **✓ CONSIDER** stellt Methoden bereit, mit dem Anzeigenamen, die entsprechen ab, zu jedem überladener Operator.  
  
 Überladen von unterstützt zahlreichen Sprachen nicht. Aus diesem Grund wird empfohlen, dass Typen, die Operatoren überladen eine zweite Methode mit einem entsprechenden domänenspezifischen Namen enthalten, die entsprechende Funktionalität bietet.  
  
 Die folgende Tabelle enthält eine Liste von Operatoren und die entsprechenden Anzeigenamen Methodennamen.  
  
|C#-Symbol "Operator"|Metadatenname|Anzeigename|  
|-------------------------|-------------------|-------------------|  
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|  
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|  
|`+ (binary)`|`op_Addition`|`Add`|  
|`- (binary)`|`op_Subtraction`|`Subtract`|  
|`* (binary)`|`op_Multiply`|`Multiply`|  
|`/`|`op_Division`|`Divide`|  
|`%`|`op_Modulus`|`Mod or Remainder`|  
|`^`|`op_ExclusiveOr`|`Xor`|  
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|  
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|  
|`&&`|`op_LogicalAnd`|`And`|  
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|  
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
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|  
|`,`|`op_Comma`|`Comma`|  
|`/=`|`op_DivisionAssignment`|`Divide`|  
|`--`|`op_Decrement`|`Decrement`|  
|`++`|`op_Increment`|`Increment`|  
|`- (unary)`|`op_UnaryNegation`|`Negate`|  
|`+ (unary)`|`op_UnaryPlus`|`Plus`|  
|`~`|`op_OnesComplement`|`OnesComplement`|  
  
### <a name="overloading-operator-"></a>Operator überladen ==  
 Überladen von `operator ==` ist ziemlich kompliziert. Die Semantik des Operators müssen für die Kompatibilität mit mehreren anderen Mitgliedern, wie z. B. <xref:System.Object.Equals%2A?displayProperty=nameWithType>.  
  
### <a name="conversion-operators"></a>Konvertierungsoperatoren  
 Konvertierungsoperatoren sind unäre Operatoren, die Konvertierung von einem Typ in einen anderen zu ermöglichen. Die Operatoren müssen als statische Member der Operanden oder der Rückgabetyp definiert werden. Es gibt zwei Arten von Konvertierungsoperatoren: implizite und explizite.  
  
 **X DO NOT** Geben Sie einen Konvertierungsoperator aus, wenn eine solche Konvertierung nicht eindeutig von den Endbenutzern erwartet wird.  
  
 **X DO NOT** Konvertierungsoperatoren außerhalb der Domäne des Typs definiert.  
  
 Beispielsweise <xref:System.Int32>, <xref:System.Double>, und <xref:System.Decimal> alle numerische Typen sind, während <xref:System.DateTime> nicht. Daher es darf keine Konvertierungsoperator konvertiert eine `Double(long)` auf eine `DateTime`. In diesem Fall wird ein Konstruktor bevorzugt.  
  
 **X DO NOT** Geben Sie einen impliziten Konvertierungsoperator, wenn die Konvertierung potenziell lossy ist.  
  
 Beispielsweise gibt es keine muss eine implizite Konvertierung von `Double` auf `Int32` da `Double` hat einen größeren Bereich als `Int32`. Ein expliziten Konvertierungsoperators kann bereitgestellt werden, selbst wenn die Konvertierung potenziell lossy ist.  
  
 **X DO NOT** lösen Ausnahmen aus implizite Umwandlungen.  
  
 Es ist sehr schwierig für Endbenutzer, um zu verstehen, was geschieht, da sie nicht bekannt sein könnten, dass eine Konvertierung stattfindet.  
  
 **✓ DO** auslösen <xref:System.InvalidCastException?displayProperty=nameWithType> Wenn ein Aufruf an ein Cast-Operator eine verlustbehaftete Konvertierung führt und der Vertrag des Operators lossy Konvertierungen nicht zulässt.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
