---
title: Erstellen und Verwenden von Komponenten in Visual Basic | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 1235f62f6ac0878e16387c35150764f3585bc004
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="creating-and-using-components-in-visual-basic"></a>Erstellen und Verwenden von Komponenten in Visual Basic
Eine *Komponente* ist eine Klasse, die die Schnittstelle <xref:System.ComponentModel.IComponent?displayProperty=fullName> implementiert oder die direkt oder indirekt von einer Klasse ableitet, die <xref:System.ComponentModel.IComponent> implementiert. Eine [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)]-Komponente ist ein Objekt, das wiederverwendet werden, mit anderen Objekten interagieren, die Steuerung von externen Ressourcen ermöglichen und Unterstützung während der Entwurfszeit bieten kann.  
  
 Ein wichtiges Feature der Komponenten ist, dass sie entworfen werden können, was bedeutet, dass eine Klasse, die eine Komponente ist, in der [!INCLUDE[vsprvs](../../csharp/includes/vsprvs_md.md)] integrierten Entwicklungsumgebung verwendet werden kann. Eine Komponente kann der Toolbox hinzugefügt, auf einem Formular abgelegt, und auf der Entwurfsoberfläche bearbeitet werden. Beachten Sie, dass die Basisunterstützung für die Entwurfszeit für Komponenten in [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)] integriert ist; ein Komponentenentwickler muss keine zusätzlichen Schritte leisten, um die Basisfunktionalität zur Entwurfszeit zu nutzen.  
  
 Ein *Steuerelement* ist einer Komponente ähnlich, da beide entworfen werden können. Allerdings stellt ein Steuerelement eine Benutzeroberfläche bereit, eine Komponente jedoch nicht. Ein Steuerelement muss von einer der Basissteuerklassen abgeleitet werden: <xref:System.Windows.Forms.Control> oder <xref:System.Web.UI.Control>.  
  
## <a name="when-to-create-a-component"></a>Wann eine Komponente zu erstellen ist  
 Wenn Ihre Klasse auf einer Entwurfsoberfläche (z.B. dem Windows Forms- oder Web Forms-Designer) verwendet wird, aber keine Benutzeroberfläche hat, sollte sie eine Komponente sein und <xref:System.ComponentModel.IComponent> implementieren, oder von einer Klasse abgeleitet werden, die direkt oder indirekt <xref:System.ComponentModel.IComponent> implementiert.  
  
 Die Klassen <xref:System.ComponentModel.Component> und <xref:System.ComponentModel.MarshalByValueComponent> sind Implementierungen der Schnittstelle <xref:System.ComponentModel.IComponent>. Der Hauptunterschied zwischen diesen Klassen besteht darin, das die <xref:System.ComponentModel.Component>-Klasse als Verweis gemarshallt wird, während <xref:System.ComponentModel.IComponent> als Wert gemarshallt wird. Die folgende Liste enthält allgemeine Richtlinien für die Implementierung.  
  
-   Wenn Ihre Komponente als Verweis gemarshallt werden muss, leiten Sie von <xref:System.ComponentModel.Component> ab.  
  
-   Wenn Ihre Komponente als Wert gemarshallt werden muss, leiten Sie von <xref:System.ComponentModel.MarshalByValueComponent> ab.  
  
-   Wenn die Komponente aufgrund einfacher Vererbung nicht von einer der Basisimplementierungen abgeleitet werden kann, implementieren Sie <xref:System.ComponentModel.IComponent>.  
  
 Weitere Informationen zur Unterstützung während der Entwurfszeit finden Sie unter [Entwurfszeitattribute für Komponenten](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3) und [Erweitern der Entwurfszeitunterstützung](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).  
  
## <a name="component-classes"></a>Komponentenklassen  
 Der Namespace <xref:System.ComponentModel> stellt Klassen bereit, mit denen das Verhalten von Komponenten und Steuerelementen zur Laufzeit und zur Entwurfszeit implementiert wird. Dieser Namespace enthält die Basisklassen und Schnittstellen zum Implementieren von Attributen und Typkonvertern, die Datenquellen binden und Komponenten lizenzieren.  
  
 Die zentralen Komponentenklassen sind:  
  
