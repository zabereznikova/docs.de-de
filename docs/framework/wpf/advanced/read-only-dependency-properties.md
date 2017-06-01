---
title: "Schreibgesch&#252;tzte Abh&#228;ngigkeitseigenschaften | Microsoft Docs"
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
  - "Abhängigkeitseigenschaften, Schreibgeschützt"
  - "Schreibgeschützte Abhängigkeitseigenschaften"
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Schreibgesch&#252;tzte Abh&#228;ngigkeitseigenschaften
In diesem Thema werden die schreibgeschützten Abhängigkeitseigenschaften, einschließlich vorhandener schreibgeschützter Eigenschaften, sowie die Szenarien und Methoden zum Erstellen einer benutzerdefinierten, schreibgeschützten Abhängigkeitseigenschaft beschrieben.  
  
   
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie mit den grundlegenden Szenarien zum Implementieren einer Abhängigkeitseigenschaft und dem Anwenden von Metadaten auf eine benutzerdefinierte Abhängigkeitseigenschaft vertraut sind.  Weitere Kontextinformationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) und [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="existing"></a>   
## Vorhandene schreibgeschützte Abhängigkeitseigenschaften  
 Einige der Abhängigkeitseigenschaften, die im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Framework definiert werden, sind schreibgeschützt.  Der Hauptgrund zum Festlegen einer schreibgeschützten Abhängigkeitseigenschaft ist der, dass dies Eigenschaften sind, die zur Statusermittlung verwendet werden sollten. Wenn der Status jedoch von zahlreichen Faktoren beeinflusst wird, ist es aus Sicht des Benutzeroberflächenentwurfs nicht wünschenswert, die Eigenschaft einfach auf diesen Wert festzulegen.  So ist die <xref:System.Windows.UIElement.IsMouseOver%2A>\-Eigenschaft nur ein Oberflächenstatus, wie durch die Mauseingabe definiert.  Jeder Versuch, diesen Wert programmgesteuert festzulegen, indem die eigentliche Mauseingabe umgangen wird, hat unvorhergesehene Auswirkungen und führt zu Inkonsistenzen.  
  
 Da sie nicht festgelegt werden können, sind schreibgeschützte Abhängigkeitseigenschaften für zahlreiche Szenarien, in denen Abhängigkeitseigenschaften normalerweise eine Lösung bieten, nicht geeignet \(Datenbindung, direkt nach einem Wert formatierbar, Validierung, Animation, Vererbung\).  Obwohl sie nicht festgelegt werden können, verfügen schreibgeschützte Abhängigkeitseigenschaften trotzdem über einige der zusätzlichen Funktionen, die von Abhängigkeitseigenschaften im Eigenschaftensystem unterstützt werden.  Die wichtigste verbleibende Funktion ist die, dass schreibgeschützte Abhängigkeitseigenschaften weiterhin als Eigenschaftentrigger in einem Stil verwendet werden können.  Sie können keine Trigger mit einer normalen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Eigenschaft aktivieren; es muss sich um eine Abhängigkeitseigenschaft handeln.  Die zuvor bereits erwähnte <xref:System.Windows.UIElement.IsMouseOver%2A>\-Eigenschaft ist ein gutes Beispiel für ein Szenario, in dem es nützlich sein kann, einen Stil für ein Steuerelement zu definieren, bei dem sich einige sichtbare Eigenschaften wie Hintergrund, Vordergrund oder ähnliche Eigenschaften zusammengesetzter Elemente im Steuerelement ändern, wenn der Benutzer den Mauszeiger über einen definierten Bereich des Steuerelements führt.  Änderungen schreibgeschützter Abhängigkeitseigenschaften können auch erkannt und vom inhärenten Ungültigkeitsprozess des Eigenschaftensystems protokolliert werden, wobei dies auch die Eigenschaftentriggerfunktion intern unterstützt.  
  
<a name="new"></a>   
## Erstellen von benutzerdefinierten schreibgeschützten Abhängigkeitseigenschaften  
 Lesen Sie unbedingt den Abschnitt weiter oben, in dem erläutert wird, warum schreibgeschützte Abhängigkeitseigenschaften in zahlreichen herkömmlichen Szenarien für Abhängigkeitseigenschaften nicht funktionieren.  Wenn Sie jedoch über ein passendes Szenario verfügen, können Sie Ihre eigene schreibgeschützte Abhängigkeitseigenschaft erstellen.  
  
 Das Verfahren zum Erstellen einer schreibgeschützten Abhängigkeitseigenschaft entspricht weitgehend den unter [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) und [Implementieren einer Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) beschriebenen Verfahren.  Es gibt jedoch drei wichtige Unterschiede:  
  
-   Rufen Sie beim Registrieren der Eigenschaft die <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>\-Methode statt der normalen <xref:System.Windows.DependencyProperty.Register%2A>\-Methode für die Eigenschaftenregistrierung auf.  
  
-   Stellen Sie beim Implementieren der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Wrappereigenschaft sicher, dass auch der Wrapper nicht über eine festgelegte Implementierung verfügt, damit keine Inkonsistenz beim schreibgeschützten Status für den von Ihnen bereitgestellten öffentlichen Wrapper besteht.  
  
-   Das von der schreibgeschützten Registrierung zurückgegebene Objekt ist <xref:System.Windows.DependencyPropertyKey> statt <xref:System.Windows.DependencyProperty>.  Sie sollten dieses Feld trotzdem als Member speichern, wobei Sie es in der Regel jedoch nicht als öffentlichen Member des Typs festlegen.  
  
 Das private Feld oder der Wert, das bzw. der der schreibgeschützten Eigenschaft zugrunde liegt, kann jedoch mit der von Ihnen gewünschten Logik jederzeit bearbeitet werden.  Die Eigenschaft lässt sich jedoch am einfachsten anfänglich oder als Teil der Laufzeitlogik festlegen, indem die [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] des Eigenschaftensystems verwendet werden, statt das Eigenschaftensystem zu umgehen und das private zugrunde liegende Feld direkt festzulegen.  Es gibt insbesondere eine Signatur von <xref:System.Windows.DependencyObject.SetValue%2A>, die einen Parameter des <xref:System.Windows.DependencyPropertyKey>\-Typs verwendet.  Wie und wo Sie diesen Wert programmatisch in der Anwendungslogik festlegen, hat Auswirkungen darauf, wie Sie den Zugriff auf den <xref:System.Windows.DependencyPropertyKey> angeben, der bei der ersten Registrierung der Abhängigkeitseigenschaft erstellt wurde.  Wenn Sie diese Logik nur in der Klasse behandeln, können Sie sie als privat festlegen; wenn sie jedoch aus anderen Teilen der Assembly festgelegt werden soll, können Sie sie als intern festlegen.  Eine Vorgehensweise besteht darin, <xref:System.Windows.DependencyObject.SetValue%2A> in einem Klassenereignishandler eines relevanten Ereignisses aufzurufen, der eine Klasseninstanz darüber informiert, dass der gespeicherte Eigenschaftswert geändert werden muss.  Eine andere Vorgehensweise ist, die Abhängigkeitseigenschaften durch die Verwendung eines Rückrufpaars, das aus <xref:System.Windows.PropertyChangedCallback> und <xref:System.Windows.CoerceValueCallback> besteht, als Teil der Eigenschaftenmetadaten während der Registrierung zu verbinden.  
  
 Da der <xref:System.Windows.DependencyPropertyKey> privat ist und nicht durch das Eigenschaftensystem außerhalb des Codes weitergegeben wird, verfügt eine schreibgeschützte Abhängigkeitseigenschaft über eine bessere Festlegungssicherheit als eine Abhängigkeitseigenschaft mit Lese\-\/Schreibzugriff.  Bei einer Abhängigkeitseigenschaft mit Lese\-\/Schreibzugriff ist das identifizierende Feld explizit oder implizit öffentlich, sodass die Eigenschaft umfassend festgelegt werden kann.  Ausführlichere Informationen finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
## Siehe auch  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)