---
title: 'Reservierte C#-Attribute: Conditional, Obsolete, AttributeUsage'
ms.date: 04/09/2020
description: Diese Attribute werden vom Compiler interpretiert und beeinflussen den vom Compiler generierten Code.
ms.openlocfilehash: c6d697dd08233ffc88900949998047137ee170a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/29/2020
ms.locfileid: "82021762"
---
# <a name="reserved-attributes-conditionalattribute-obsoleteattribute-attributeusageattribute"></a>Reservierte Attribute: ConditionalAttribute, ObsoleteAttribute, AttributeUsageAttribute

Diese Attribute können auf Elemente in Ihrem Code angewendet werden. Sie fügen diesen Elementen eine semantische Bedeutung hinzu. Der Compiler verwendet diese semantischen Bedeutungen, um seine Ausgabe zu ändern und mögliche Entwicklerfehler im Code zu melden.

## <a name="conditional-attribute"></a>`Conditional`-Attribut

Das `Conditional`-Attribut macht die Ausführung einer Methode abhängig von einem Vorverarbeitungsbezeichner. Das `Conditional`-Attribut ist ein Alias für <xref:System.Diagnostics.ConditionalAttribute> und kann auf eine Methode oder Attributklasse angewendet werden.

Im folgenden Beispiel wird `Conditional` auf eine Methode angewendet, um die Anzeige programmspezifischer Diagnoseinformationen zu aktivieren oder zu deaktivieren:

:::code language="csharp" source="snippets/trace.cs" interactive="try-dotnet" :::

Wenn der `TRACE_ON`-Bezeichner nicht definiert ist, wird die Ausgabe der Ablaufverfolgung nicht angezeigt. Untersuchen Sie den Code im interaktiven Fenster.

Das `Conditional`-Attribut wird oft zusammen mit dem `DEBUG`-Bezeichner verwendet, um die Ablaufverfolgung und Protokollierung für Debugbuilds – nicht jedoch in Releasebuilds – wie im folgenden Beispiel gezeigt zu aktivieren:

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditional" :::

Wenn eine als bedingt gekennzeichnete Methode aufgerufen wird, bestimmt das Vorhandensein oder Fehlen des angegebenen Vorverarbeitungssymbols, ob der Aufruf eingeschlossen oder ausgelassen wird. Wenn das Symbol definiert ist, wird der Aufruf einbezogen; andernfalls wird der Aufruf ausgelassen. Eine bedingte Methode muss eine Methode in einer Klassen- oder Strukturdeklaration sein und einen `void`-Rückgabetyp aufweisen. Die Verwendung von `Conditional` ist eine sauberere, elegantere und auch weniger fehleranfällige Alternative zum Einschließen von Methoden innerhalb von `#if…#endif`-Blöcken.

Wenn eine Methode mehrere `Conditional`-Attribute besitzt, wird ein Aufruf an die Methode eingeschlossen, wenn mindestens eines der bedingten Symbole definiert ist (die Symbole durch den OR-Operator logisch miteinander verknüpft sind). Im folgenden Beispiel führt das Vorhandensein von `A` oder `B` zu einem Methodenaufruf:

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetMultipleConditions" :::

### <a name="using-conditional-with-attribute-classes"></a>Verwenden von `Conditional` mit Attributklassen

Das `Conditional`-Attribut kann auch auf die Definition einer Attributklasse angewendet werden. Im folgenden Beispiel fügt das benutzerdefinierte Attribut `Documentation` den Metadaten nur dann Informationen hinzu, wenn `DEBUG` definiert ist.

:::code language="csharp" source="snippets/ConditionalExamples.cs" id="SnippetConditionalConditionalAttribute" :::

## <a name="obsolete-attribute"></a>`Obsolete`-Attribut

Das `Obsolete`-Attribut markiert ein Codeelement als nicht länger zur Verwendung empfohlen. Die Verwendung einer als veraltet markierten Entität führt zu einer Warnung oder einem Fehler. Das `Obsolete`-Attribut ist ein Attribut zur einmaligen Nutzung und kann auf jede Entität angewendet werden, die Attribute zulässt. `Obsolete` ist ein Alias für <xref:System.ObsoleteAttribute>.

Das folgende Beispiel zeigt, wie das `Obsolete`-Attribut auf die `A`-Klasse und die `B.OldMethod`-Methode angewendet wird. Da das zweite Argument des Attributkonstruktors, das auf `B.OldMethod` angewendet wurde, auf `true` festgelegt wird, verursacht diese Methode einen Compilerfehler. Die Verwendung der `A`-Klasse erzeugt hingegen nur eine Warnung. Wenn Sie `B.NewMethod` aufrufen, werden weder Warnungen noch Fehler erzeugt. Wenn Sie es mit den vorherigen Definitionen verwenden, generiert der folgende Code zwei Warnungen und einen Fehler:

