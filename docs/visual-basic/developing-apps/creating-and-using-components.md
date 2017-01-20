---
title: "Creating and Using Components in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "components [Visual Basic]"
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Creating and Using Components in Visual Basic
[!INCLUDE[vs2017banner](../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine *Komponente* ist eine Klasse, die die <xref:System.ComponentModel.IComponent?displayProperty=fullName>\-Schnittstelle implementiert oder die direkt oder indirekt von einer Klasse abgeleitet ist, die <xref:System.ComponentModel.IComponent> implementiert.  Eine [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Komponente ist ein wiederverwendbares Objekt, das mit anderen Objekten interagieren kann, die Steuerung externer Ressourcen ermöglicht und Unterstützung zur Entwurfszeit bietet.  
  
 Ein wichtiges Feature von Komponenten besteht darin, dass diese entwurfsfähig sind, d. h., dass eine Klasse, die eine Komponente ist, in der [!INCLUDE[vsprvs](../../csharp/includes/vsprvs-md.md)]\-IDE verwendet werden kann.  Eine Komponente kann der Toolbox hinzugefügt, per Drag & Drop in ein Formular eingefügt und in einer Entwurfsoberfläche geändert werden.  Beachten Sie, dass die Basisunterstützung zur Entwurfszeit für Komponenten in [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort-md.md)] integriert ist. Ein Komponentenentwickler muss daher keine zusätzlichen Schritte unternehmen, um die Vorteile der Basisfunktionalität zur Entwurfszeit nutzen zu können.  
  
 Ein *Steuerelement* ist einer Komponente ähnlich, da beide entwurfsfähig sind.  Ein Steuerelement stellt jedoch im Gegensatz zu einer Komponente eine Benutzeroberfläche bereit.  Steuerelemente müssen entweder von der <xref:System.Windows.Forms.Control>\-Basisklasse oder der <xref:System.Web.UI.Control>\-Basisklasse abgeleitet sein.  
  
## Richtlinien für die Implementierung von Komponenten  
 Wenn eine Klasse in einer Entwurfsoberfläche \(z. B. dem Windows Forms\- oder Web Forms\-Designer\) verwendet werden soll, jedoch über keine Benutzeroberfläche verfügt, erstellen Sie diese als Komponente, die <xref:System.ComponentModel.IComponent> implementiert, oder leiten Sie diese von einer Klasse ab, die <xref:System.ComponentModel.IComponent> direkt oder indirekt implementiert.  
  
 Die <xref:System.ComponentModel.Component>\-Klasse und die <xref:System.ComponentModel.MarshalByValueComponent>\-Klasse sind Basisimplementierungen der <xref:System.ComponentModel.IComponent>\-Schnittstelle.  Der wesentliche Unterschied zwischen diesen Klassen liegt darin, dass die <xref:System.ComponentModel.Component>\-Klasse als Verweis gemarshallt wird, während die <xref:System.ComponentModel.IComponent> als Wert gemarshallt wird.  Die folgende Liste enthält allgemeine Richtlinien für die Implementierung.  
  
-   Wenn eine Komponente als Verweis gemarshallt werden muss, leiten Sie diese von <xref:System.ComponentModel.Component> ab.  
  
-   Wenn eine Komponente als Wert gemarshallt werden muss, leiten Sie diese von <xref:System.ComponentModel.MarshalByValueComponent> ab.  
  
-   Wenn die Komponente aufgrund einfacher Vererbung nicht von einer der Basisimplementierungen abgeleitet werden kann, implementieren Sie <xref:System.ComponentModel.IComponent>.  
  
 Weitere Informationen zur Unterstützung während der Entwurfszeit finden Sie unter [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md) und [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md).  
  
## Komponentenklassen  
 Der <xref:System.ComponentModel>\-Namespace stellt Klassen bereit, die für die Implementierung des Verhaltens von Komponenten und Steuerelementen zur Laufzeit und zur Entwurfszeit verwendet werden.  Dieser Namespace enthält die Basisklassen und Schnittstellen zum Implementieren von Attributen, Typkonvertern, Bindungen an Datenquellen und Lizenzierungskomponenten.  
  
 Im Folgenden finden Sie eine Auflistung der wichtigsten Komponentenklassen:  
  
-   <xref:System.ComponentModel.Component>.  Eine Basisimplementierung der <xref:System.ComponentModel.IComponent>\-Schnittstelle.  Diese Klasse ermöglicht die gemeinsame Nutzung von Objekten durch Anwendungen.  
  
-   <xref:System.ComponentModel.MarshalByValueComponent>.  Eine Basisimplementierung der <xref:System.ComponentModel.IComponent>\-Schnittstelle.  
  
-   <xref:System.ComponentModel.Container>.  Die Basisimplementierung der <xref:System.ComponentModel.IContainer>\-Schnittstelle.  Diese Klasse kapselt 0 \(null\) oder mehr Komponenten.  
  
 Im Folgenden werden einige der Klassen aufgeführt, die für die Komponentenlizenzierung verwendet werden:  
  
-   <xref:System.ComponentModel.License>.  Die abstrakte Basisklasse für alle Lizenzen.  Eine Lizenz wird für eine bestimmte Instanz einer Komponente erteilt.  
  
-   <xref:System.ComponentModel.LicenseManager>.  Stellt Eigenschaften und Methoden bereit, um einer Komponente eine Lizenz hinzuzufügen und eine <xref:System.ComponentModel.LicenseProvider>\-Klasse zu verwalten.  
  
-   <xref:System.ComponentModel.LicenseProvider>.  Die abstrakte Basisklasse für die Implementierung eines Lizenzgebers.  
  
-   <xref:System.ComponentModel.LicenseProviderAttribute>.  Gibt die mit einer Klasse zu verwendende <xref:System.ComponentModel.LicenseProvider>\-Klasse an.  
  
 Im Folgenden werden Klassen aufgeführt, die im Allgemeinen für das Beschreiben und das Beibehalten von Komponenten verwendet werden.  
  
-   <xref:System.ComponentModel.TypeDescriptor>.  Stellt Informationen über die Eigenschaften einer Komponente bereit, z. B. seine Attribute, Eigenschaften und Ereignisse.  
  
-   <xref:System.ComponentModel.EventDescriptor>.  Stellt Informationen zu einem Ereignis bereit.  
  
-   <xref:System.ComponentModel.PropertyDescriptor>.  Stellt Informationen über eine Eigenschaft bereit.  
  
## Verwandte Abschnitte  
 [Class vs. Component vs. Control](../Topic/Class%20vs.%20Component%20vs.%20Control.md)  
 Definiert die Begriffe *Komponente* und *Steuerelement* und erläutert deren Unterschiede zu Klassen.  
  
 [Component Authoring](../Topic/Component%20Authoring.md)  
 Bietet einen Wegweiser für den Einstieg in die Arbeit mit Komponenten.  
  
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)  
 Enthält Links zu Themen mit schrittweisen Anleitungen für die Komponentenprogrammierung.  
  
 [Component Classes](../Topic/Component%20Classes.md)  
 Beschreibt, in welchen Fall Klassen Komponenten sind, die Möglichkeiten zum Verfügbarmachen der Komponentenfunktionalität, die Steuerung des Zugriffs auf Komponenten und die Steuerung der Erstellung von Komponenteninstanzen.  
  
 [Problembehandlung beim Erstellen von Komponenten und Steuerelementen](../Topic/Troubleshooting%20Control%20and%20Component%20Authoring.md)  
 Bietet Lösungen für allgemeine Probleme.  
  
## Siehe auch  
 [How to: Access Design\-Time Support in Windows Forms](../Topic/How%20to:%20Access%20Design-Time%20Support%20in%20Windows%20Forms.md)   
 [How to: Extend the Appearance and Behavior of Controls in Design Mode](../Topic/How%20to:%20Extend%20the%20Appearance%20and%20Behavior%20of%20Controls%20in%20Design%20Mode.md)   
 [How to: Perform Custom Initialization for Controls in Design Mode](../Topic/How%20to:%20Perform%20Custom%20Initialization%20for%20Controls%20in%20Design%20Mode.md)