---
title: Auflistungen und Auflistungstypen für XAML
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 5605c97b13503e18e2f698f2a19f715663052b08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562975"
---
# <a name="collections-and-collection-types-for-xaml"></a>Auflistungen und Auflistungstypen für XAML
Dieses Thema beschreibt die Eigenschaften der Typen zu definieren, die zur Unterstützung einer auflistungs, um die Verwendung von XAML-Syntax zu unterstützen, zum Instanziieren der Auflistungselemente als untergeordnete Elemente eines übergeordneten Object-Element oder die Property-Element bestimmt werden.  
  
## <a name="xaml-collection-concepts"></a>Verwendung von XAML-Auflistung Konzepte  
 Im Prinzip einer Beziehung in XAML, in denen mehrere untergeordnete Elemente innerhalb des Bereichs von einem XAML-Objektelement vorhanden sind oder Verwendung von XAML-Property-Element muss als Auflistung implementiert werden. Diese Sammlung muss mit einer bestimmten XAML-Eigenschaft von der Verwendung von XAML-Typ zugeordnet werden, die das übergeordnete Element in dieser Beziehung ist. Die Eigenschaft muss eine Auflistung sein, da ein XAML-Prozessor erwartet, dass jedes Element im Markup für eine neu hinzugefügte Element der dahinter liegende Auflistungseigenschaft werden zugewiesen.  
  
 Bei der Verwendung von XAML-Sprachebene werden Bindungen die Anforderungen der Unterstützung von nicht vollständig definiert. Das Konzept, dass eine Auflistung kann entweder eine Liste oder ein Wörterbuch (aber nicht beide zusammen) auf die Verwendung von XAML-Sprachebene definiert ist, aber welche unterstützende Typen darstellen, entweder Listen oder Wörterbücher wird nicht durch die XAML-Sprache definiert.  
  
 In .NET Framework XAML Services wird das Konzept des XAML-Unterstützung in Bezug auf .NET Framework-Unterstützungstypen genauer definiert. Insbesondere basiert die Verwendung von XAML-Unterstützung für Auflistungen auf mehrere .NET Framework-Konzepte und APIs, die für Listen und Wörterbücher allgemeine Programmierung in .NET Framework verwendet werden.  
  
1.  Die <xref:System.Collections.IList> -Schnittstelle gibt eine listenauflistung an.  
  
2.  Die <xref:System.Collections.IDictionary> -Schnittstelle gibt eine dicionary Auflistung an.  
  
3.  <xref:System.Array> Stellt ein Array, und ein Array unterstützt <xref:System.Collections.IList> Methoden.  
  
 In jedem dieser Auflistung Konzepte können ein .NET Framework XAML Services-XAML-Prozessor erwartet, dass zum Aufrufen der `Add` Methode in einer bestimmten Instanz des Typs für die Auflistungseigenschaft. Oder in einem Szenario Serialisierung erzeugt ein XAML-Prozessor diskrete-Diagramm nach der Verwendung von XAML-Instanzen für jedes Element in der Liste, Wörterbuch oder Array basierend auf jede Sammlung spezifische Konzept der "Elemente" gefunden. Dies sind: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; die explizite <xref:System.Array.System%23Collections%23IList%23Item%2A> für <xref:System.Array>.  
  
## <a name="generic-collections"></a>Generische Auflistungen  
 Generische Auflistungen können für allgemeine .NET Framework-Programmierung nützlich sein, und können auch bei Auflistungseigenschaften XAML verwendet werden. Die generische jedoch Schnittstellen <xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602> von .NET Framework XAML Services-XAML-Prozessoren als gleichwertig, die nicht generische nicht erkannt <xref:System.Collections.IList> oder <xref:System.Collections.IDictionary>. Statt die Schnittstellen zu implementieren, ist eine empfohlene Vorgehensweise für generische Auflistungstypen-Eigenschaft von den Klassen ableiten <xref:System.Collections.Generic.List%601> oder <xref:System.Collections.Generic.Dictionary%602>. Diese Klassen, die nicht generische Schnittstellen implementieren und daher enthalten die erwartete Unterstützung für die Verwendung von XAML-Auflistungen in der basisimplementierung.  
  
## <a name="read-only-collections-and-initialization-logic"></a>Nur-Lese Sammlungen und Initialisierungslogik  
 In .NET Framework-Programmierung ist es ein allgemeines Entwurfsmuster, um eine Eigenschaft zu erstellen, die einen Wert, der eine Auflistung als eine schreibgeschützte Auflistung enthält. Dieses Muster ist die Instanz, die die Auflistungseigenschaft eine verbesserte Steuerung besitzt, was, auf die Auflistung geschieht... Insbesondere verhindert, dass das Muster versehentliche Ersetzung der gesamten vorhandenen Auflistung durch Festlegen der Eigenschaft. Bei diesem Muster keinen Zugriff auf die Auflistung von Aufrufern sollten stattdessen erfolgen durch Aufrufen von Methoden oder Eigenschaften, wie z. B. durch die "Sammlung" und/oder die relevanten Auflistungsschnittstellen unterstützt <xref:System.Collections.IList>.  
  
 Mithilfe des folgenden Musters impliziert, dass jede Klasse, die eine schreibgeschützte Auflistungseigenschaft verfügbar macht diese Eigenschaft eine leere Auflistung enthält zunächst initialisieren muss. Die Initialisierung wird in der Regel als Teil des Verhaltens zur Erstellung für die Klasse ausgeführt. Um die für Markuperweiterungen für XAML hilfreich sein, es ist wichtig, dass solche Logik immer vom Standardkonstruktor, verwiesen wird da XAML in der Regel den Standardkonstruktor vor dem Verarbeiten der Eigenschaften aufruft (Sammlungseigenschaften oder auf andere Weise).  
  
## <a name="xaml-type-system-support-and-collections"></a>Unterstützung von XAML-Typ und Sammlungen  
 Über die grundlegende Funktionsweise der XAML-Analyse und Auffüllen oder Sammlungseigenschaften Serialisieren enthält der XAML-Typsystem in .NET Framework XAML Services implementierte mehrere Entwurfsfunktionen, die für Sammlungen in XAML beziehen.  
  
1.  <xref:System.Xaml.XamlType.IsCollection%2A> Gibt true zurück, wenn die XAML-Typ von einem Typ gesichert wird, der XAML-Auflistung unterstützt.  
  
2.  <xref:System.Xaml.XamlType.IsDictionary%2A> und <xref:System.Xaml.XamlType.IsArray%2A> können weiter identifizieren, welcher auflistmodus die Verwendung von XAML-Typ unterstützt. Für benutzerdefinierte XAML Prozessoren, die auf .NET Framework-XAML-Dienste und der XAML-Typsystem, aber nicht basierend auf vorhandenen <xref:System.Xaml.XamlWriter> -Implementierungen zu wissen, welcher auflistmodus verwendet wird möglicherweise notwendig, damit bekannt ist, welche Methode für aufrufen die Verarbeitung einer Auflistung.  
  
3.  Jeder der vorherigen Eigenschaftswerte sind potenziell beeinflusst durch Außerkraftsetzungen von <xref:System.Xaml.XamlType.LookupCollectionKind%2A> auf einen XAML-Typ.