:::code language="csharp" source="snippets/ObsoleteExample.cs" interactive="try-dotnet" :::

Die Zeichenfolge, die als erstes Argument für den Attributkonstruktor bereitgestellt wurde, wird als Teil der Warnung oder des Fehlers angezeigt. Es werden zwei Warnungen für die Klasse `A` generiert: eine für die Deklaration des Klassenverweises und eine für den Klassenkonstruktor. Das `Obsolete`-Attribut kann ohne Argumente verwendet werden. Es wird jedoch empfohlen, in einer Erläuterung anzugeben, was stattdessen verwendet werden soll.

## <a name="attributeusage-attribute"></a>`AttributeUsage`-Attribut

Das `AttributeUsage`-Attribut bestimmt, wie eine benutzerdefinierte Attributklasse verwendet werden kann. Bei <xref:System.AttributeUsageAttribute> handelt es sich um ein Attribut, das Sie auf benutzerdefinierte Attributdefinitionen anwenden. Mithilfe des `AttributeUsage`-Attribut können Sie Folgendes steuern:

- Auf welche Programmelemente das Attribut angewendet werden kann. Wenn Sie dessen Verwendung nicht einschränken, kann ein Attribut auf jedes der folgenden Programmelemente angewendet werden:
  - Assembly
  - module
  - Feld
  - event
  - Methode
  - Parameter
  - property
  - return
  - Typ
- Ob ein Attribut mehrfach auf ein einzelnes Programmelement angewendet werden kann.
- Ob Attribute von abgeleiteten Klassen geerbt werden.

Die Standardeinstellungen ähneln folgendem Beispiel, wenn Sie explizit angewendet werden:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageFirst" :::

In diesem Beispiel kann die `NewAttribute`-Klasse auf jedes unterstützte Programmelement angewendet werden. Es kann jedoch nur einmal auf jede Entität angewendet werden. Wenn das Attribut auf eine Basisklasse angewendet wird, wird es an eine abgeleitete Klasse vererbt.

Die Argumente <xref:System.AttributeUsageAttribute.AllowMultiple> und <xref:System.AttributeUsageAttribute.Inherited> sind optional, sodass folgender Code die gleiche Wirkung hat:

:::code language="csharp" source="snippets/NewAttribute.cs" id="SnippetUsageSecond" :::

Das erste <xref:System.AttributeUsageAttribute>-Argument muss mindestens ein Element der <xref:System.AttributeTargets>-Enumeration sein. Mehrere Zieltypen können wie im folgenden Beispiel dargestellt mithilfe des OR-Operators verknüpft werden:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetDefinePropertyAttribute" :::

Ab C# 7.3 können Attribut auf das Eigenschaften- oder das Unterstützungsfeld einer automatisch implementierten Eigenschaft angewendet werden. Das Attribut wird auf die Eigenschaft angewendet, sofern Sie den `field`-Bezeichner des Attributs nicht angeben. Beides wird im folgenden Beispiel veranschaulicht:

:::code language="csharp" source="snippets/NewPropertyOrFieldAttribute.cs" id="SnippetUsePropertyAttribute" :::

Wenn das <xref:System.AttributeUsageAttribute.AllowMultiple>-Argument auf `true` festgelegt ist, kann das daraus entstehende Attribut wie im folgenden Beispiel dargestellt mehr als einmal auf eine einzelne Entität angewendet werden:

:::code language="csharp" source="snippets/MultiUseAttribute.cs" id="SnippetMultiUse" :::

In diesem Fall kann `MultiUseAttribute` wiederholt angewendet werden, da `AllowMultiple` auf `true` festgelegt wurde. Beide gezeigten Formate für das Anwenden von mehreren Attributen sind gültig.

Wenn <xref:System.AttributeUsageAttribute.Inherited> auf `false` festgelegt wurde, wird das Attribut nicht von Klassen geerbt, die von einer Attributklasse abgeleitet werden. Zum Beispiel:

:::code language="csharp" source="snippets/NonInheritedAttribute.cs" id="SnippetNonInherited" :::

In diesem Fall wird `NonInheritedAttribute` nicht durch Vererbung auf `DClass` angewendet.

## <a name="see-also"></a>Siehe auch

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Attribute](../../../standard/attributes/index.md)
- [Reflexion](../../programming-guide/concepts/reflection.md)
