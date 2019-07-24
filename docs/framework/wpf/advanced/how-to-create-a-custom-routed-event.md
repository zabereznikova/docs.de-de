---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: cbfb88af4e35e3f090248982bb14d6b7a3a03cef
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401466"
---
# <a name="how-to-create-a-custom-routed-event"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses
Damit das benutzerdefinierte Ereignis das Ereignis Routing unterstützt, müssen Sie ein <xref:System.Windows.RoutedEvent> mit der <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> -Methode registrieren. Dieses Beispiel zeigt die Grundlagen der Erstellung eines benutzerdefinierten Routingereignisses.  
  
## <a name="example"></a>Beispiel  
 Wie im folgenden Beispiel gezeigt, registrieren <xref:System.Windows.RoutedEvent> Sie zunächst mithilfe der <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> -Methode. Gemäß der Konvention sollte <xref:System.Windows.RoutedEvent> der statische Feldname mit dem Suffix- ***Ereignis***enden. In diesem Beispiel ist `Tap` der Name des Ereignisses, und die Routing Strategie des Ereignisses ist. <xref:System.Windows.RoutingStrategy.Bubble> Nach dem Registrierungs Befehl können Sie Add-and-Remove Common Language Runtime (CLR)-Ereignisaccessoren für das Ereignis bereitstellen.  
  
 Beachten Sie, dass die Art, obwohl das Ereignis in diesem speziellen Beispiel über die virtuelle Methode `OnTap` ausgelöst wird, wie Sie das Ereignis auslösen oder wie Ihr Event auf Änderungen reagiert, von Ihren Anforderungen abhängt.  
  
 Beachten Sie auch, dass in diesem Beispiel grundsätzlich eine gesamte unter <xref:System.Windows.Controls.Button>Klasse von implementiert wird. Diese Unterklasse wird als separate Assembly erstellt und dann als benutzerdefinierte Klasse auf einer separaten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seite instanziiert. Dadurch wird veranschaulicht, dass Steuerelemente als Unterklasse in Strukturen, die aus anderen Steuerelementen zusammengesetzt sind, eingefügt werden können, und in diesem Fall benutzerdefinierte Ereignisse dieser Steuerelemente über die gleichen Ereignisroutingfunktionen wie jedes native Element von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verfügen.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Tunnelingereignisse werden auf die gleiche Weise erstellt, wobei <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> jedoch im <xref:System.Windows.RoutingStrategy.Tunnel> Registrierungs Befehl auf festgelegt ist. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erhalten Tunneling-Ereignissen per Konvention das Wort „Preview“ als Präfix.  
  
 Ein Beispiel der Funktionsweise des Bubbling von Ereignissen finden Sie unter [Behandeln eines Routingereignisses](how-to-handle-a-routed-event.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Übersicht über die Eingabe](input-overview.md)
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
