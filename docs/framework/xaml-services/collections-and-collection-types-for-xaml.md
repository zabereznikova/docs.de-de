---
title: Auflistungen und Auflistungstypen für XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 4123b64545f7c47a96c4cae496046a89b7e576b0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494622"
---
# <a name="collections-and-collection-types-for-xaml"></a>Auflistungen und Auflistungstypen für XAML

Dieses Thema beschreibt, wie Sie Eigenschaften von Typen zu definieren, die zur Unterstützung von einer Sammlung und die XAML-Syntax zu unterstützen, für die Instanziierung der sammelhäufigkeit (Sek) als untergeordnete Elemente eines übergeordneten Object-Element oder die Property-Element vorgesehen sind.

## <a name="xaml-collection-concepts"></a>Konzepte der XAML-Auflistung

Vom Konzept her einer Beziehung in XAML, in denen es sind mehrere untergeordnete Elemente innerhalb des Bereichs von einem XAML-Objektelement oder XAML-Property-Element muss als eine Auflistung implementiert werden. Diese Sammlung muss eine bestimmte XAML-Eigenschaft, der den XAML-Typ zugeordnet sein, die das übergeordnete Element in dieser Beziehung ist. Die Eigenschaft muss eine Auflistung sein, da ein XAML-Prozessor erwartet, dass jedes Element im Markup für ein neu hinzugefügtes Element der Auflistungseigenschaft sichern werden zugewiesen.

Auf der XAML-Sprachebene sind die genauen Anforderungen von auflistungsunterstützung nicht vollständig definiert. Das Konzept, dass eine Auflistung kann entweder eine Liste oder ein Wörterbuch (aber nicht beide) wird definiert, auf der XAML-Sprachebene, aber die unterstützenden Typen darstellen, entweder Listen oder Wörterbücher ist nicht von der XAML-Sprache definiert.

In .NET Framework-XAML-Dienste wird das Konzept der Unterstützung von XAML in Bezug auf .NET Framework Unterstützungstypen genauer definiert. Insbesondere basiert die XAML-Unterstützung für Sammlungen verschiedene Konzepte von .NET Framework und APIs, die für Listen und Wörterbücher im Allgemeinen .NET Framework-Programmierung verwendet werden.

1. Die <xref:System.Collections.IList> -Schnittstelle gibt eine listenauflistung an.

2. Die <xref:System.Collections.IDictionary> Schnittstelle gibt ein Dictionary-Auflistung an.

3. <xref:System.Array> Stellt ein Array und einem Array unterstützt <xref:System.Collections.IList> Methoden.

In jedem dieser Konzepte Sammlung, ein .NET Framework XAML Services XAML-Prozessor erwartet, dass zum Aufrufen der `Add` Methode für eine bestimmte Instanz der den Typ der Auflistungseigenschaft. Alternativ dazu können Sie in einem Szenario mit Serialisierung erzeugt ein XAML-Prozessor diskrete XAML-Typ-Instanzen für jedes Element in der Liste, Wörterbuch oder Array basierend auf bestimmten Konzept jede Sammlung "Items" wurde gefunden. Hierbei handelt es sich: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; die explizite <xref:System.Array.System%23Collections%23IList%23Item%2A> für <xref:System.Array>.

## <a name="generic-collections"></a>Generische Auflistungen

Generische Auflistungen für allgemeine .NET Framework-Programmierung nützlich sein können, und können auch für XAML-Auflistung – Eigenschaften verwendet werden. Die generische jedoch Schnittstellen <xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602> von .NET Framework XAML Services XAML-Prozessoren als äquivalent zu nicht generischen nicht erkannt <xref:System.Collections.IList> oder <xref:System.Collections.IDictionary>. Statt die Schnittstellen zu implementieren, ist eine empfohlene Vorgehensweise für generische Auflistungstypen-Eigenschaft, die von den Klassen abgeleitet werden <xref:System.Collections.Generic.List%601> oder <xref:System.Collections.Generic.Dictionary%602>. Diese Klassen, die nicht generische Schnittstellen implementieren und sind daher die erwartete Unterstützung für XAML-Auflistungen in der basisimplementierung.

## <a name="read-only-collections-and-initialization-logic"></a>Nur-Lese Sammlungen und Initialisierungslogik

In .NET Framework-Programmierung ist es ein gängiges Entwurfsmuster, um eine beliebige Eigenschaft zu erstellen, die einen Wert aus einer Sammlung als schreibgeschützte Auflistung enthält. Dieses Muster ermöglicht die Instanz, die die Auflistungseigenschaft eine bessere Steuerung besitzt, was mit der Auflistung geschieht... Insbesondere wird verhindert, dass das Muster versehentlichen Ersatz für die gesamte vorhandene Auflistung durch Festlegen der Eigenschaft. In diesem Muster werden alle Zugriff auf die Auflistung von Aufrufern stattdessen gemacht werden sollen durch Aufrufen von Methoden oder Eigenschaften, wie z. B. durch den Auflistungstyp und/oder der relevanten Sammlungsschnittstellen unterstützt <xref:System.Collections.IList>.

Mit diesem Muster bedeutet, dass jede Klasse, die eine schreibgeschützte Auflistung-Eigenschaft verfügbar macht zuerst diese Eigenschaft enthält eine leere Auflistung initialisieren muss. Die Initialisierung wird in der Regel als Teil der Konstruktionsverhalten der Klasse ausgeführt. Um für XAML nützlich sein, es ist wichtig, dass solche Logik immer durch den Standardkonstruktor, verwiesen wird da XAML in der Regel vor dem Verarbeiten der Eigenschaften der Standard-Konstruktor aufruft (Eigenschaften der Sammlung oder auf andere Weise).

## <a name="xaml-type-system-support-and-collections"></a>Systemunterstützung für XAML-Typ und Sammlungen

Über die grundlegende Funktionsweise der Analyse von XAML und Auffüllen oder -Auflistung – Eigenschaften serialisiert werden soll enthält die XAML-Typsystems in .NET Framework-XAML-Dienste implementiert mehrere Funktionen, die auf Auflistungen in XAML beziehen.

1. <xref:System.Xaml.XamlType.IsCollection%2A> Gibt true zurück, wenn der XAML-Typ von einem Typ unterstützt wird, der Unterstützung von XAML enthält.

2. <xref:System.Xaml.XamlType.IsDictionary%2A> und <xref:System.Xaml.XamlType.IsArray%2A> können weiter identifizieren, welcher auflistmodus der XAML-Typ unterstützt. Für benutzerdefinierte XAML-Prozessoren, die auf .NET Framework-XAML-Dienste und die XAML basieren Typsystem jedoch nicht basierend auf vorhandenen <xref:System.Xaml.XamlWriter> Implementierungen, zu wissen, welcher auflistmodus verwendet wird, kann erforderlich sein, um zu ermitteln, welche Methode Sie aufrufen für auflistungsverarbeitung.

3. Jeder der vorherigen Eigenschaftswerte möglicherweise beeinflusst überschreibungen von <xref:System.Xaml.XamlType.LookupCollectionKind%2A> für einen XAML-Typ.
