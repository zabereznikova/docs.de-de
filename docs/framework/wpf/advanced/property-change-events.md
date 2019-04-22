---
title: Eigenschaftenänderungsereignisse
ms.date: 03/30/2017
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
ms.openlocfilehash: b6f625f76e230b7d6bf0488bfa75c227de31a5d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166204"
---
# <a name="property-change-events"></a>Eigenschaftenänderungsereignisse
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] definiert mehrere Ereignisse, die ausgelöst werden als Antwort auf eine Änderung des Werts einer Eigenschaft. Häufig ist die Eigenschaft eine Abhängigkeitseigenschaft. Das Ereignis selbst ist manchmal ein Routingereignis und manchmal ein [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Standardereignis. Die Definition des Ereignisses variiert je nach Szenario, da einige Eigenschaftenänderungen besser durch eine Elementstruktur weitergeleitet werden, während andere Eigenschaftenänderungen in der Regel nur für das Objekt von Bedeutung sind, bei dem sich die Eigenschaft geändert hat.  
  
## <a name="identifying-a-property-change-event"></a>Identifizierung eines Eigenschaftenänderungsereignisses  
 Nicht alle Ereignisse, die eine Eigenschaftenänderung melden, werden explizit als Eigenschaftenänderungsereignis identifiziert. Dies geschieht entweder durch ein Signaturmuster oder ein Namensmuster. Im Allgemeinen weist die Beschreibung des Ereignisses in der [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]-Dokumentation darauf hin, ob das Ereignis unmittelbar mit einer Eigenschaftswertänderung verbunden ist und Querverweise zwischen der Eigenschaft und dem Ereignis enthält.  
  
### <a name="routedpropertychanged-events"></a>Routingeigenschaftenänderungs-Ereignisse  
 Bestimmte Ereignisse verwenden einen Ereignisdatentyp und Delegaten, die explizit für Eigenschaftenänderungsereignisse verwendet werden. Der Ereignisdatentyp ist <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, und der Delegat ist <xref:System.Windows.RoutedPropertyChangedEventHandler%601>. Die Ereignisdaten und Delegaten haben einen generischen Typparameter, der verwendet wird, um den tatsächlichen Typ der zu ändernden Eigenschaft anzugeben, wenn Sie den Handler festlegen. Die Ereignisdaten enthält zwei Eigenschaften: <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> und <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, die beide sind dann als Typargument in den Ereignisdaten übergeben.  
  
 Der „weitergeleitete“ Teil des Namens gibt an, dass das Eigenschaftenänderungsereignis als Routingereignis registriert ist. Der Vorteil des Routings eines Eigenschaftenänderungsereignisses liegt darin, dass die oberste Ebene eines Steuerelements Eigenschaftenänderungsereignisse empfangen kann, wenn Eigenschaften von untergeordneten Elementen (zusammengesetzte Komponenten des Steuerelements) die Werte ändern. Sie erstellen beispielsweise ein Steuerelement mit einem <xref:System.Windows.Controls.Primitives.RangeBase> steuern, wie z. B. eine <xref:System.Windows.Controls.Slider>. Wenn der Wert des der <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> eigenschaftsänderungen für den Schieberegler, Sie möchten, die diese Änderung auf das übergeordnete Steuerelement und nicht auf den Teil zu behandeln.  
  
 Da Sie über einen vorherigen und einen neuen Wert verfügen, kann es dazu verleiten, diesen Ereignishandler als ein Validierungssteuerelement für den Eigenschaftswert zu verwenden. Allerdings ist dies nicht der Zweck der meisten Eigenschaften, die durch Ereignisse geändert wurden. Im Allgemeinen werden die Werte bereitgestellt, damit Sie diese Werte in anderen Logikbereichen Ihres Codes ausführen können, aber eigentlich ist das Ändern der Werte aus dem Ereignishandler heraus nicht empfehlenswert und kann zu unbeabsichtigter Rekursion führen, dies ist davon abhängig, wie der Handler implementiert ist.  
  
 Wenn die Eigenschaft eine benutzerdefinierte Abhängigkeitseigenschaft ist, oder wenn Sie eine abgeleitete Klasse arbeiten, in dem Sie den Instanziierungscode festgelegt haben, ein viel besserer Mechanismus zum Nachverfolgen von Änderungen von Eigenschaften, die ist in integrierten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaftensystem: die Eigenschaftensystemrückrufen <xref:System.Windows.CoerceValueCallback> und <xref:System.Windows.PropertyChangedCallback>. Weitere Informationen über die Verwendung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystems für die Überprüfung und Koersion, finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](dependency-property-callbacks-and-validation.md) und [Benutzerdefinierten Abhängigkeitseigenschaften](custom-dependency-properties.md).  
  
