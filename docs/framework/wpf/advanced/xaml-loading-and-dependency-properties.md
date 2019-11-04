---
title: Laden von XAML und Abhängigkeitseigenschaften
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
ms.openlocfilehash: 57c25297f995acd1ef307466258b5f4e03cc3098
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459543"
---
# <a name="xaml-loading-and-dependency-properties"></a>Laden von XAML und Abhängigkeitseigenschaften
Die aktuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessors ist mit Abhängigkeitseigenschaften kompatibel. Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessor verwendet Methoden des Eigenschaftensystems zum Laden von binären [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und zum Verarbeiten von Attributen, die Abhängigkeitseigenschaften sind. Dadurch werden Eigenschaftenwrapper praktisch umgangen. Wenn Sie benutzerdefinierte Abhängigkeits Eigenschaften implementieren, müssen Sie dieses Verhalten berücksichtigen und vermeiden, dass Sie anderen Code in Ihrem Eigenschaften Wrapper außer den Eigenschaften System Methoden <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A>platzieren.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Voraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften sowohl aus Sicht eines Anwenders als auch der eines Autors verstehen, und dass Sie [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) und [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) gelesen haben. Sie sollten auch [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) und [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md) gelesen haben.  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementierung und Leistung des WPF-XAML-Ladeprogramms  
 Aus Implementierungs Gründen ist es rechnerisch kostengünstiger, eine Eigenschaft als Abhängigkeits Eigenschaft zu identifizieren und auf das Eigenschafts System <xref:System.Windows.DependencyObject.SetValue%2A> Methode zuzugreifen, um Sie festzulegen, anstatt den Eigenschafts Wrapper und dessen Setter zu verwenden. Grund hierfür ist, dass der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessor das gesamte Objektmodell des unterstützenden Codes allein auf Basis der Typ- und Mitgliedsbeziehungen, die durch die Markupstruktur und verschiedene Zeichenfolgen erkennbar sind, herleiten muss.  
  
 Der Typ wird durch eine Kombination aus xmlns-und Assemblyattributen durchsucht, aber die Elemente werden identifiziert, und es wird festgelegt, welche Unterstützung als Attribut festgelegt werden kann mit <xref:System.Reflection.PropertyInfo>. Da Abhängigkeits Eigenschaften für einen bestimmten Typ als Speicher Tabelle über das-Eigenschaften System zugänglich sind, verwendet die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessors diese Tabelle und leitet, dass eine bestimmte Eigenschaft *ABC* effizienter durch festgelegt werden kann. Aufrufen von <xref:System.Windows.DependencyObject.SetValue%2A> für den enthaltenden <xref:System.Windows.DependencyObject> abgeleiteten Typ mithilfe der Abhängigkeits Eigenschaft Bezeichner *abcProperty*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Auswirkungen auf Benutzerdefinierte Abhängigkeitseigenschaften  
 Da die aktuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessorverhaltens für die Festlegung von Eigenschaften die Wrapper vollständig umgeht, dürfen Sie keine zusätzliche Logik in die Set-Definitionen des Wrappers für die benutzerdefinierte Abhängigkeitseigenschaft einfügen. Wenn Sie solche Logik in der Set-Definition einfügen, wird diese Logik nicht ausgeführt werden, wenn die Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] statt in Code festgelegt wird.  
  
 Ebenso verwenden andere Aspekte des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessors, die Eigenschaftswerte aus [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Verarbeitung abrufen, auch <xref:System.Windows.DependencyObject.GetValue%2A> statt den Wrapper zu verwenden. Daher sollten Sie auch zusätzliche Implementierungen in der `get` Definition vermeiden, die über den <xref:System.Windows.DependencyObject.GetValue%2A>-aufrufungstyp hinausgehen.  
  
 Das folgende Beispiel ist eine empfohlene Definition von Abhängigkeitseigenschaften mit Wrappern, wobei der Eigenschaftenbezeichner als `public` `static` `readonly`-Feld gespeichert wird und die `get`- und `set`-Definitionen keinen Code außer den erforderlichen Systemmethoden enthalten, die die Unterstützung der Abhängigkeitseigenschaft definieren.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Abhängigkeitseigenschaften vom Auflistungstyp](collection-type-dependency-properties.md)
- [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md)
- [Sichere Konstruktormuster für DependencyObjects](safe-constructor-patterns-for-dependencyobjects.md)
