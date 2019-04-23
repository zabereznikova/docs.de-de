---
title: 'Vorgehensweise: Registrieren einer angefügten Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
ms.openlocfilehash: 4c678a64b62b8f4db24cf39ffbafac52e56c9982
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137630"
---
# <a name="how-to-register-an-attached-property"></a>Vorgehensweise: Registrieren einer angefügten Eigenschaft
In diesem Beispiel wird das Registrieren einer angefügten Eigenschaft und das Bereitstellen öffentlicher Accessoren beschrieben, damit Sie die Eigenschaft jeweils in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und in Code verwenden können. Angefügte Eigenschaften sind ein von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definiertes Syntaxkonzept. Die meisten angefügten Eigenschaften für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Typen werden auch als Abhängigkeitseigenschaften implementiert. Verwenden von Abhängigkeitseigenschaften können auf jedem <xref:System.Windows.DependencyObject> Typen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine angefügte Eigenschaft als eine Abhängigkeitseigenschaft registrieren, mit der <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode. Die Providerklasse hat die Möglichkeit zur Bereitstellung von Standardmetadaten für die Eigenschaft, die angewendet wird, wenn die Eigenschaft in einer anderen Klasse verwendet wird, es sei denn, diese Klasse überschreibt die Metadaten. In diesem Beispiel wird der Standardwert der `IsBubbleSource`-Eigenschaft auf `false` festgelegt.  
  
 Die Anbieterklasse für eine angefügte Eigenschaft (auch wenn diese nicht als Abhängigkeitseigenschaft registriert ist) muss statische get- und set-Accessoren bereitstellen, die die Benennungskonvention `Set`*[NameDerAngefügtenEigenschaft]* und `Get`*[NameDerAngefügtenEigenschaft]* befolgen. Diese Accessoren sind erforderlich, damit der agierende Leser von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] die Eigenschaft als Attribut in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erkennen und die entsprechenden Typen auflösen kann.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.DependencyProperty>
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Themen zu Vorgehensweisen](properties-how-to-topics.md)
