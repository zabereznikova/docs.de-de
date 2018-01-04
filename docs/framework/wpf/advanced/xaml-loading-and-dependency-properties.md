---
title: "Laden von XAML und Abhängigkeitseigenschaften"
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
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9771aa05d029603a018e041644ff3e2018e26ca4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-loading-and-dependency-properties"></a>Laden von XAML und Abhängigkeitseigenschaften
Die aktuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessors ist mit Abhängigkeitseigenschaften kompatibel. Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessor verwendet Methoden des Eigenschaftensystems zum Laden von binären [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und zum Verarbeiten von Attributen, die Abhängigkeitseigenschaften sind. Dadurch werden Eigenschaftenwrapper praktisch umgangen. Wenn Sie benutzerdefinierte Abhängigkeitseigenschaften implementieren, Sie müssen für dieses Verhalten berücksichtigen sollten gehalten und keinem anderen Code in Ihrer Eigenschaftenwrapper als das System Eigenschaftenmethoden <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften sowohl aus Sicht eines Anwenders als auch der eines Autors verstehen, und dass Sie [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) und [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) gelesen haben. Sie sollten auch [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) und [Ausführliche Erläuterung der XAML-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md) gelesen haben.  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementierung und Leistung des WPF-XAML-Ladeprogramms  
 Aus Gründen der Implementierung ist weniger rechenintensiv zu identifiziert eine Eigenschaft als Abhängigkeitseigenschaft im Eigenschaftensystem zugreifen <xref:System.Windows.DependencyObject.SetValue%2A> Methode, um diesen, anstatt den Eigenschaftenwrapper und die Setter-Methode festgelegt. Grund hierfür ist, dass der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessor das gesamte Objektmodell des unterstützenden Codes allein auf Basis der Typ- und Mitgliedsbeziehungen, die durch die Markupstruktur und verschiedene Zeichenfolgen erkennbar sind, herleiten muss.  
  
 Der Typ mit einer Kombination von Xmlns und Assemblyattribute jedoch identifizieren die Elemente, die ermittelt werden, unterstützen kann, der als ein Attribut festgelegt nachgeschlagen und welche Typen die Eigenschaftswerte unterstützen andernfalls würde eine umfangreiche Reflektion erfordern Mithilfe von <xref:System.Reflection.PropertyInfo>. Da Abhängigkeitseigenschaften für einen bestimmten Typ als eine Speichertabelle durch das Eigenschaftensystem zugegriffen werden die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Implementierung seiner [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor verwendet diese Tabelle, und leitet alle angegebene Eigenschaft *ABC* kann effizienter festgelegt werden, durch den Aufruf <xref:System.Windows.DependencyObject.SetValue%2A> für das enthaltende <xref:System.Windows.DependencyObject> abgeleiteten Typ unter Verwendung des Bezeichners der Abhängigkeitseigenschaft *ABCProperty*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Auswirkungen auf Benutzerdefinierte Abhängigkeitseigenschaften  
 Da die aktuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessorverhaltens für die Festlegung von Eigenschaften die Wrapper vollständig umgeht, dürfen Sie keine zusätzliche Logik in die Set-Definitionen des Wrappers für die benutzerdefinierte Abhängigkeitseigenschaft einfügen. Wenn Sie solche Logik in der Set-Definition einfügen, wird diese Logik nicht ausgeführt werden, wenn die Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] statt in Code festgelegt wird.  
  
 Auf ähnliche Weise andere Aspekte der der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, wie die Eigenschaftswerte aus abrufen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Verarbeitung auch verwenden <xref:System.Windows.DependencyObject.GetValue%2A> statt den Wrapper. Aus diesem Grund auch sollten Sie alle zusätzliche-Implementierung in der `get` Definition außerhalb der <xref:System.Windows.DependencyObject.GetValue%2A> aufrufen.  
  
 Das folgende Beispiel ist eine empfohlene Definition von Abhängigkeitseigenschaften mit Wrappern, wobei der Eigenschaftenbezeichner als `public` `static` `readonly`-Feld gespeichert wird und die `get`- und `set`-Definitionen keinen Code außer den erforderlichen Systemmethoden enthalten, die die Unterstützung der Abhängigkeitseigenschaft definieren.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [Abhängigkeitseigenschaften vom Auflistungstyp](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)  
 [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md)  
 [Sichere Konstruktormuster für DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)
