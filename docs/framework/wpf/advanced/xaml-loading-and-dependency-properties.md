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
ms.openlocfilehash: ed608a658b5077a20ed56419c4ac731641610e3d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373074"
---
# <a name="xaml-loading-and-dependency-properties"></a>Laden von XAML und Abhängigkeitseigenschaften
Die aktuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessors ist mit Abhängigkeitseigenschaften kompatibel. Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessor verwendet Methoden des Eigenschaftensystems zum Laden von binären [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und zum Verarbeiten von Attributen, die Abhängigkeitseigenschaften sind. Dadurch werden Eigenschaftenwrapper praktisch umgangen. Wenn Sie benutzerdefinierte Abhängigkeitseigenschaften implementieren, Sie müssen dieses Verhalten berücksichtigen und vermeiden jeder andere Code in Ihrem Eigenschaftenwrapper außer den Methoden des Eigenschaftensystems <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften sowohl aus Sicht eines Anwenders als auch der eines Autors verstehen, und dass Sie [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) und [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) gelesen haben. Sie sollten auch [Übersicht über XAML (WPF)](xaml-overview-wpf.md) und [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md) gelesen haben.  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementierung und Leistung des WPF-XAML-Ladeprogramms  
 Für die Implementierung betrifft, ist es weniger rechenintensiv, eine Eigenschaft als Abhängigkeitseigenschaft zu identifizieren und Zugriff auf das Eigenschaftensystem <xref:System.Windows.DependencyObject.SetValue%2A> Methode, um es anstelle der Verwendung des Eigenschaftenwrapper und dessen Setter festzulegen. Grund hierfür ist, dass der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessor das gesamte Objektmodell des unterstützenden Codes allein auf Basis der Typ- und Mitgliedsbeziehungen, die durch die Markupstruktur und verschiedene Zeichenfolgen erkennbar sind, herleiten muss.  
  
 Der Typ gesucht wird durch eine Kombination von Xmlns und Assemblyattribute, sondern identifiziert die Elemente ermitteln, welches kann als Attribut festgelegt wird, und beheben, welche Typen die Eigenschaftswerte unterstützen, würde sonst umfangreiche Reflektion erfordern Mithilfe von <xref:System.Reflection.PropertyInfo>. Da Abhängigkeitseigenschaften für einen bestimmten Typ als eine Speichertabelle über das Eigenschaftensystem, zugänglich sind die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Implementierung der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor verwendet diese Tabelle und folgert, dass die angegebene Eigenschaft *ABC* durch Aufrufen von effizienter festgelegt werden können <xref:System.Windows.DependencyObject.SetValue%2A> auf dem mit <xref:System.Windows.DependencyObject> abgeleiteten Typ, mit der Bezeichner der Abhängigkeitseigenschaft *ABCProperty*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Auswirkungen auf Benutzerdefinierte Abhängigkeitseigenschaften  
 Da die aktuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessorverhaltens für die Festlegung von Eigenschaften die Wrapper vollständig umgeht, dürfen Sie keine zusätzliche Logik in die Set-Definitionen des Wrappers für die benutzerdefinierte Abhängigkeitseigenschaft einfügen. Wenn Sie solche Logik in der Set-Definition einfügen, wird diese Logik nicht ausgeführt werden, wenn die Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] statt in Code festgelegt wird.  
  
 Auf ähnliche Weise andere Aspekte der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, der die Eigenschaftswerte aus abrufen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Verarbeitung mittels <xref:System.Windows.DependencyObject.GetValue%2A> statt den Wrapper. Aus diesem Grund zudem sollten Sie alle von zusätzlichen Implementierung in der `get` Definition außerhalb der <xref:System.Windows.DependencyObject.GetValue%2A> aufrufen.  
  
 Das folgende Beispiel ist eine empfohlene Definition von Abhängigkeitseigenschaften mit Wrappern, wobei der Eigenschaftenbezeichner als `public` `static` `readonly`-Feld gespeichert wird und die `get`- und `set`-Definitionen keinen Code außer den erforderlichen Systemmethoden enthalten, die die Unterstützung der Abhängigkeitseigenschaft definieren.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Abhängigkeitseigenschaften vom Auflistungstyp](collection-type-dependency-properties.md)
- [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md)
- [Sichere Konstruktormuster für DependencyObjects](safe-constructor-patterns-for-dependencyobjects.md)
