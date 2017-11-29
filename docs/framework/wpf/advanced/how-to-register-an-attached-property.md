---
title: "Gewusst wie: Registrieren einer angefügten Eigenschaft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aecb5d2f35b8532ad2ae7558af1a93243b0fd6df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-register-an-attached-property"></a>Gewusst wie: Registrieren einer angefügten Eigenschaft
In diesem Beispiel wird das Registrieren einer angefügten Eigenschaft und das Bereitstellen öffentlicher Accessoren beschrieben, damit Sie die Eigenschaft jeweils in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] und in Code verwenden können. Angefügte Eigenschaften sind ein von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] definiertes Syntaxkonzept. Die meisten angefügten Eigenschaften für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Typen werden auch als Abhängigkeitseigenschaften implementiert. Können Sie für ein beliebiges Abhängigkeitseigenschaften <xref:System.Windows.DependencyObject> Typen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie zum Registrieren einer angefügten Eigenschaft als eine Abhängigkeitseigenschaft mit dem <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Methode. Die Providerklasse hat die Möglichkeit zur Bereitstellung von Standardmetadaten für die Eigenschaft, die angewendet wird, wenn die Eigenschaft in einer anderen Klasse verwendet wird, es sei denn, diese Klasse überschreibt die Metadaten. In diesem Beispiel wird der Standardwert der `IsBubbleSource`-Eigenschaft auf `false` festgelegt.  
  
 Die Anbieterklasse für eine angefügte Eigenschaft (auch wenn diese nicht als Abhängigkeitseigenschaft registriert ist) muss statische get- und set-Accessoren bereitstellen, die die Benennungskonvention `Set`*[NameDerAngefügtenEigenschaft]* und `Get`*[NameDerAngefügtenEigenschaft]* befolgen. Diese Accessoren sind erforderlich, damit der agierende Leser von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] die Eigenschaft als Attribut in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erkennen und die entsprechenden Typen auflösen kann.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.DependencyProperty>  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
