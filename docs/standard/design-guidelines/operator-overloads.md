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
ms.openlocfilehash: 893b7d1f76dfb059a0ddca77dfd8654812e9ae12
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289732"
---
# <a name="operator-overloads"></a>Operatorüberladungen
Mit Operator Überladungen können Frameworktypen so angezeigt werden, als wären Sie integrierte Sprach primitive.

 Obwohl es in manchen Situationen zulässig und nützlich ist, sollten Operator Überladungen vorsichtig verwendet werden. Es gibt viele Fälle, in denen das Überladen von Operatoren missbraucht wurde, z. b. wenn frameworkdesigner die Verwendung von Operatoren für Vorgänge gestartet haben, die einfache Methoden sein sollten. Die folgenden Richtlinien sollten Sie bei der Entscheidung unterstützen, wann und wie die Operator Überladung verwendet werden soll.

 ❌Vermeiden Sie das Definieren von Operator Überladungen, außer in Typen, die sich wie primitive (integrierte) Typen fühlen sollten.

 ✔️ in Erwägung gezogen, Operator Überladungen in einem Typ zu definieren, der wie ein primitiver Typ aussehen sollte.

 Beispielsweise <xref:System.String?displayProperty=nameWithType> ist `operator==` und `operator!=` definiert.

 ✔️ definieren Operator Überladungen in Strukturen, die Zahlen darstellen (z. b <xref:System.Decimal?displayProperty=nameWithType> .).

 ❌Beim Definieren von Operator Überladungen sind Sie nicht nett.

 Die Operator Überladung ist in Fällen nützlich, in denen es sofort offensichtlich ist, was das Ergebnis des Vorgangs sein wird. Beispielsweise ist es sinnvoll, einen von einem anderen subtrahieren <xref:System.DateTime> `DateTime` und einen zu erhalten <xref:System.TimeSpan> . Es ist jedoch nicht geeignet, den logischen Union-Operator für die Union zweier Datenbankabfragen zu verwenden oder den Shift-Operator zum Schreiben in einen Stream zu verwenden.

 ❌Geben Sie keine Operator Überladungen an, es sei denn, mindestens einer der Operanden ist vom Typ, der die Überladung definiert.

 ✔️ Überladungs Operatoren auf symmetrische Weise.

 Wenn Sie z. b. überladen, `operator==` sollten Sie auch die überladen `operator!=` . Wenn Sie das überladen `operator<` , sollten Sie auch die überladen `operator>` , und so weiter.

 ✔️ sollten Sie Methoden mit anzeigen Amen bereitstellen, die den einzelnen überladenen Operatoren entsprechen.

 Viele Sprachen unterstützen das Überladen von Operatoren nicht. Aus diesem Grund wird empfohlen, dass Typen, die Operatoren überlasten, eine sekundäre Methode mit einem entsprechenden domänenspezifischen Namen enthalten, der entsprechende Funktionalität bereitstellt.

 Die folgende Tabelle enthält eine Liste der Operatoren und der entsprechenden anzeigen amen der Methode.

|C#-Operator (Symbol)|Metadatenname|Anzeigename|
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
 Das überladen `operator ==` ist recht kompliziert. Die Semantik des Operators muss mit mehreren anderen Membern kompatibel sein, z. b <xref:System.Object.Equals%2A?displayProperty=nameWithType> ..

### <a name="conversion-operators"></a>Konvertierungsoperatoren
 Konvertierungs Operatoren sind unäre Operatoren, die eine Konvertierung von einem Typ in einen anderen ermöglichen. Die Operatoren müssen als statische Member entweder für den Operanden oder den Rückgabetyp definiert werden. Es gibt zwei Typen von Konvertierungs Operatoren: implizit und explizit.

 ❌Geben Sie keinen Konvertierungs Operator an, wenn eine solche Konvertierung von den Endbenutzern nicht eindeutig erwartet wird.

 ❌Definieren Sie keine Konvertierungs Operatoren außerhalb der Domäne eines Typs.

 Beispielsweise <xref:System.Int32> sind, <xref:System.Double> und <xref:System.Decimal> alle numerischen Typen, während <xref:System.DateTime> nicht ist. Daher sollte kein Konvertierungs Operator vorhanden sein, um eine `Double(long)` in eine zu konvertieren `DateTime` . Ein Konstruktor wird in einem solchen Fall bevorzugt.

 ❌Geben Sie keinen impliziten Konvertierungs Operator an, wenn die Konvertierung potenziell Verlust Haft ist.

 Beispielsweise sollte keine implizite Konvertierung von in vorhanden sein, `Double` `Int32` da `Double` über einen größeren Bereich als verfügt `Int32` . Ein expliziter Konvertierungs Operator kann auch dann bereitgestellt werden, wenn die Konvertierung potenziell Verlust Haft ist.

 ❌Lösen Sie keine Ausnahmen von impliziten Umwandlungen aus.

 Es ist für Endbenutzer sehr schwierig, herauszufinden, was passiert, da Sie möglicherweise nicht erkennen, dass eine Konvertierung stattfindet.

 ✔️ lösen Sie <xref:System.InvalidCastException?displayProperty=nameWithType> aus, wenn ein Cast Operator eine verlustfreie Konvertierung auslöst und der Vertrag des Operators keine verlustfreien Konvertierungen zulässt.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfs Richtlinien für Member](member.md)
- [Framework-Entwurfs Richtlinien](index.md)
