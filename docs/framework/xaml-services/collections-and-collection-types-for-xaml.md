---
title: Auflistungen und Auflistungstypen für XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 63f6346837f77dbdbdcb4a90ec5af725be69ee02
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364334"
---
# <a name="collections-and-collection-types-for-xaml"></a>Auflistungen und Auflistungstypen für XAML

In diesem Thema wird beschrieben, wie Eigenschaften von Typen definiert werden, die zur Unterstützung einer Auflistung vorgesehen sind, und wie die XAML-Syntax zum Instanziieren von Auflistungs Elementen als untergeordnete Elemente eines übergeordneten Objekt Elements oder Eigenschafts Elements unterstützt wird.

## <a name="xaml-collection-concepts"></a>Konzepte der XAML-Sammlung

Konzeptionell muss jede Beziehung in XAML, in der mehrere untergeordnete Elemente innerhalb des Gültigkeits Bereichs eines XAML-Objekt Elements oder eines XAML-Eigenschafts Elements vorhanden sind, als Auflistung implementiert werden. Diese Auflistung muss einer bestimmten XAML-Eigenschaft des XAML-Typs zugeordnet werden, der in dieser Beziehung übergeordnet ist. Die-Eigenschaft muss eine Auflistung sein, da ein XAML-Prozessor erwartet, dass jedes Element im Markup als neu hinzugefügtes Element der Sicherungs Auflistungs Eigenschaft zugewiesen wird.

Auf der XAML-Sprachebene werden die genauen Anforderungen an die Unterstützung von Sammlungen nicht vollständig definiert. Das Konzept, dass eine Auflistung entweder eine Liste oder ein Wörterbuch (aber nicht beides) sein kann, wird auf der XAML-Sprachebene definiert, aber die Unterstützungs Typen, die entweder Listen oder Wörterbücher darstellen, werden nicht von der XAML-Sprache definiert.

In .NET Framework XAML-Diensten ist das Konzept der Unterstützung von XAML-Auflistungen klarer definiert in Bezug auf .NET Framework Unterstützungs Typen. Die XAML-Unterstützung für Auflistungen basiert insbesondere auf mehreren .NET Framework Konzepten und APIs, die für Listen und Wörterbücher in allgemeiner .NET Framework Programmierung verwendet werden.

1. Die <xref:System.Collections.IList> -Schnittstelle gibt eine Listen Auflistung an.

2. Die <xref:System.Collections.IDictionary> -Schnittstelle gibt eine Wörterbuch Auflistung an.

3. <xref:System.Array>stellt ein Array dar, und ein Array <xref:System.Collections.IList> unterstützt Methoden.

In jedem dieser Auflistungs Konzepte erwartet ein XAML-Prozessor für .NET Framework XAML-Dienste `Add` , dass die-Methode für eine bestimmte Instanz des Typs der Sammlungs Eigenschaft aufgerufen wird. In einem serialisierungsszenario erzeugt ein XAML-Prozessor diskrete XAML-Typinstanzen für jedes Element, das in der Liste, im Wörterbuch oder im Array auf der Grundlage des spezifischen "Items"-Konzepts der Auflistung gefunden wird. Diese sind: <xref:System.Collections.IList.Item%2A>; ; das explizite <xref:System.Array.System%23Collections%23IList%23Item%2A> für <xref:System.Array>. <xref:System.Collections.IDictionary.Item%2A>

## <a name="generic-collections"></a>Generische Auflistungen

Generische Auflistungen können für die allgemeine .NET Framework Programmierung nützlich sein und können auch für XAML-Auflistungs Eigenschaften verwendet werden. Allerdings werden die generischen <xref:System.Collections.Generic.IDictionary%602> Schnittstellen <xref:System.Collections.Generic.IList%601> und nicht durch .NET Framework XAML-Dienste von XAML-Prozessoren als Äquivalent zum nicht <xref:System.Collections.IList> generischen oder <xref:System.Collections.IDictionary>identifiziert. Anstatt die-Schnittstellen zu implementieren, empfiehlt es sich, für generische Auflistungs Eigenschafts Typen <xref:System.Collections.Generic.List%601> eine <xref:System.Collections.Generic.Dictionary%602>Ableitung von den-Klassen oder durchzuführen. Diese Klassen implementieren die nicht generischen Schnittstellen und enthalten daher die erwartete Unterstützung für XAML-Auflistungen in der Basis Implementierung.

## <a name="read-only-collections-and-initialization-logic"></a>Schreibgeschützte Auflistungen und Initialisierungs Logik

In .NET Framework Programmierung ist es ein gängiges Entwurfsmuster, jede Eigenschaft, die einen Wert einer Auflistung enthält, als schreibgeschützte Auflistung festzulegen. Dieses Muster ermöglicht es der-Instanz, die die-Auflistungs Eigenschaft besitzt, besser zu steuern, was mit der Auflistung geschieht. Das-Muster verhindert insbesondere das versehentliche ersetzen der gesamten bereits vorhandenen-Auflistung durch Festlegen der-Eigenschaft. In diesem Muster sollte der Zugriff auf die Auflistung durch Aufrufer stattdessen durch das Aufrufen von Methoden oder Eigenschaften erfolgen, die vom Sammlungstyp und/oder den relevanten Auflistungs Schnittstellen wie <xref:System.Collections.IList>unterstützt werden.

Die Verwendung dieses Musters impliziert, dass jede Klasse, die eine schreibgeschützte Auflistungs Eigenschaft verfügbar macht, diese Eigenschaft zuerst so initialisieren muss, dass Sie eine leere Auflistung enthält. In der Regel wird die Initialisierung im Rahmen des Konstruktions Verhaltens für die-Klasse ausgeführt. Um für XAML nützlich zu sein, ist es wichtig, dass auf diese Logik immer durch den Parameter losen Konstruktor verwiesen wird, da XAML in der Regel den Parameter losen Konstruktor aufruft, bevor die Eigenschaften verarbeitet werden (Auflistungs Eigenschaften oder anderweitig).

## <a name="xaml-type-system-support-and-collections"></a>XAML-typsystemunterstützung und-Auflistungen

Das XAML-Typsystem, das in .NET Framework XAML-Diensten implementiert ist, umfasst über die grundlegenden Mechanismen zum Durchlaufen von XAML und Auffüllen oder Serialisieren von Auflistungs Eigenschaften hinaus verschiedene Entwurfsfunktionen, die sich auf Auflistungen in XAML beziehen.

1. <xref:System.Xaml.XamlType.IsCollection%2A>gibt true zurück, wenn der XAML-Typ durch einen Typ gestützt wird, der XAML-Auflistungs Unterstützung bereitstellt.

2. <xref:System.Xaml.XamlType.IsDictionary%2A>und <xref:System.Xaml.XamlType.IsArray%2A> können den Auflistmodus, den der XAML-Typ unterstützt, genauer identifizieren. Bei benutzerdefinierten XAML-Prozessoren, die auf .NET Framework XAML-Diensten und dem XAML-Typsystem basieren, <xref:System.Xaml.XamlWriter> aber nicht auf vorhandenen Implementierungen basieren, kann es erforderlich sein, den verwendeten Auflistungs Modus zu ermitteln, um zu ermitteln, für welche Methode aufgerufen werden soll. Sammlungs Verarbeitung.

3. Jeder der vorherigen Eigenschaftswerte wird potenziell durch über schreibungen von <xref:System.Xaml.XamlType.LookupCollectionKind%2A> für einen XAML-Typ beeinflusst.