-   <xref:System.ComponentModel.Component>. Eine Basisimplementierung für die Schnittstelle <xref:System.ComponentModel.IComponent>. Diese Klasse ermöglicht das Freigeben von Objekten zwischen Anwendungen.  
  
-   <xref:System.ComponentModel.MarshalByValueComponent>. Eine Basisimplementierung für die Schnittstelle <xref:System.ComponentModel.IComponent>.  
  
-   <xref:System.ComponentModel.Container>. Die Basisimplementierung für die Schnittstelle <xref:System.ComponentModel.IContainer>. Diese Klasse enthält 0 oder mehr Komponenten.  
  
 Einige der Klassen, die für die Komponentenlizenzierung verwendet werden, sind:  
  
-   <xref:System.ComponentModel.License>. Abstrakte Basisklasse für alle Lizenzen. Eine Lizenz wird einer bestimmten Instanz einer Komponente erteilt.  
  
-   <xref:System.ComponentModel.LicenseManager>. Stellt Eigenschaften und Methoden zur Verfügung, um eine Lizenz zu einer Komponente hinzuzufügen und einen <xref:System.ComponentModel.LicenseProvider> zu verwalten.  
  
-   <xref:System.ComponentModel.LicenseProvider>. Die abstrakte Basisklasse für die Implementierung eines Lizenzgebers.  
  
-   <xref:System.ComponentModel.LicenseProviderAttribute>. Gibt die Klasse <xref:System.ComponentModel.LicenseProvider> an, die mit einer Klasse verwendet werden sollen.  
  
 Klassen, die häufig zum Beschreiben und Beibehalten von Komponenten verwendet werden.  
  
-   <xref:System.ComponentModel.TypeDescriptor>. Stellt Informationen zu den Merkmalen für eine Komponente bereit, z.B. zu Attributen, Eigenschaften und Ereignissen.  
  
-   <xref:System.ComponentModel.EventDescriptor>. Enthält Informationen über ein Ereignis.  
  
-   <xref:System.ComponentModel.PropertyDescriptor>. Gibt Informationen über eine Eigenschaft an.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Klasse vs. Komponente vs. Steuerelement](http://msdn.microsoft.com/library/db8b842e-44d9-40cc-a0f8-70fd189632c3)  
 Definiert *Komponente* und *Steuerelement*, und erläutert die Unterschiede zwischen ihnen und den Klassen.  
  
 [Komponentenerstellung](http://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 Roadmap für erste Schritte mit Komponenten.  
  
 [Exemplarische Vorgehensweise: Erstellen von Komponenten](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 Enthält Links zu Themen, die eine Schritt-für-Schritt-Anleitung für die Programmierung von Komponenten bereitstellen.  
  
 [Komponentenklassen](http://msdn.microsoft.com/library/ce2e5647-e673-4c2b-8125-ffebbd9d71bc)  
 Beschreibt, was eine Klasse zu einer Komponente macht, wie Komponentenfunktionen verfügbar gemacht werden und wie der Zugriff auf Komponenten und die Erstellung von Komponenteninstanzen gesteuert werden.  
  
 [Problembehandlung beim Erstellen von Komponenten und Steuerelementen](../../framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Erläutert die Behebung häufiger Probleme.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Zugriff auf Entwurfszeitunterstützung in Windows Forms](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)   
 [Vorgehensweise: Erweitern der Darstellung und des Verhaltens von Steuerelementen im Entwurfsmodus](http://msdn.microsoft.com/library/68f85054-2253-47f5-a4f2-3f1ac8c9f27b)   
 [Vorgehensweise: Ausführen von benutzerdefinierter Initialisierung für Steuerelemente im Entwurfsmodus](http://msdn.microsoft.com/library/914eaa03-092f-4556-9160-b8a2a40641d9)
