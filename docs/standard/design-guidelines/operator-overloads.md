---
title: Operatorüberladungen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
author: KrzysztofCwalina
ms.openlocfilehash: d1b9d8bc1f5f6f83a50dbd798894f94937320d2b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152135"
---
# <a name="operator-overloads"></a>Operatorüberladungen
Operatorüberladungen können angezeigt werden, als wären sie integrierte Sprachprimitive Framework-Typen.  
  
 Obwohl zulässig und in einigen Situationen nützlich, sollte die operatorüberladungen mit Vorsicht verwendet werden. Es gibt viele Fälle, die in der, die, die Operator überladen missbräuchlich verwendet wurde z. B. beim Start der Framework-Designer Verwendung Operatoren für Vorgänge, die einfache Methoden werden soll, ein. Die folgenden Richtlinien sollten Sie entscheiden, wann und wie Sie die Überladung von Operatoren verwenden können.  
  
 **X AVOID** definieren operatorüberladungen, außer in Typen, die z. B. primitive (integrierte) Typen können sollten.  
  
 **✓ CONSIDER** operatorüberladungen in einen Typ, der wie ein primitiver Typ denken sollten definieren.  
  
 Z. B. <xref:System.String?displayProperty=nameWithType> hat `operator==` und `operator!=` definiert.  
  
 **✓ DO** operatorüberladungen in Strukturen, die Zahlen darstellen definieren (z. B. <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X DO NOT** beim Definieren von operatorüberladungen nette sein.  
  
 Überladen des Operators ist hilfreich in Fällen, in denen es sofort offensichtlich wird das Ergebnis des Vorgangs. Beispielsweise ist es sinnvoll, eine subtrahieren können <xref:System.DateTime> von einem anderen `DateTime` und erhalten Sie eine <xref:System.TimeSpan>. Es ist jedoch nicht sinnvoll, logische union-Operators auf zwei-union-Datenbankabfragen verwenden oder mithilfe der UMSCHALT-Operator verwenden, um das Schreiben in einen Stream.  
  
 **X DO NOT** bieten überlädt, wenn mindestens einer der Operanden den Typ definieren die Überladung aufweist.  
  
 **✓ DO** Überladen von Operatoren symmetrisch.  
  
 Wenn Sie überladen, z. B. die `operator==`, überladen Sie auch die `operator!=`. Auf ähnliche Weise, wenn Sie überladen der `operator<`, überladen Sie auch die `operator>`und so weiter.  
  
 **✓ CONSIDER** stellt Methoden bereit, mit dem Anzeigenamen, die entsprechen ab, zu jedem überladener Operator.  
  
 Überladen von unterstützt vielen Sprachen nicht. Aus diesem Grund empfiehlt es sich, dass Typen, die Operatoren überladen eine zweite Methode mit einem entsprechenden domänenspezifischen Namen enthalten, die entsprechende Funktionalität bietet.  
  
 Die folgende Tabelle enthält eine Liste der Operatoren und die entsprechenden Anzeigenamen Methodennamen.  
  
|C#-Symbol "Operator"|Metadatennamen|Anzeigename|  
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
  
### <a name="overloading-operator-"></a>Überladen des ==  
 Überladen von `operator ==` ist ziemlich kompliziert. Die Semantik des Operators müssen als kompatibel mit mehrere andere Member, z. B. <xref:System.Object.Equals%2A?displayProperty=nameWithType>.  
  
### <a name="conversion-operators"></a>Konvertierungsoperatoren  
 Konvertierungsoperatoren sind unäre Operatoren, die Konvertierung von einem Typ in einen anderen zu ermöglichen. Die Operatoren müssen als statische Member auf den Operanden oder der Rückgabetyp definiert werden. Es gibt zwei Typen von Konvertierungsoperatoren: implizite und explizite.  
  
 **X DO NOT** Geben Sie einen Konvertierungsoperator aus, wenn eine solche Konvertierung nicht eindeutig von den Endbenutzern erwartet wird.  
  
 **X DO NOT** Konvertierungsoperatoren außerhalb der Domäne des Typs definiert.  
  
 Z. B. <xref:System.Int32>, <xref:System.Double>, und <xref:System.Decimal> alle numerische Typen sind, während <xref:System.DateTime> nicht. Daher dürfte kein Konvertierungsoperator zum Konvertieren einer `Double(long)` zu einem `DateTime`. Ein Konstruktor wird in diesem Fall bevorzugt.  
  
 **X DO NOT** Geben Sie einen impliziten Konvertierungsoperator, wenn die Konvertierung potenziell lossy ist.  
  
 Beispielsweise gibt es keine muss eine implizite Konvertierung von `Double` zu `Int32` da `Double` hat einen größeren Bereich als `Int32`. Ein expliziten Konvertierungsoperator kann angegeben werden, auch wenn die Konvertierung Datenverlust auftreten kann.  
  
 **X DO NOT** lösen Ausnahmen aus implizite Umwandlungen.  
  
 Es ist sehr schwierig für Endbenutzer zu verstehen, was passiert, da sie nicht bewusst sein könnten, dass eine Konvertierung stattfindet.  
  
 **✓ DO** auslösen <xref:System.InvalidCastException?displayProperty=nameWithType> Wenn ein Aufruf an ein Cast-Operator eine verlustbehaftete Konvertierung führt und der Vertrag des Operators lossy Konvertierungen nicht zulässt.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