### <a name="dependencypropertychanged-events"></a>Abhängigkeitseigenschaftsänderungs-Ereignisse  
 Ist ein weiteres Paar von Typen, die Teil einer Eigenschaftenänderungsereignis-Szenarios sind <xref:System.Windows.DependencyPropertyChangedEventArgs> und <xref:System.Windows.DependencyPropertyChangedEventHandler>. Ereignisse für diese Eigenschaftenänderungen werden nicht weitergeleitet; Sie sind [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Standardereignisse. <xref:System.Windows.DependencyPropertyChangedEventArgs> ist ein ungewöhnlicher ereignisdatenberichts geben, da es nicht von abgeleitet ist <xref:System.EventArgs>; <xref:System.Windows.DependencyPropertyChangedEventArgs> ist eine Struktur, die keine Klasse.  
  
 Ereignisse, mit denen <xref:System.Windows.DependencyPropertyChangedEventArgs> und <xref:System.Windows.DependencyPropertyChangedEventHandler> werden häufiger auf als `RoutedPropertyChanged` Ereignisse. Ein Beispiel für ein Ereignis, das diese Typen verwendet ist <xref:System.Windows.UIElement.IsMouseCapturedChanged>.  
  
 Wie <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, <xref:System.Windows.DependencyPropertyChangedEventArgs> meldet ebenfalls einen alten und neuen Wert für die Eigenschaft. Außerdem gelten die gleichen Überlegungen dazu, was Sie mit den Werten tun können; im Allgemeinen ist es nicht empfehlenswert, dass Sie versuchen, die Werte für den Absender als Antwort auf das Ereignis erneut zu ändern.  
  
## <a name="property-triggers"></a>Eigenschaftsauslöser  
 Ein eng mit einem Eigenschaftenänderungsereignis verbundenes Konzept ist ein Eigenschaftsauslöser. Ein Eigenschaftsauslöser wird innerhalb eines Stils oder einer Vorlage erstellt und ermöglicht es Ihnen, ein bedingtes Verhalten basierend auf dem Wert der Eigenschaft zu erstellen, in dem der Eigenschaftsauslöser zugeordnet ist.  
  
 Die Eigenschaft für einen Eigenschaftsauslöser muss eine Abhängigkeitseigenschaft sein. Es kann (und ist häufig) eine schreibgeschützte Abhängigkeitseigenschaft sein. Ein guter Indikator für den Fall, dass eine Abhängigkeitseigenschaft von einem Steuerelement verfügbar gemacht wird, ist zumindest teilweise konzipiert, um ein Eigenschaftsauslöser zu sein, wenn der Eigenschaftsname mit „Is“ beginnt. Eigenschaften, die diese Namen tragen, sind häufig schreibgeschützte boolesche Abhängigkeitseigenschaften, in denen das primäre Szenario für die Eigenschaft den Steuerelementzustand meldet, der möglicherweise Konsequenzen für die Benutzeroberfläche in Echtzeit hat und sich somit als Eigenschaftsauslöserkandidat eignet.  
  
 Einige dieser Eigenschaften können auch ein dediziertes Eigenschaftenänderungsereignis haben. Beispielsweise die Eigenschaft <xref:System.Windows.UIElement.IsMouseCaptured%2A> verfügt über ein Eigenschaftenänderungsereignis <xref:System.Windows.UIElement.IsMouseCapturedChanged>. Die Eigenschaft selbst ist schreibgeschützt, wobei des Werts durch das Eingabesystem angepasst, und das Eingabesystem löst <xref:System.Windows.UIElement.IsMouseCapturedChanged> auf jeder Änderung in Echtzeit.  
  
 Im Vergleich zu einem echten Eigenschaftenänderungsereignis, das einen Eigenschaftsauslöser verwendet, um eine Eigenschaftenänderung zu bearbeiten, gelten hier einige Einschränkungen.  
  
 Eigenschaftsauslöser funktionieren durch eine genaue Übereinstimmungslogik. Sie legen eine Eigenschaft und einen Wert fest, die den spezifischen Wert angeben für den der Auslöser agiert. Zum Beispiel: `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`. Aufgrund dieser Einschränkung werden die meisten Eigenschaftsauslöser für boolesche Eigenschaften verwendet oder für Eigenschaften, die einen dedizierten Enumerationswert haben, wobei der mögliche Wertebereich überschaubar genug ist, um einen Auslöser für jeden Fall festzulegen. Eigenschaftsauslöser können nur für spezielle Werte vorhanden sein, z.B. wenn die Elementanzahl 0 erreicht, und keine Auslöser vorhanden sind, die Rechenschaft für die Fälle ablegen, wenn der Eigenschaftswert sich erneut von 0 entfernt (an Stelle von Auslösern benötigen Sie hier für alle Fälle ggf. einen Code-Ereignishandler oder ein Standardverhalten, das vom Auslöserstatus erneut zurückschaltet, wenn der Wert ungleich 0 ist).  
  
 Die Syntax der Eigenschaftsauslöser entspricht einer „if“-Anweisung in der Programmierung. Wenn die Auslöserbedingung echt ist, wird der „Textkörper“ des Eigenschaftsauslösers „ausgeführt“. Der „Textkörper“ von einem Eigenschaftsauslöser ist kein Code, sondern ein Markup. Das Markup ist beschränkt, die mit einem oder mehreren <xref:System.Windows.Setter> Elemente festlegen anderer Eigenschaften des Objekts, auf der Stil oder die Vorlage angewendet wird.  
  
 Um die "If"-Bedingung eines eigenschaftsauslösers, die eine Vielzahl von möglichen Werten verfügt, ist es generell ratsam, diesen Eigenschaftswert auf einen Standardwert festgelegt, mit einem <xref:System.Windows.Setter>. Auf diese Weise die <xref:System.Windows.Trigger> enthaltene Setter Vorrang haben, wenn die auslöserbedingung auf true festgelegt ist und die <xref:System.Windows.Setter> , die sich nicht innerhalb einer <xref:System.Windows.Trigger> wird Vorrang haben, wenn die auslöserbedingung falsch ist.  
  
 Eigenschaftsauslöser eigenen sich im Allgemeinen für Szenarios, in denen eine oder mehrere Darstellungseigenschaften sich basierend auf dem Zustand einer anderen Eigenschaft auf dem selben Element ändern sollten.  
  
 Weitere Informationen zu Eigenschaftsauslösern finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
