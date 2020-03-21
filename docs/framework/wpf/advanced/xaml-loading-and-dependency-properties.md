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
ms.openlocfilehash: de8050e582f5b1a5a288c350c179cfa24fb5471c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186252"
---
# <a name="xaml-loading-and-dependency-properties"></a>Laden von XAML und Abhängigkeitseigenschaften
Die aktuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessors ist mit Abhängigkeitseigenschaften kompatibel. Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor verwendet Eigenschaftensystemmethoden für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Abhängigkeitseigenschaften beim Laden von binären und Verarbeitungsattributen, die Abhängigkeitseigenschaften sind. Dadurch werden Eigenschaftenwrapper praktisch umgangen. Wenn Sie benutzerdefinierte Abhängigkeitseigenschaften implementieren, müssen Sie dieses Verhalten berücksichtigen und sollten vermeiden, <xref:System.Windows.DependencyObject.GetValue%2A> dass <xref:System.Windows.DependencyObject.SetValue%2A>andere Codes in Ihrem Eigenschaftenwrapper als die Eigenschaftensystemmethoden und platziert werden.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie Abhängigkeitseigenschaften sowohl aus Sicht eines Anwenders als auch der eines Autors verstehen, und dass Sie [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) und [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) gelesen haben. Sie sollten auch [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) und [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md) gelesen haben.  
  
<a name="implementation"></a>
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementierung und Leistung des WPF-XAML-Ladeprogramms  
 Aus Implementierungsgründen ist es rechnerisch kostengünstiger, eine Eigenschaft als <xref:System.Windows.DependencyObject.SetValue%2A> Abhängigkeitseigenschaft zu identifizieren und auf die Eigenschaftssystemmethode zuzugreifen, um sie festzulegen, anstatt den Eigenschaftenwrapper und dessen Setter zu verwenden. Grund hierfür ist, dass der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessor das gesamte Objektmodell des unterstützenden Codes allein auf Basis der Typ- und Mitgliedsbeziehungen, die durch die Markupstruktur und verschiedene Zeichenfolgen erkennbar sind, herleiten muss.  
  
 Der Typ wird durch eine Kombination aus XMLns und Assemblyattributen gesucht, aber die Member identifiziert, bestimmt, welche als Attribut festgelegt <xref:System.Reflection.PropertyInfo>werden können, und auflösen, welche Typen die Eigenschaftenwerte unterstützen würden, die andernfalls umfangreiche Reflexion mithilfe erfordern würden. Da Abhängigkeitseigenschaften für einen bestimmten Typ über das Eigenschaftensystem als Speichertabelle zugänglich sind, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet die Implementierung [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] des Prozessors diese Tabelle und leitet ab, dass jede bestimmte Eigenschaft *ABC* effizienter festgelegt werden kann, indem <xref:System.Windows.DependencyObject.SetValue%2A> der enthaltende <xref:System.Windows.DependencyObject> abgeleitete Typ mithilfe des Abhängigkeitseigenschaftsbezeichners *ABCProperty*aufgerufen wird.  
  
<a name="implications"></a>
## <a name="implications-for-custom-dependency-properties"></a>Auswirkungen auf Benutzerdefinierte Abhängigkeitseigenschaften  
 Da die aktuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Prozessorverhaltens für die Festlegung von Eigenschaften die Wrapper vollständig umgeht, dürfen Sie keine zusätzliche Logik in die Set-Definitionen des Wrappers für die benutzerdefinierte Abhängigkeitseigenschaft einfügen. Wenn Sie solche Logik in der Set-Definition einfügen, wird diese Logik nicht ausgeführt werden, wenn die Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] statt in Code festgelegt wird.  
  
 In ähnlicher Weise [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] werden auch andere [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Aspekte des <xref:System.Windows.DependencyObject.GetValue%2A> Prozessors, die Eigenschaftswerte aus der Verarbeitung abrufen, anstelle des Wrappers verwendet. Daher sollten Sie auch jede zusätzliche `get` Implementierung <xref:System.Windows.DependencyObject.GetValue%2A> in der Definition über den Aufruf hinaus vermeiden.  
  
 Das folgende Beispiel ist eine empfohlene Abhängigkeitseigenschaftsdefinition mit Wrappern, bei der der Eigenschaftsbezeichner `public` `static` `readonly` als Feld gespeichert wird und die und-Definitionen `get` `set` keinen Code enthalten, der über die erforderlichen Eigenschaftensystemmethoden hinausgeht, die die Unterstützung der Abhängigkeitseigenschaft definieren.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Abhängigkeitseigenschaften vom Auflistungstyp](collection-type-dependency-properties.md)
- [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md)
- [Sichere Konstruktormuster für DependencyObjects](safe-constructor-patterns-for-dependencyobjects.md)
