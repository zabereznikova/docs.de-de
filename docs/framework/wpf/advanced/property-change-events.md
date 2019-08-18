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
ms.openlocfilehash: 06056b492439531aa60becbb7bca250a439bfb68
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567421"
---
# <a name="property-change-events"></a>Eigenschaftenänderungsereignisse
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] definiert mehrere Ereignisse, die ausgelöst werden als Antwort auf eine Änderung des Werts einer Eigenschaft. Häufig ist die Eigenschaft eine Abhängigkeitseigenschaft. Das Ereignis selbst ist manchmal ein Routing Ereignis und ist manchmal ein Standard Common Language Runtime Ereignis (CLR). Die Definition des Ereignisses variiert je nach Szenario, da einige Eigenschaftenänderungen besser durch eine Elementstruktur weitergeleitet werden, während andere Eigenschaftenänderungen in der Regel nur für das Objekt von Bedeutung sind, bei dem sich die Eigenschaft geändert hat.  
  
## <a name="identifying-a-property-change-event"></a>Identifizierung eines Eigenschaftenänderungsereignisses  
 Nicht alle Ereignisse, die eine Eigenschaftenänderung melden, werden explizit als Eigenschaftenänderungsereignis identifiziert. Dies geschieht entweder durch ein Signaturmuster oder ein Namensmuster. Im Allgemeinen gibt die Beschreibung des Ereignisses in der SDK-Dokumentation an, ob das Ereignis direkt an eine Änderung des Eigenschafts Werts gebunden ist und Querverweise zwischen der Eigenschaft und dem Ereignis bereitstellt.  
  
### <a name="routedpropertychanged-events"></a>Routingeigenschaftenänderungs-Ereignisse  
 Bestimmte Ereignisse verwenden einen Ereignisdatentyp und Delegaten, die explizit für Eigenschaftenänderungsereignisse verwendet werden. Der Ereignis Datentyp ist <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, und der Delegat <xref:System.Windows.RoutedPropertyChangedEventHandler%601>ist. Die Ereignisdaten und Delegaten haben einen generischen Typparameter, der verwendet wird, um den tatsächlichen Typ der zu ändernden Eigenschaft anzugeben, wenn Sie den Handler festlegen. Die Ereignisdaten enthalten zwei Eigenschaften, <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> und <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, die beide als Typargument in den Ereignisdaten weitergegeben werden.  
  
 Der „weitergeleitete“ Teil des Namens gibt an, dass das Eigenschaftenänderungsereignis als Routingereignis registriert ist. Der Vorteil des Routings eines Eigenschaftenänderungsereignisses liegt darin, dass die oberste Ebene eines Steuerelements Eigenschaftenänderungsereignisse empfangen kann, wenn Eigenschaften von untergeordneten Elementen (zusammengesetzte Komponenten des Steuerelements) die Werte ändern. Sie können z. b. ein Steuerelement erstellen, <xref:System.Windows.Controls.Primitives.RangeBase> das ein Steuerelement <xref:System.Windows.Controls.Slider>wie eine enthält. Wenn sich der Wert der <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> -Eigenschaft im Schieberegler-Teil ändert, können Sie diese Änderung für das übergeordnete Steuerelement anstelle des-Teils verarbeiten.  
  
 Da Sie über einen vorherigen und einen neuen Wert verfügen, kann es dazu verleiten, diesen Ereignishandler als ein Validierungssteuerelement für den Eigenschaftswert zu verwenden. Allerdings ist dies nicht der Zweck der meisten Eigenschaften, die durch Ereignisse geändert wurden. Im Allgemeinen werden die Werte bereitgestellt, damit Sie diese Werte in anderen Logikbereichen Ihres Codes ausführen können, aber eigentlich ist das Ändern der Werte aus dem Ereignishandler heraus nicht empfehlenswert und kann zu unbeabsichtigter Rekursion führen, dies ist davon abhängig, wie der Handler implementiert ist.  
  
 Wenn die Eigenschaft eine benutzerdefinierte Abhängigkeits Eigenschaft ist, oder wenn Sie mit einer abgeleiteten Klasse arbeiten, in der Sie den Instanziierungscode definiert haben, gibt es einen viel besseren Mechanismus für das Nachverfolgen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschafts Änderungen, die in das Eigenschaften System integriert sind: Eigenschaften System Rückrufe <xref:System.Windows.CoerceValueCallback> und <xref:System.Windows.PropertyChangedCallback>. Weitere Informationen über die Verwendung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaftensystems für die Überprüfung und Koersion, finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](dependency-property-callbacks-and-validation.md) und [Benutzerdefinierten Abhängigkeitseigenschaften](custom-dependency-properties.md).  
  
### <a name="dependencypropertychanged-events"></a>Abhängigkeitseigenschaftsänderungs-Ereignisse  
 Ein anderes Paar von Typen, die Bestandteil eines Ereignis Szenarios <xref:System.Windows.DependencyPropertyChangedEventArgs> für die Eigenschaften Änderung sind, sind und. <xref:System.Windows.DependencyPropertyChangedEventHandler> Ereignisse für diese Eigenschafts Änderungen werden nicht weitergeleitet. Dabei handelt es sich um CLR-Standard Ereignisse. <xref:System.Windows.DependencyPropertyChangedEventArgs>ist ein ungewöhnlicher ereignisdatenberichtstyp, weil er nicht <xref:System.EventArgs>von abgeleitet ist. <xref:System.Windows.DependencyPropertyChangedEventArgs> ist eine-Struktur, keine-Klasse.  
  
 Ereignisse, die <xref:System.Windows.DependencyPropertyChangedEventArgs> und <xref:System.Windows.DependencyPropertyChangedEventHandler> verwenden, sind etwas häufiger `RoutedPropertyChanged` als Ereignisse. Ein Beispiel für ein Ereignis, das diese Typen verwendet <xref:System.Windows.UIElement.IsMouseCapturedChanged>, ist.  
  
 Wie <xref:System.Windows.RoutedPropertyChangedEventArgs%601>meldetaucheinenaltenund neuenWertfürdie-Eigenschaft.<xref:System.Windows.DependencyPropertyChangedEventArgs> Außerdem gelten die gleichen Überlegungen dazu, was Sie mit den Werten tun können; im Allgemeinen ist es nicht empfehlenswert, dass Sie versuchen, die Werte für den Absender als Antwort auf das Ereignis erneut zu ändern.  
  
