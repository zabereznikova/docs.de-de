---
title: "Eigenschaftenänderungsereignisse"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency properties [WPF], change events
- property value changes [WPF]
- change events [WPF], property
- events [WPF], change in property values
- creating property triggers [WPF]
- property change events [WPF], types of
- property change events [WPF]
- property triggers [WPF]
- identifying changed property events [WPF]
- property triggers [WPF], definition of
ms.assetid: 0a7989df-9674-4cc1-bc50-5d8ef5d9c055
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46a11b072731daf420e35bc9c9cfd7d4fced1fe5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="property-change-events"></a>Eigenschaftenänderungsereignisse
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] definiert mehrere Ereignisse, die ausgelöst werden als Antwort auf eine Änderung des Werts einer Eigenschaft. Häufig ist die Eigenschaft eine Abhängigkeitseigenschaft. Das Ereignis selbst ist manchmal ein Routingereignis und manchmal ein [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Standardereignis. Die Definition des Ereignisses variiert je nach Szenario, da einige Eigenschaftenänderungen besser durch eine Elementstruktur weitergeleitet werden, während andere Eigenschaftenänderungen in der Regel nur für das Objekt von Bedeutung sind, bei dem sich die Eigenschaft geändert hat.  
  
## <a name="identifying-a-property-change-event"></a>Identifizierung eines Eigenschaftenänderungsereignisses  
 Nicht alle Ereignisse, die eine Eigenschaftenänderung melden, werden explizit als Eigenschaftenänderungsereignis identifiziert. Dies geschieht entweder durch ein Signaturmuster oder ein Namensmuster. Im Allgemeinen weist die Beschreibung des Ereignisses in der [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]-Dokumentation darauf hin, ob das Ereignis unmittelbar mit einer Eigenschaftswertänderung verbunden ist und Querverweise zwischen der Eigenschaft und dem Ereignis enthält.  
  
### <a name="routedpropertychanged-events"></a>Routingeigenschaftenänderungs-Ereignisse  
 Bestimmte Ereignisse verwenden einen Ereignisdatentyp und Delegaten, die explizit für Eigenschaftenänderungsereignisse verwendet werden. Der Ereignistyp der Daten ist <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, und der Delegat ist <xref:System.Windows.RoutedPropertyChangedEventHandler%601>. Die Ereignisdaten und Delegaten haben einen generischen Typparameter, der verwendet wird, um den tatsächlichen Typ der zu ändernden Eigenschaft anzugeben, wenn Sie den Handler festlegen. Die Ereignisdaten enthält zwei Eigenschaften <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> und <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, beide sind dann als Typargument in der ereignismeldung Daten übergeben.  
  
 Der „weitergeleitete“ Teil des Namens gibt an, dass das Eigenschaftenänderungsereignis als Routingereignis registriert ist. Der Vorteil des Routings eines Eigenschaftenänderungsereignisses liegt darin, dass die oberste Ebene eines Steuerelements Eigenschaftenänderungsereignisse empfangen kann, wenn Eigenschaften von untergeordneten Elementen (zusammengesetzte Komponenten des Steuerelements) die Werte ändern. Sie erstellen beispielsweise ein Steuerelement mit einem <xref:System.Windows.Controls.Primitives.RangeBase> steuern, wie z. B. eine <xref:System.Windows.Controls.Slider>. Wenn der Wert, der die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> eigenschaftenänderungen für den Schieberegler, Sie können diese Änderung auf das übergeordnete Steuerelement und nicht auf dem Teil behandeln möchten.  
  
 Da Sie über einen vorherigen und einen neuen Wert verfügen, kann es dazu verleiten, diesen Ereignishandler als ein Validierungssteuerelement für den Eigenschaftswert zu verwenden. Allerdings ist dies nicht der Zweck der meisten Eigenschaften, die durch Ereignisse geändert wurden. Im Allgemeinen werden die Werte bereitgestellt, damit Sie diese Werte in anderen Logikbereichen Ihres Codes ausführen können, aber eigentlich ist das Ändern der Werte aus dem Ereignishandler heraus nicht empfehlenswert und kann zu unbeabsichtigter Rekursion führen, dies ist davon abhängig, wie der Handler implementiert ist.  
  
 Wenn die Eigenschaft eine benutzerdefinierte Abhängigkeitseigenschaft ist oder wenn Sie mit einer abgeleiteten Klasse arbeiten, in dem Sie den Code definiert haben, ein viel bessere Mechanismus zum Nachverfolgen von eigenschaftenänderungen, die besteht in integrierten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaftensystem: die System Rückrufen <xref:System.Windows.CoerceValueCallback> und <xref:System.Windows.PropertyChangedCallback>. Weitere Informationen über die Verwendung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystems für die Überprüfung und Koersion, finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md) und [Benutzerdefinierten Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
### <a name="dependencypropertychanged-events"></a>Abhängigkeitseigenschaftsänderungs-Ereignisse  
 Eine andere Typen, die eine Eigenschaft geänderten Ereignisses Szenarios sind <xref:System.Windows.DependencyPropertyChangedEventArgs> und <xref:System.Windows.DependencyPropertyChangedEventHandler>. Ereignisse für diese Eigenschaftenänderungen werden nicht weitergeleitet; Sie sind [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Standardereignisse. <xref:System.Windows.DependencyPropertyChangedEventArgs>ist ein ungewöhnlicher für Ereignisdaten, da es nicht von abgeleitet ist <xref:System.EventArgs>; <xref:System.Windows.DependencyPropertyChangedEventArgs> ist eine Struktur, die nicht in einer Klasse.  
  
 Ereignisse, mit denen <xref:System.Windows.DependencyPropertyChangedEventArgs> und <xref:System.Windows.DependencyPropertyChangedEventHandler> sind etwas häufiger anzutreffen als `RoutedPropertyChanged` Ereignisse. Ist ein Beispiel für ein Ereignis, das diese Typen verwendet <xref:System.Windows.UIElement.IsMouseCapturedChanged>.  
  
 Wie <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, <xref:System.Windows.DependencyPropertyChangedEventArgs> gibt auch einen alten und neuen Wert für die Eigenschaft. Außerdem gelten die gleichen Überlegungen dazu, was Sie mit den Werten tun können; im Allgemeinen ist es nicht empfehlenswert, dass Sie versuchen, die Werte für den Absender als Antwort auf das Ereignis erneut zu ändern.  
  
## <a name="property-triggers"></a>Eigenschaftsauslöser  
 Ein eng mit einem Eigenschaftenänderungsereignis verbundenes Konzept ist ein Eigenschaftsauslöser. Ein Eigenschaftsauslöser wird innerhalb eines Stils oder einer Vorlage erstellt und ermöglicht es Ihnen, ein bedingtes Verhalten basierend auf dem Wert der Eigenschaft zu erstellen, in dem der Eigenschaftsauslöser zugeordnet ist.  
  
 Die Eigenschaft für einen Eigenschaftsauslöser muss eine Abhängigkeitseigenschaft sein. Es kann (und ist häufig) eine schreibgeschützte Abhängigkeitseigenschaft sein. Ein guter Indikator für den Fall, dass eine Abhängigkeitseigenschaft von einem Steuerelement verfügbar gemacht wird, ist zumindest teilweise konzipiert, um ein Eigenschaftsauslöser zu sein, wenn der Eigenschaftsname mit „Is“ beginnt. Eigenschaften, die diese Namen tragen, sind häufig schreibgeschützte boolesche Abhängigkeitseigenschaften, in denen das primäre Szenario für die Eigenschaft den Steuerelementzustand meldet, der möglicherweise Konsequenzen für die Benutzeroberfläche in Echtzeit hat und sich somit als Eigenschaftsauslöserkandidat eignet.  
  
 Einige dieser Eigenschaften können auch ein dediziertes Eigenschaftenänderungsereignis haben. Für die Instanz, die Eigenschaft <xref:System.Windows.UIElement.IsMouseCaptured%2A> wurde von einem eigenschaftsänderungsereignis <xref:System.Windows.UIElement.IsMouseCapturedChanged>. Die Eigenschaft selbst ist schreibgeschützt, wobei des Werts von der Eingabesystem angepasst und der Eingabesystem löst <xref:System.Windows.UIElement.IsMouseCapturedChanged> bei jeder Änderung in Echtzeit.  
  
 Im Vergleich zu einem echten Eigenschaftenänderungsereignis, das einen Eigenschaftsauslöser verwendet, um eine Eigenschaftenänderung zu bearbeiten, gelten hier einige Einschränkungen.  
  
 Eigenschaftsauslöser funktionieren durch eine genaue Übereinstimmungslogik. Sie legen eine Eigenschaft und einen Wert fest, die den spezifischen Wert angeben für den der Auslöser agiert. Zum Beispiel: `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`. Aufgrund dieser Einschränkung werden die meisten Eigenschaftsauslöser für boolesche Eigenschaften verwendet oder für Eigenschaften, die einen dedizierten Enumerationswert haben, wobei der mögliche Wertebereich überschaubar genug ist, um einen Auslöser für jeden Fall festzulegen. Eigenschaftsauslöser können nur für spezielle Werte vorhanden sein, z.B. wenn die Elementanzahl 0 erreicht, und keine Auslöser vorhanden sind, die Rechenschaft für die Fälle ablegen, wenn der Eigenschaftswert sich erneut von 0 entfernt (an Stelle von Auslösern benötigen Sie hier für alle Fälle ggf. einen Code-Ereignishandler oder ein Standardverhalten, das vom Auslöserstatus erneut zurückschaltet, wenn der Wert ungleich 0 ist).  
  
 Die Syntax der Eigenschaftsauslöser entspricht einer „if“-Anweisung in der Programmierung. Wenn die Auslöserbedingung echt ist, wird der „Textkörper“ des Eigenschaftsauslösers „ausgeführt“. Der „Textkörper“ von einem Eigenschaftsauslöser ist kein Code, sondern ein Markup. Das Markup ist beschränkt, die mit einem oder mehreren <xref:System.Windows.Setter> Elemente, um andere Eigenschaften des Objekts festzulegen, auf der Stil oder eine Vorlage angewendet wird.  
  
 Um die Bedingung "If" einen Eigenschaftsauslöser versetzt wird, die eine Vielzahl von möglichen Werten aufweist, wird in der Regel empfehlenswert, diesen Eigenschaftswert auf den Standardwert festlegen, indem eine <xref:System.Windows.Setter>. Auf diese Weise die <xref:System.Windows.Trigger> enthaltenen Setter haben Vorrang vor, wenn die auslöserbedingung "true" ist und die <xref:System.Windows.Setter> , die sich nicht innerhalb einer <xref:System.Windows.Trigger> wird haben Vorrang vor, wenn die auslöserbedingung auf "false" festgelegt ist.  
  
 Eigenschaftsauslöser eigenen sich im Allgemeinen für Szenarios, in denen eine oder mehrere Darstellungseigenschaften sich basierend auf dem Zustand einer anderen Eigenschaft auf dem selben Element ändern sollten.  
  
 Weitere Informationen zu Eigenschaftsauslösern finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
