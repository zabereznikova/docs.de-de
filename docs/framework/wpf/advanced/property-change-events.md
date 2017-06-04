---
title: "Eigenschaften&#228;nderungsereignisse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Änderungsereignisse [WPF], Eigenschaft"
  - "Erstellen von Eigenschaftentriggern [WPF]"
  - "Abhängigkeitseigenschaften [WPF], Änderungsereignisse"
  - "Ereignisse [WPF], Änderung in Eigenschaftswerten"
  - "Identifizieren von geänderten Eigenschaftenereignissen [WPF]"
  - "Eigenschaftenänderungsereignisse [WPF]"
  - "Eigenschaftenänderungsereignisse [WPF], Typen"
  - "Eigenschaftentrigger [WPF]"
  - "Eigenschaftentrigger [WPF], Definition von"
  - "Eigenschaftswertänderungen [WPF]"
ms.assetid: 0a7989df-9674-4cc1-bc50-5d8ef5d9c055
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Eigenschaften&#228;nderungsereignisse
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] definiert mehrere Ereignisse, die bei einer Änderung eines Eigenschaftswerts ausgelöst werden.  Häufig handelt es sich hierbei im eine [Abhängigkeitseigenschaft](GTMT).  Das Ereignis ist entweder ein [Routingereignis](GTMT) oder ein [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Standardereignis.  Die Definition des Ereignisses variiert je nach Szenario, da einige Eigenschaftenänderungen besser durch eine Elementstruktur weitergeleitet werden, während andere Eigenschaftenänderungen zumeist nur für das Objekt, für das die Eigenschaft geändert wurde, relevant sind.  
  
## Identifizieren eines Eigenschaftenänderungsereignisses  
 Nicht alle Ereignisse, die eine Eigenschaftenänderung kennzeichnen, werden durch ein Signaturmuster oder Benennungsschema explizit als Eigenschaftenänderungsereignis identifiziert.  Die Beschreibung des Ereignisses in der [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]\-Dokumentation gibt in der Regel an, ob das Ereignis unmittelbar mit der Änderung eines Eigenschaftswerts verbunden ist. Weiterhin enthält sie Querverweise zwischen der Eigenschaft und dem Ereignis.  
  
### RoutedPropertyChanged\-Ereignisse  
 Bestimmte Ereignisse verwenden einen Ereignisdatentyp und einen Delegat, die speziell für Eigenschaftenänderungsereignisse verwendet werden.  Der Ereignisdatentyp ist <xref:System.Windows.RoutedPropertyChangedEventArgs%601>, und der Delegat ist <xref:System.Windows.RoutedPropertyChangedEventHandler%601>.  Die Ereignisdaten und der Delegat verfügen beide über einen allgemeinen Typparameter, mit dem der Typ der geänderten Eigenschaft bei der Definition des Handlers angegeben wird.  Die Ereignisdaten enthalten zwei Eigenschaften, <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> und <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, die beide als Typargument in den Ereignisdaten übergeben werden.  
  
 Der "Routed"\-Teil des Namens kennzeichnet, dass das Eigenschaftenänderungsereignis als Routingereignis registriert wird.  Der Vorteil beim Routing eines Eigenschaftenänderungsereignisses besteht darin, dass die übergeordnete Ebene eines Steuerelements Eigenschaftenänderungsereignisse empfangen kann, wenn die Eigenschaftswerte von untergeordneten Elementen \(Komponenten des Steuerelements\) geändert werden.  Sie können beispielsweise ein Steuerelement erstellen, das ein <xref:System.Windows.Controls.Primitives.RangeBase>\-Steuerelement enthält, z. B. <xref:System.Windows.Controls.Slider>.  Wenn sich der Wert der <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>\-Eigenschaft für den Schieberegler ändert, können Sie die Änderung auf dem übergeordneten Steuerelement, anstatt auf der Schiebereglerkomponente verarbeiten.  
  
 Da Sie hierdurch über einen vorherigen und einen neuen Wert verfügen, läge es nahe, diesen Ereignishandler zum Überprüfen des Eigenschaftswerts zu nutzen.  Dies ist jedoch nicht der Zweck von Eigenschaftenänderungsereignissen.  In der Regel werden die Werte bereitgestellt, damit Sie diese in anderen logischen Bereichen des Codes verwenden können. Es ist jedoch nicht ratsam, die Werte innerhalb des Ereignishandlers zu ändern. Dies könnte je nach Implementierung des Handlers eine unbeabsichtigte Rekursion zur Folge haben.  
  
 Wenn es sich bei der Eigenschaft um eine benutzerdefinierte Abhängigkeitseigenschaft handelt oder wenn Sie eine abgeleitete Klasse verwenden, in der Sie den Code zum Instanziieren definiert haben, ist ein wesentlich effektiverer Mechanismus zum Verfolgen von Eigenschaftenänderungen verfügbar, der in das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystem integriert ist: die Eigenschaftensystemrückrufe <xref:System.Windows.CoerceValueCallback> und <xref:System.Windows.PropertyChangedCallback>.  Weitere Informationen über die Verwendung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Eigenschaftensystems für Validierung und Koersion finden Sie unter [Rückrufe und Validierung von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md) und [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
### DependencyPropertyChanged\-Ereignisse  
 Zwei weitere Typen, die im Szenario für Eigenschaftenänderungsereignisse zum Einsatz kommen, sind <xref:System.Windows.DependencyPropertyChangedEventArgs> und <xref:System.Windows.DependencyPropertyChangedEventHandler>.  Die Ereignisse für diese Eigenschaftenänderungen werden nicht weitergeleitet. Es handelt sich hierbei um [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Standardereignisse.  <xref:System.Windows.DependencyPropertyChangedEventArgs> ist ein spezieller Berichterstellungstyp für Ereignisdaten, da dieser nicht von <xref:System.EventArgs> abgeleitet wird. <xref:System.Windows.DependencyPropertyChangedEventArgs> ist eine Struktur, keine Klasse.  
  
 Ereignisse, die <xref:System.Windows.DependencyPropertyChangedEventArgs> und <xref:System.Windows.DependencyPropertyChangedEventHandler> verwenden, treten häufiger auf als `RoutedPropertyChanged`\-Ereignisse.  Ein Beispiel für ein Ereignis, das diese Typen verwendet, ist <xref:System.Windows.UIElement.IsMouseCapturedChanged>.  
  
 <xref:System.Windows.DependencyPropertyChangedEventArgs> gibt ebenso wie <xref:System.Windows.RoutedPropertyChangedEventArgs%601> einen vorherigen und einen neuen Wert für die Eigenschaft zurück.  Für die Verwendung der Werte gilt das Gleiche. Es wird davon abgeraten, diese Werte als Reaktion auf ein Ereignis am Sender zu ändern.  
  
## Eigenschaftentrigger  
 Eigenschaftentrigger sind eng mit dem Konzept der Eigenschaftenänderungsereignisse verbunden.  Eigenschaftentrigger werden innerhalb eines Formats oder einer Vorlage erstellt und ermöglichen Ihnen, basierend auf dem Wert der Eigenschaft, der der Eigenschaftentrigger zugeordnet ist, ein bedingtes Verhalten zu definieren.  
  
 Die Eigenschaft für einen Eigenschaftentrigger muss eine Abhängigkeitseigenschaft sein.  Hierbei handelt es sich häufig um eine schreibgeschützte Abhängigkeitseigenschaft.  Einen Hinweis darüber, ob eine von einem Steuerelement verfügbar gemachte Abhängigkeitseigenschaft zumindest teilweise als Eigenschaftentrigger konzipiert wurde, liefert der Eigenschaftenname, wenn dieser mit "Is" beginnt.  Eigenschaften mit einem solchen Namen sind häufig schreibgeschützte boolesche Abhängigkeitseigenschaften. Das Hauptszenario für die Eigenschaft ist, den Steuerelementzustand zu berichten, der sich auf die Echtzeitbenutzeroberfläche auswirken kann und somit ein möglicher Eigenschaftentrigger ist.  
  
 Einige dieser Eigenschaften verfügen zudem über ein dediziertes Eigenschaftenänderungsereignis.  Die Eigenschaft <xref:System.Windows.UIElement.IsMouseCaptured%2A> verfügt beispielsweise über das Eigenschaftenänderungsereignis <xref:System.Windows.UIElement.IsMouseCapturedChanged>.  Die Eigenschaft selbst ist schreibgeschützt, wobei der Wert durch das Eingabesystem angepasst wird. Das Eingabesystem löst dann für jede Echtzeitänderung <xref:System.Windows.UIElement.IsMouseCapturedChanged> aus.  
  
 Die Verwendung eines Eigenschaftentriggers für eine Eigenschaftenänderung ist im Vergleich mit einem echten Eigenschaftenänderungsereignis mit Einschränkungen verbunden.  
  
 Eigenschaftentrigger basieren auf einer Logik mit genauen Übereinstimmungen.  Sie geben dabei eine Eigenschaft und einen genauen Wert an, bei dem der Trigger reagiert.  Beispiel: `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`.  Aufgrund dieser Einschränkung werden Eigenschaftentrigger zumeist für boolesche Eigenschaften oder Eigenschaften mit einem dedizierten Enumerationswert verwendet, bei denen der mögliche Wertebereich überschaubar genug ist, um einen Trigger für jeden Fall zu definieren.  Zudem können Eigenschaftentrigger nur für spezifische Werte angegeben werden, z. B. wenn die Elementanzahl den Wert Null erreicht, wobei kein Trigger für Fälle verfügbar ist, in denen der Eigenschaftswert ungleich Null ist \(hier benötigen Sie anstelle eines Triggers für jeden Einzelfall ggf. einen Code\-Ereignishandler oder ein Standardverhalten, das bei einem Wert ungleich Null wiederhergestellt wird\).  
  
 Die Syntax des Eigenschaftentriggers entspricht einer "if"\-Anweisung beim Programmieren.  Wenn die Triggerbedingung zutrifft \(true\), wird der "Inhalt" des Eigenschaftentriggers "ausgeführt".  Der "Inhalt" eines Eigenschaftentriggers ist dabei kein Code, sondern Markup.  Das Markup ist auf die Verwendung von einem oder mehreren <xref:System.Windows.Setter>\-Elementen beschränkt, um andere Eigenschaften des Objekts festzulegen, auf die das Format oder die Vorlage angewendet wird.  
  
 Um die "if"\-Bedingung eines Eigenschaftentriggers, der eine Vielzahl potenzieller Werte zulässt, zu versetzen, sollten Sie für diesen Eigenschaftswert mithilfe eines <xref:System.Windows.Setter> eine Standardeinstellung festlegen.  Ein im <xref:System.Windows.Trigger> enthaltener Setter hat in diesem Fall Vorrang, wenn die Triggerbedingung zutrifft \(true\). Ein <xref:System.Windows.Setter>, der sich nicht innerhalb eines <xref:System.Windows.Trigger> befindet, hat Vorrang, wenn die Triggerbedingung nicht zutrifft \(false\).  
  
 Eigenschaftentrigger eignen sich in der Regel für Szenarien, in denen sich mindestens eine Darstellungseigenschaft basierend auf dem Zustand einer anderen Eigenschaft im gleichen Element ändern soll.  
  
 Weitere Informationen zu Eigenschaftentriggern finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
## Siehe auch  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)