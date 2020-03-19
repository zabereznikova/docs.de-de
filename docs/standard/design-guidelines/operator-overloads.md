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
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401220"
---
# <a name="operator-overloads"></a>Operatorüberladungen
Überladungen von Operatoren ermöglichen es Frameworktypen, so zu wie integrierte Sprachprimitive zu erscheinen.

 Obwohl es in einigen Situationen zulässig und nützlich ist, sollten Operatorüberladungen vorsichtig verwendet werden. Es gibt viele Fälle, in denen die Überladung von Operatoren missbraucht wurde, z. B. wenn Frameworkdesigner begannen, Operatoren für Vorgänge zu verwenden, die einfache Methoden sein sollten. Die folgenden Richtlinien sollten Ihnen bei der Entscheidung helfen, wann und wie Operatorüberlastung verwendet werden soll.

 ❌AVOID definiert Operatorüberladungen, außer in Typen, die sich wie primitive (integrierte) Typen anfühlen sollten.

 ✔️ CONSIDER definieren Operatorüberladungen in einem Typ, der sich wie ein primitiver Typ anfühlen sollte.

 Zum Beispiel <xref:System.String?displayProperty=nameWithType> `operator==` hat `operator!=` und definiert.

 ✔️ DO definieren Operatorüberladungen in Strukturen, <xref:System.Decimal?displayProperty=nameWithType>die Zahlen darstellen (z. B. ).

 ❌Seien Sie NICHT niedlich, wenn Operator-Überlastungen definiert werden.

 Eine Überladung des Bedieners ist in Fällen nützlich, in denen sofort klar ist, was das Ergebnis des Vorgangs sein wird. Es ist z. B. sinnvoll, <xref:System.DateTime> eine `DateTime` von der <xref:System.TimeSpan>anderen subtrahieren zu können und eine zu erhalten. Es ist jedoch nicht sinnvoll, den logischen Union-Operator zu verwenden, um zwei Datenbankabfragen zu vereinigen, oder den Schichtoperator zum Schreiben in einen Stream zu verwenden.

 ❌Stellen Sie KEINE Operatorüberladungen bereit, es sei denn, mindestens einer der Operanden ist vom Typ, der die Überladung definiert.

 ✔️ DO-Überlastoperatoren in symmetrischer Weise.

 Wenn Sie z. B. die `operator==`überladen, `operator!=`sollten Sie auch die überladen. Wenn Sie die `operator<`überladen, sollten Sie `operator>`auch die überladen usw.

 ✔️ CONSIDER, methoden mit Anzeigenamen bereitzustellen, die jedem überlasteten Operator entsprechen.

 Viele Sprachen unterstützen keine Operatorüberlastung. Aus diesem Grund wird empfohlen, dass Typen, die Überlastoperatoren enthalten, eine sekundäre Methode mit einem entsprechenden domänenspezifischen Namen enthalten, der eine gleichwertige Funktionalität bereitstellt.

 Die folgende Tabelle enthält eine Liste der Operatoren und die entsprechenden Anzeigemethodennamen.

|Operatorsymbol für die C-Operator|Metadatenname|Anzeigename|
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

### <a name="overloading-operator-"></a>Überladen des Operators ==
 Überlastung `operator ==` ist ziemlich kompliziert. Die Semantik des Operators muss mit mehreren anderen <xref:System.Object.Equals%2A?displayProperty=nameWithType>Elementen kompatibel sein, z. B. .

### <a name="conversion-operators"></a>Konvertierungsoperatoren
 Konvertierungsoperatoren sind unäre Operatoren, die die Konvertierung von einem Typ in einen anderen ermöglichen. Die Operatoren müssen als statische Elemente entweder im Operanden oder im Rückgabetyp definiert werden. Es gibt zwei Arten von Konvertierungsoperatoren: implizit und explizit.

 ❌Stellen Sie KEINEN Konvertierungsoperator bereit, wenn eine solche Konvertierung von den Endbenutzern nicht eindeutig erwartet wird.

 ❌Definieren Sie NICHT Konvertierungsoperatoren außerhalb der Domäne eines Typs.

 Beispiel: <xref:System.Int32>, <xref:System.Double>und <xref:System.Decimal> sind alle numerischen Typen, während <xref:System.DateTime> dies nicht der Fall ist. Daher sollte es keinen Konvertierungsoperator `Double(long)` geben, um eine in eine `DateTime`zu konvertieren. In einem solchen Fall wird ein Konstruktor bevorzugt.

 ❌Stellen Sie NICHT einen impliziten Konvertierungsoperator bereit, wenn die Konvertierung potenziell verlustbehaftet ist.

 Beispielsweise sollte es keine implizite `Double` Konvertierung `Int32` `Double` von in geben, da sie einen größeren Bereich als `Int32`hat. Ein expliziter Konvertierungsoperator kann auch dann bereitgestellt werden, wenn die Konvertierung potenziell verlustbehaftet ist.

 ❌Nicht Ausnahmen von impliziten Umwandlungen auslösen.

 Es ist sehr schwierig für Endbenutzer zu verstehen, was passiert, weil sie möglicherweise nicht wissen, dass eine Konvertierung stattfindet.

 ✔️ do <xref:System.InvalidCastException?displayProperty=nameWithType> werfen, wenn ein Anruf bei einem Gussoperator zu einer verlustbehafteten Umwandlung führt und der Vertrag des Operators keine verlustbehafteten Umwandlungen zulässt.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Framework Design-Richtlinien](../../../docs/standard/design-guidelines/index.md)
