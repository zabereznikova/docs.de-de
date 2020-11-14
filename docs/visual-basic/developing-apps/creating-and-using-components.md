---
title: Erstellen und Verwenden von Komponenten
ms.date: 07/20/2015
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
ms.openlocfilehash: 106b8791ee5cb3db95759ccca2fddd799661ef3c
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282065"
---
# <a name="creating-and-using-components-in-visual-basic"></a>Erstellen und Verwenden von Komponenten in Visual Basic

Eine *Komponente* ist eine Klasse, die die Schnittstelle <xref:System.ComponentModel.IComponent?displayProperty=nameWithType> implementiert oder die direkt oder indirekt von einer Klasse ableitet, die <xref:System.ComponentModel.IComponent> implementiert. Eine .NET-Komponente ist ein Objekt, das wiederverwendet werden, mit anderen Objekten interagieren, die Steuerung von externen Ressourcen ermöglichen und Unterstützung während der Entwurfszeit bieten kann.  
  
 Ein wichtiges Feature der Komponenten ist, dass sie entworfen werden können, was bedeutet, dass eine Klasse, die eine Komponente ist, in der integrierten Entwicklungsumgebung von Visual Studio verwendet werden kann. Eine Komponente kann der Toolbox hinzugefügt, auf einem Formular abgelegt, und auf der Entwurfsoberfläche bearbeitet werden. Grundlegende Unterstützung für Komponenten zur Entwurfszeit ist in .NET integriert. Ein Entwickler von Komponenten muss daher nichts weiter tun, um in den Genuss der grundlegenden Entwurfszeitfunktionen zu kommen.  
  
 Ein *Steuerelement* ist einer Komponente ähnlich, da beide entworfen werden können. Allerdings stellt ein Steuerelement eine Benutzeroberfläche bereit, eine Komponente jedoch nicht. Ein Steuerelement muss von einer der Basissteuerklassen abgeleitet werden: <xref:System.Windows.Forms.Control> oder <xref:System.Web.UI.Control>.  
  
## <a name="when-to-create-a-component"></a>Wann eine Komponente zu erstellen ist  

 Wenn Ihre Klasse auf einer Entwurfsoberfläche (z.B. dem Windows Forms- oder Web Forms-Designer) verwendet wird, aber keine Benutzeroberfläche hat, sollte sie eine Komponente sein und <xref:System.ComponentModel.IComponent> implementieren, oder von einer Klasse abgeleitet werden, die direkt oder indirekt <xref:System.ComponentModel.IComponent> implementiert.  
  
 Die Klassen <xref:System.ComponentModel.Component> und <xref:System.ComponentModel.MarshalByValueComponent> sind Implementierungen der Schnittstelle <xref:System.ComponentModel.IComponent>. Der Hauptunterschied zwischen diesen Klassen besteht darin, das die <xref:System.ComponentModel.Component>-Klasse als Verweis gemarshallt wird, während <xref:System.ComponentModel.IComponent> als Wert gemarshallt wird. Die folgende Liste enthält allgemeine Richtlinien für die Implementierung.  
  
- Wenn Ihre Komponente als Verweis gemarshallt werden muss, leiten Sie von <xref:System.ComponentModel.Component> ab.  
  
- Wenn Ihre Komponente als Wert gemarshallt werden muss, leiten Sie von <xref:System.ComponentModel.MarshalByValueComponent> ab.  
  
- Wenn die Komponente aufgrund einfacher Vererbung nicht von einer der Basisimplementierungen abgeleitet werden kann, implementieren Sie <xref:System.ComponentModel.IComponent>.  
  
## <a name="component-classes"></a>Komponentenklassen  

 Der Namespace <xref:System.ComponentModel> stellt Klassen bereit, mit denen das Verhalten von Komponenten und Steuerelementen zur Laufzeit und zur Entwurfszeit implementiert wird. Dieser Namespace enthält die Basisklassen und Schnittstellen zum Implementieren von Attributen und Typkonvertern, die Datenquellen binden und Komponenten lizenzieren.  
  
 Die zentralen Komponentenklassen sind:  
  
- <xref:System.ComponentModel.Component>. Eine Basisimplementierung für die Schnittstelle <xref:System.ComponentModel.IComponent>. Diese Klasse ermöglicht das Freigeben von Objekten zwischen Anwendungen.  
  
- <xref:System.ComponentModel.MarshalByValueComponent>. Eine Basisimplementierung für die Schnittstelle <xref:System.ComponentModel.IComponent>.  
  
- <xref:System.ComponentModel.Container>. Die Basisimplementierung für die Schnittstelle <xref:System.ComponentModel.IContainer>. Diese Klasse enthält 0 oder mehr Komponenten.  
  
 Einige der Klassen, die für die Komponentenlizenzierung verwendet werden, sind:  
  
- <xref:System.ComponentModel.License>. Abstrakte Basisklasse für alle Lizenzen. Eine Lizenz wird einer bestimmten Instanz einer Komponente erteilt.  
  
- <xref:System.ComponentModel.LicenseManager>. Stellt Eigenschaften und Methoden zur Verfügung, um eine Lizenz zu einer Komponente hinzuzufügen und einen <xref:System.ComponentModel.LicenseProvider> zu verwalten.  
  
- <xref:System.ComponentModel.LicenseProvider>. Die abstrakte Basisklasse für die Implementierung eines Lizenzgebers.  
  
- <xref:System.ComponentModel.LicenseProviderAttribute>. Gibt die Klasse <xref:System.ComponentModel.LicenseProvider> an, die mit einer Klasse verwendet werden sollen.  
  
 Klassen, die häufig zum Beschreiben und Beibehalten von Komponenten verwendet werden.  
  
- <xref:System.ComponentModel.TypeDescriptor>. Stellt Informationen zu den Merkmalen für eine Komponente bereit, z.B. zu Attributen, Eigenschaften und Ereignissen.  
  
- <xref:System.ComponentModel.EventDescriptor>. Enthält Informationen über ein Ereignis.  
  
- <xref:System.ComponentModel.PropertyDescriptor>. Gibt Informationen über eine Eigenschaft an.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Problembehandlung beim Erstellen von Komponenten und Steuerelementen](/dotnet/desktop/winforms/controls/troubleshooting-control-and-component-authoring)  
 Erläutert die Behebung häufiger Probleme.  
  
## <a name="see-also"></a>Siehe auch

- [How to: Zugriff auf Unterstützung während der Entwurfszeit in Windows Forms](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time)
