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
ms.openlocfilehash: 4cea3c17de40a873d977223f36b6dcef4f2c2d78
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709139"
---
# <a name="operator-overloads"></a>Operatorüberladungen
Mit Operator Überladungen können Frameworktypen so angezeigt werden, als wären Sie integrierte Sprach primitive.  
  
 Obwohl es in manchen Situationen zulässig und nützlich ist, sollten Operator Überladungen vorsichtig verwendet werden. Es gibt viele Fälle, in denen das Überladen von Operatoren missbraucht wurde, z. b. wenn frameworkdesigner die Verwendung von Operatoren für Vorgänge gestartet haben, die einfache Methoden sein sollten. Die folgenden Richtlinien sollten Sie bei der Entscheidung unterstützen, wann und wie die Operator Überladung verwendet werden soll.  
  
 **X AVOID** definieren operatorüberladungen, außer in Typen, die z. B. primitive (integrierte) Typen können sollten.  
  
 **✓ CONSIDER** operatorüberladungen in einen Typ, der wie ein primitiver Typ denken sollten definieren.  
  
 Beispielsweise ist <xref:System.String?displayProperty=nameWithType> `operator==` und `operator!=` definiert.  
  
 **✓ DO** operatorüberladungen in Strukturen, die Zahlen darstellen definieren (z. B. <xref:System.Decimal?displayProperty=nameWithType>).  
  
 **X DO NOT** beim Definieren von operatorüberladungen nette sein.  
  
 Die Operator Überladung ist in Fällen nützlich, in denen es sofort offensichtlich ist, was das Ergebnis des Vorgangs sein wird. Beispielsweise ist es sinnvoll, eine <xref:System.DateTime> von einem anderen `DateTime` zu subtrahieren und eine <xref:System.TimeSpan>zu erhalten. Es ist jedoch nicht geeignet, den logischen Union-Operator für die Union zweier Datenbankabfragen zu verwenden oder den Shift-Operator zum Schreiben in einen Stream zu verwenden.  
  
 **X DO NOT** bieten überlädt, wenn mindestens einer der Operanden den Typ definieren die Überladung aufweist.  
  
 **✓ DO** Überladen von Operatoren symmetrisch.  
  
 Wenn Sie z. b. die `operator==`überladen, sollten Sie auch die `operator!=`überladen. Wenn Sie die `operator<`überladen, sollten Sie auch die `operator>`überladen usw.  
  
 **✓ CONSIDER** stellt Methoden bereit, mit dem Anzeigenamen, die entsprechen ab, zu jedem überladener Operator.  
  
 Viele Sprachen unterstützen das Überladen von Operatoren nicht. Aus diesem Grund wird empfohlen, dass Typen, die Operatoren überlasten, eine sekundäre Methode mit einem entsprechenden domänenspezifischen Namen enthalten, der entsprechende Funktionalität bereitstellt.  
  
 Die folgende Tabelle enthält eine Liste der Operatoren und der entsprechenden anzeigen amen der Methode.  
  
|C#Operator Symbol|Metadatenname|Geeigneter Name|  
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
  
### <a name="overloading-operator-"></a>Überladen des Operators = =  
 Das Überladen von `operator ==` ist recht kompliziert. Die Semantik des Operators muss mit mehreren anderen Membern kompatibel sein, z. b. <xref:System.Object.Equals%2A?displayProperty=nameWithType>.  
  
### <a name="conversion-operators"></a>Konvertierungsoperatoren  
 Konvertierungs Operatoren sind unäre Operatoren, die eine Konvertierung von einem Typ in einen anderen ermöglichen. Die Operatoren müssen als statische Member entweder für den Operanden oder den Rückgabetyp definiert werden. Es gibt zwei Typen von Konvertierungs Operatoren: implizit und explizit.  
  
 **X DO NOT** Geben Sie einen Konvertierungsoperator aus, wenn eine solche Konvertierung nicht eindeutig von den Endbenutzern erwartet wird.  
  
 **X DO NOT** Konvertierungsoperatoren außerhalb der Domäne des Typs definiert.  
  
 Beispielsweise sind <xref:System.Int32>, <xref:System.Double>und <xref:System.Decimal> alle numerischen Typen, während <xref:System.DateTime> nicht ist. Daher sollte kein Konvertierungs Operator vorhanden sein, um eine `Double(long)` in eine `DateTime`zu konvertieren. Ein Konstruktor wird in einem solchen Fall bevorzugt.  
  
 **X DO NOT** Geben Sie einen impliziten Konvertierungsoperator, wenn die Konvertierung potenziell lossy ist.  
  
 Beispielsweise sollte keine implizite Konvertierung von `Double` in `Int32` vorhanden sein, da `Double` über einen größeren Bereich als `Int32`verfügt. Ein expliziter Konvertierungs Operator kann auch dann bereitgestellt werden, wenn die Konvertierung potenziell Verlust Haft ist.  
  
 **X DO NOT** lösen Ausnahmen aus implizite Umwandlungen.  
  
 Es ist für Endbenutzer sehr schwierig, herauszufinden, was passiert, da Sie möglicherweise nicht erkennen, dass eine Konvertierung stattfindet.  
  
 **✓ DO** auslösen <xref:System.InvalidCastException?displayProperty=nameWithType> Wenn ein Aufruf an ein Cast-Operator eine verlustbehaftete Konvertierung führt und der Vertrag des Operators lossy Konvertierungen nicht zulässt.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