## <a name="property-triggers"></a>Eigenschaftsauslöser  
 Ein eng mit einem Eigenschaftenänderungsereignis verbundenes Konzept ist ein Eigenschaftsauslöser. Ein Eigenschaftsauslöser wird innerhalb eines Stils oder einer Vorlage erstellt und ermöglicht es Ihnen, ein bedingtes Verhalten basierend auf dem Wert der Eigenschaft zu erstellen, in dem der Eigenschaftsauslöser zugeordnet ist.  
  
 Die Eigenschaft für einen Eigenschaftsauslöser muss eine Abhängigkeitseigenschaft sein. Es kann (und ist häufig) eine schreibgeschützte Abhängigkeitseigenschaft sein. Ein guter Indikator für den Fall, dass eine Abhängigkeitseigenschaft von einem Steuerelement verfügbar gemacht wird, ist zumindest teilweise konzipiert, um ein Eigenschaftsauslöser zu sein, wenn der Eigenschaftsname mit „Is“ beginnt. Eigenschaften, die diese Namen tragen, sind häufig schreibgeschützte boolesche Abhängigkeitseigenschaften, in denen das primäre Szenario für die Eigenschaft den Steuerelementzustand meldet, der möglicherweise Konsequenzen für die Benutzeroberfläche in Echtzeit hat und sich somit als Eigenschaftsauslöserkandidat eignet.  
  
 Einige dieser Eigenschaften können auch ein dediziertes Eigenschaftenänderungsereignis haben. Zum Beispiel hat die- <xref:System.Windows.UIElement.IsMouseCaptured%2A> Eigenschaft ein Ereignis <xref:System.Windows.UIElement.IsMouseCapturedChanged>für eine Eigenschaft, das geändert wurde. Die Eigenschaft selbst ist schreibgeschützt, und ihr Wert wird vom Eingabe System angepasst, und das Eingabe System <xref:System.Windows.UIElement.IsMouseCapturedChanged> löst jede echt Zeitänderung aus.  
  
 Im Vergleich zu einem echten Eigenschaftenänderungsereignis, das einen Eigenschaftsauslöser verwendet, um eine Eigenschaftenänderung zu bearbeiten, gelten hier einige Einschränkungen.  
  
 Eigenschaftsauslöser funktionieren durch eine genaue Übereinstimmungslogik. Sie legen eine Eigenschaft und einen Wert fest, die den spezifischen Wert angeben für den der Auslöser agiert. Zum Beispiel: `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`. Aufgrund dieser Einschränkung werden die meisten Eigenschaftsauslöser für boolesche Eigenschaften verwendet oder für Eigenschaften, die einen dedizierten Enumerationswert haben, wobei der mögliche Wertebereich überschaubar genug ist, um einen Auslöser für jeden Fall festzulegen. Eigenschaftsauslöser können nur für spezielle Werte vorhanden sein, z.B. wenn die Elementanzahl 0 erreicht, und keine Auslöser vorhanden sind, die Rechenschaft für die Fälle ablegen, wenn der Eigenschaftswert sich erneut von 0 entfernt (an Stelle von Auslösern benötigen Sie hier für alle Fälle ggf. einen Code-Ereignishandler oder ein Standardverhalten, das vom Auslöserstatus erneut zurückschaltet, wenn der Wert ungleich 0 ist).  
  
 Die Syntax der Eigenschaftsauslöser entspricht einer „if“-Anweisung in der Programmierung. Wenn die Auslöserbedingung echt ist, wird der „Textkörper“ des Eigenschaftsauslösers „ausgeführt“. Der „Textkörper“ von einem Eigenschaftsauslöser ist kein Code, sondern ein Markup. Dieses Markup ist auf die Verwendung eines oder mehrerer <xref:System.Windows.Setter> -Elemente beschränkt, um andere Eigenschaften des Objekts festzulegen, auf das der Stil oder die Vorlage angewendet wird.  
  
 Um die "if"-Bedingung eines Eigenschafts Auslösers zu versetzen, der über eine Vielzahl möglicher Werte verfügt, empfiehlt es sich im Allgemeinen, denselben Eigenschafts Wert mit einem <xref:System.Windows.Setter>Standardwert festzulegen. Auf diese Weise hat <xref:System.Windows.Trigger> der enthaltene Setter Vorrang, wenn die Auslöserbedingung true ist, <xref:System.Windows.Setter> und die, die nicht <xref:System.Windows.Trigger> innerhalb einer liegt, hat Vorrang, wenn die Auslöserbedingung false ist.  
  
 Eigenschaftsauslöser eigenen sich im Allgemeinen für Szenarios, in denen eine oder mehrere Darstellungseigenschaften sich basierend auf dem Zustand einer anderen Eigenschaft auf dem selben Element ändern sollten.  
  
 Weitere Informationen zu Eigenschaftsauslösern finden Sie unter [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
