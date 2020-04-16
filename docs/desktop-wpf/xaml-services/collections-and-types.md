---
title: Auflistungen und Auflistungstypen für XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 2ec58026c605df31489c8aab4c4cc714dab11474
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "81432581"
---
# <a name="collections-and-collection-types-for-xaml"></a>Auflistungen und Auflistungstypen für XAML

In diesem Artikel wird beschrieben, wie Eigenschaften von Typen definiert werden, die eine Auflistung unterstützen sollen, und wie die XAML-Syntax zum Instanziieren von Auflistungselementen als elementuntergeordneteElemente eines übergeordneten Objektelements oder Eigenschaftselements unterstützt wird.

## <a name="xaml-collection-concepts"></a>XAML-Auflistungskonzepte

Im Prinzip muss jede Beziehung in XAML, in der sich mehrere untergeordnete Elemente im Bereich eines XAML-Objektelements oder XAML-Eigenschaftselements befinden, als Auflistung implementiert werden. Diese Auflistung muss einer bestimmten XAML-Eigenschaft des XAML-Typs zugeordnet sein, der das übergeordnete Element in dieser Beziehung ist. Die Eigenschaft muss eine Auflistung sein, da ein XAML-Prozessor erwartet, dass jedes Element in Markup als neu hinzugefügtes Element der Backing Collection-Eigenschaft zugewiesen wird.

Auf der XAML-Sprachebene sind die genauen Anforderungen an die Sammlungsunterstützung nicht vollständig definiert. Das Konzept, dass eine Auflistung entweder eine Liste oder ein Wörterbuch (aber nicht beides) sein kann, wird auf XAML-Sprachebene definiert, aber welche Sicherungstypen entweder Listen oder Wörterbücher darstellen, wird nicht durch die XAML-Sprache definiert.

In .NET XAML Services ist das Konzept der XAML-Auflistungsunterstützung in Bezug auf .NET-Sicherungstypen klarer definiert. Insbesondere basiert die XAML-Unterstützung für Sammlungen auf mehreren .NET-Konzepten und APIs, die für Listen und Wörterbücher in der allgemeinen .NET-Programmierung verwendet werden.

1. Die <xref:System.Collections.IList> Schnittstelle gibt eine Listenauflistung an.

2. Die <xref:System.Collections.IDictionary> Schnittstelle gibt eine Wörterbuchsammlung an.

3. <xref:System.Array>stellt ein Array dar, <xref:System.Collections.IList> und ein Array unterstützt Methoden.

In jedem dieser Auflistungskonzepte erwartet ein .NET XAML Services `Add` XAML-Prozessor, dass die Methode für eine bestimmte Instanz des Auflistungseigenschaftstyps aufruft. Oder in einem Serialisierungsszenario erstellt ein XAML-Prozessor diskrete XAML-Typinstanzen für jedes Element, das in der Liste, im Wörterbuch oder im Array gefunden wird, basierend auf dem spezifischen Konzept der einzelnen "Elemente" jeder Auflistung. Diese Punkte <xref:System.Collections.IList.Item%2A?displayProperty=nameWithType>sind: ; <xref:System.Collections.IDictionary.Item%2A?displayProperty=nameWithType>; die <xref:System.Array.System%23Collections%23IList%23Item%2A?displayProperty=nameWithType> explizite für <xref:System.Array>.

## <a name="generic-collections"></a>Generische Sammlungen

Generische Auflistungen können für die allgemeine .NET-Programmierung nützlich sein und auch für XAML-Auflistungseigenschaften verwendet werden. Die generischen Schnittstellen <xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IDictionary%602> und werden jedoch nicht von .NET XAML Services XAML-Prozessoren als äquivalent zu den nicht generischen <xref:System.Collections.IList> oder <xref:System.Collections.IDictionary>. Anstatt die Schnittstellen zu implementieren, wird ein empfohlener Ansatz für <xref:System.Collections.Generic.List%601> generische <xref:System.Collections.Generic.Dictionary%602>Auflistungseigenschaftstypen von den Klassen oder ableiten. Diese Klassen implementieren die nicht generischen Schnittstellen und enthalten daher die erwartete Unterstützung für XAML-Auflistungen in der Basisimplementierung.

## <a name="read-only-collections-and-initialization-logic"></a>Read-Only Collections und Initialisierungslogik

In der .NET-Programmierung ist es ein allgemeines Entwurfsmuster, jede Eigenschaft, die einen Wert einer Auflistung enthält, als schreibgeschützte Auflistung zu erstellen. Dieses Muster ermöglicht es der Instanz, die Eigentümerin der Auflistungseigenschaft ist, besser zu steuern, was mit der Auflistung geschieht. Insbesondere verhindert das Muster den versehentlichen Austausch der gesamten bereits vorhandenen Auflistung durch Festlegen der Eigenschaft. In diesem Muster sollte jeder Zugriff von Aufrufern auf die Auflistung stattdessen durch Aufrufen von Methoden oder Eigenschaften <xref:System.Collections.IList>erfolgen, die vom Auflistungstyp und/oder den entsprechenden Auflistungsschnittstellen wie unterstützt werden.

Die Verwendung dieses Musters impliziert, dass jede Klasse, die eine schreibgeschützte Auflistungseigenschaft verfügbar macht, diese Eigenschaft zuerst initialisieren muss, um eine leere Auflistung zu enthalten. In der Regel wird die Initialisierung als Teil des Konstruktionsverhaltens für die Klasse durchgeführt. Um für XAML nützlich zu sein, ist es wichtig, dass auf diese Logik immer vom parameterlosen Konstruktor verwiesen wird, da XAML im Allgemeinen den parameterlosen Konstruktor aufruft, bevor die Eigenschaften verarbeitet werden (Auflistungseigenschaften oder auf andere Weise).

## <a name="xaml-type-system-support-and-collections"></a>XAML-Typsystemunterstützung und -sammlungen

Neben der grundlegenden Mechanik des Analysierens von XAML und des Auffüllens oder Serialisierens von Auflistungseigenschaften enthält das XAML-Typsystem, wie es in .NET XAML Services implementiert ist, mehrere Entwurfsfeatures, die sich auf Sammlungen in XAML beziehen.

1. <xref:System.Xaml.XamlType.IsCollection%2A>gibt true zurück, wenn der XAML-Typ von einem Typ unterstützt wird, der XAML-Auflistungsunterstützung bereitstellt.

2. <xref:System.Xaml.XamlType.IsDictionary%2A>und <xref:System.Xaml.XamlType.IsArray%2A> kann weiter identifizieren, welchen Erfassungsmodus der XAML-Typ unterstützt. Für benutzerdefinierte XAML-Prozessoren, die auf .NET XAML-Diensten und dem <xref:System.Xaml.XamlWriter> XAML-Typsystem basieren, aber nicht auf vorhandenen Implementierungen basieren, ist möglicherweise zu wissen, welcher Erfassungsmodus verwendet wird, um zu wissen, welche Methode für die Sammlungsverarbeitung aufgerufen werden soll.

3. Jeder der vorherigen Eigenschaftswerte wird möglicherweise <xref:System.Xaml.XamlType.LookupCollectionKind%2A> durch Überschreibungen eines XAML-Typs beeinflusst.
