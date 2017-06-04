---
title: "Collections and Collection Types for XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
caps.latest.revision: 2
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 2
---
# Collections and Collection Types for XAML
In diesem Thema wird beschrieben, wie Eigenschaften von Typen definiert, die eine Auflistung zu unterstützen, und die XAML\-Syntax zum Instanziieren der Auflistungselemente als untergeordnete Elemente eines Elements des übergeordneten Objekts oder eines Eigenschaftenelements unterstützt.  
  
## XAML\-Auflistungs\-Konzepte  
 Im Prinzip muss jedes Beziehung in XAML, in dem mehrere untergeordnete Elemente im Kontext eines XAML\-Objekt element\- oder XAML\-Eigenschaft Elements vorhanden sind, als Auflistung implementiert werden.  Diese Auflistung muss mit einer bestimmten XAML\-Eigenschaft des XAML\-Typs zugeordnet sind, der das übergeordnete Element in diesem Zusammenhang ist.  Die Eigenschaft muss eine Auflistung sein, da ein XAML\-Prozessor erwartet, dass jedes Element im Markup zuzuweisen, um ein neu hinzugefügtes Element der unterstützende Eigenschaft auflistungs.  
  
 Auf der Ebene XAML\-Sprachen werden die genauen Anforderungen der Auflistungsunterstützung nicht vollständig definiert.  Das Konzept, dass eine Auflistung entweder eine Liste sein kann oder ein Wörterbuch \(jedoch nicht beides\) für die XAML\-Sprachen Ebene definiert wurde, aber die Unterstützungstypen entweder darstellen, Listen oder Wörterbücher wird nicht durch die XAML\-Sprache definiert.  
  
 In den .NET Framework\-XAML\-Diensten ist das Konzept der XAML\-Auflistungs in Bezug auf die Unterstützung von .NET Framework\-Unterstützungstypen Relative eindeutig.  Insbesondere ist die XAML\-Unterstützung für Auflistungen auf Grundlage mehrerer .NET Konzepte und APIs, die für Listen\- und \- Wörterbuch im Allgemeinen .NET Framework\-Programmierung verwendet werden.  
  
1.  Die <xref:System.Collections.IList>\-Schnittstelle gibt eine Listenauflistung an.  
  
2.  Die <xref:System.Collections.IDictionary>\-Schnittstelle gibt eine dicionary Auflistung an.  
  
3.  <xref:System.Array> stellt ein Array dar und ein Array von unterstützten Methoden <xref:System.Collections.IList> .  
  
 In jedem dieser Konzepte der Auflistung ein .NET Framework\-XAML\-Dienste XAML\-Prozessor erwartet, `Add`\-Methode auf einer bestimmten Instanz des Typs der Auflistungseigenschaft aufzurufen.  Oder in einem Szenario mit Serialisierungsinformationen, erzeugt ein XAML\-Prozessor diskrete XAML\-TYPE\-Instanzen für jedes Element, das in der Liste im Wörterbuch oder im Array auf dem Konzept einer Auflistung von Elementen „.“  Diese sind: <xref:System.Collections.IList.Item%2A>. <xref:System.Collections.IDictionary.Item%2A>. explizite <xref:System.Array.System%23Collections%23IList%23Item%2A> für <xref:System.Array>.  
  
## Generische Auflistungen  
 Generische Auflistungen können für Allgemein programmierendes .NET Framework sinnvoll sein und können auch Eigenschaften für XAML\-Auflistungs verwendet werden.  Allerdings sind die generischen Schnittstellen und <xref:System.Collections.Generic.IList%601><xref:System.Collections.Generic.IDictionary%602> XAML\-Prozessoren von .NET Framework\-XAML\-Diensten nicht als äquivalent zu nicht generische <xref:System.Collections.IList> oder <xref:System.Collections.IDictionary>identifiziert.  Anstatt die Schnittstelle implementiert, ist eine empfohlene Vorgehensweise für generische Auflistung von Klassen, eigenschaftentypen <xref:System.Collections.Generic.List%601> oder <xref:System.Collections.Generic.Dictionary%602>zu berechnen.  Diese Klassen implementieren die nicht generische Schnittstellen und beinhalten daher die erwartete Unterstützung für XAML\-Auflistungen in der Basisimplementierung zurückgreifen.  
  
## Schreibgeschützte Auflistungen und Initialisierungslogik  
 In der .NET Framework, ist es ein allgemeines Entwurfsmuster, um eine Eigenschaft zu machen, die den Wert einer Auflistung als schreibgeschützte Auflistung enthält.  Dieses Muster kann die Instanz, die die Auflistungseigenschaft besitzt, um Steuerelement zu verbessern, was geschieht. der Auflistung.  Insbesondere verhindert das Muster versehentlichen Ersetzung der gesamten bereits vorhandenen Auflistung, indem die Eigenschaft festgelegt werden soll.  In diesem Muster muss jeder Zugriff auf die Auflistung von Aufrufern durch Aufrufen von Methoden oder Eigenschaften stattdessen gemacht werden, wie vom Auflistungstyp und\/oder die relevanten Auflistung <xref:System.Collections.IList>wie Schnittstellen unterstützt.  
  
 Die Verwendung dieses Musters bedeutet, dass alle Klassen, die eine schreibgeschützte Auflistungseigenschaft verfügbar macht, diese zunächst initialisiert werden müssen, um eine leere Auflistung sein.  In der Regel wird die Initialisierung als Teil des Verhaltens zur Erstellung der Klasse ausgeführt.  Um für XAML nützlich sein, ist es wichtig, dass solche Logik immer vom Standardkonstruktor verwiesen wird, weil das XAML im Allgemeinen den Standardkonstruktor vor der Verarbeitung der Eigenschaft aufruft \(oder Auflistungseigenschaften\).  
  
## XAML\-Typsystem\-Unterstützung und Auflistungen  
 Neben den grundlegenden Mechanikern der Analyse von XAML und des Serialisierens oder Auffüllen von Auflistungseigenschaften hinaus umfasst das XAML\-Typsystem das in .NET Framework\-XAML\-Diensten implementiert einige Ausrüstungsbeschreibungen, die Auflistungen in XAML betreffen.  
  
1.  <xref:System.Xaml.XamlType.IsCollection%2A> gibt true zurück, wenn der XAML\-Typ von einem Typ, der unterstützt wird XAML\-Auflistungs die Warteschlangenunterstützung bereitstellt.  
  
2.  <xref:System.Xaml.XamlType.IsDictionary%2A> und <xref:System.Xaml.XamlType.IsArray%2A> können weiterhin identifizieren, die den Auflistmodus XAML\-Typ unterstützt.  Für benutzerdefinierte XAML\-Prozessoren, die auf .NET Framework\-XAML\-Dienste und das XAML\-Typsystem jedoch nicht auf Grundlage vorhandener <xref:System.Xaml.XamlWriter> Implementierungen sind, kann das Wissen, welcher Auflistmodus verwendet wird, erforderlich, um die Methode zu kennen, um für die Auflistungseigenschaft hinweg aufzurufen.  
  
3.  In den vorherigen Eigenschaftswerte werden möglicherweise von Überschreibungen von <xref:System.Xaml.XamlType.LookupCollectionKind%2A> für einen XAML\-Typ auswirkt.