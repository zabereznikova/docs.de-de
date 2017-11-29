---
title: "Schreibgeschützte Abhängigkeitseigenschaften"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9cb4477fe388c294bbd6b87589d5a3108a90d27f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="read-only-dependency-properties"></a>Schreibgeschützte Abhängigkeitseigenschaften
Dieses Thema beschreibt die schreibgeschützten Abhängigkeitseigenschaften, einschließlich vorhandener schreibgeschützter Abhängigkeitseigenschaften und die Szenarien und Verfahren zum Erstellen einer benutzerdefinierten, schreibgeschützten Abhängigkeitseigenschaft.  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Bei diesem Thema wird davon ausgegangen, dass Sie die grundlegenden Szenarien zum Implementieren einer Abhängigkeitseigenschaft verstehen, und Metadaten für eine benutzerdefinierte Abhängigkeitseigenschaft anwenden. Mehr dazu finden Sie unter [benutzerdefinierten Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) und [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="existing"></a>   
## <a name="existing-read-only-dependency-properties"></a>Bestehende schreibgeschützte Abhängigkeitseigenschaften  
 Einige der Abhängigkeitseigenschaften, die im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Framework festgelegt sind, sind schreibgeschützt. Der Hauptgrund zum Festlegen einer schreibgeschützten Abhängigkeitseigenschaft ist, dass dies Eigenschaften sind, die zur Statusbestimmung verwendet werden sollen, allerdings wird dieser Status durch eine Vielzahl von Faktoren beeinflusst, wobei das einfache Festlegen der Eigenschaft in diesem Status aus der Perspektive des Benutzeroberflächendesigns nicht in Frage kommt. Beispielsweise die Eigenschaft <xref:System.Windows.UIElement.IsMouseOver%2A> ist genau genommen nur Zustand versetzt, wie durch die Mauseingabe einbringen. dann wäre jeder Versuch, diesen Wert programmgesteuert - durch die Umgehung der echten Mauseingabe - festzulegen, unvorhersehbar und würde zu einer Inkonsistenz führen.  
  
 Schreibgeschützte Abhängigkeitseigenschaften sind nicht für zahlreiche Szenarien geeignet, für die Abhängigkeitseigenschaften normalerweise eine Lösung bieten, da sie nicht eingestellt werden können (genauer gesagt: Datenbindung, direkt auf einen Wert formatierbar, Überprüfung, Animation, Vererbung). Obwohl Sie nicht eingestellt werden können, verfügen schreibgeschützte Abhängigkeitseigenschaft immer noch über einige weitere Funktionen, die von Abhängigkeitseigenschaften im Eigenschaftssystem unterstützt werden. Die wichtigste verbleibende Funktion ist, dass die schreibgeschützte Abhängigkeitseigenschaft weiterhin als Eigenschaftstrigger in einem Stil verwendet werden kann. Sie können Auslöser nicht mit einer normalen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaft aktivieren. Dies muss mit einer Abhängigkeitseigenschaft geschehen. Die oben genannte <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft ist ein gutes Beispiel für ein Szenario, in denen ist es möglicherweise sehr hilfreich, um einen Stil für ein Steuerelement zu definieren, einige, visible-Eigenschaft, z. B. einen Hintergrund, Vordergrund oder ähnliche Eigenschaften zusammengesetzter Elemente innerhalb der Steuerelement ändert sich, wenn der Benutzer die Maus über einen definierten Bereich des Steuerelements platziert. Änderungen in einer schreibgeschützten Abhängigkeitseigenschaft können auch ermittelt und durch den inhärenten Ungültigkeitsprozess des Eigenschaftssystems gemeldet werden, und dies unterstützt in der Tat intern die Eigenschaftsauslöserfunktionalität.  
  
<a name="new"></a>   
## <a name="creating-custom-read-only-dependency-properties"></a>Erstellen benutzerdefinierter, schreibgeschützter Abhängigkeitseigenschaften  
 Lesen Sie auf jeden Fall den Abschnitt oben zum Thema: Warum schreibgeschützte Abhängigkeitseigenschaften für viele normale Abhängigkeitseigenschaftsszenarien nicht funktioniert. Wenn Sie ein entsprechendes Szenario haben, können Sie jedoch eine eigene schreibgeschützte Abhängigkeitseigenschaft erstellen.  
  
 Einiges des Prozesses zum Erstellen einer schreibgeschützten Abhängigkeitseigenschaft entspricht weitgehend den in [benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) und [Implementieren einer Abhängigkeitseigenschaft](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) beschriebenen Themen. Es gibt drei wichtige Unterschiede:  
  
-   Wenn Sie eine Eigenschaft zu registrieren, rufen die <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> Methode anstelle der normalen <xref:System.Windows.DependencyProperty.Register%2A> Methode für die eigenschaftsregistrierung.  
  
-   Stellen Sie bei der Implementierung der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-„Wrapper“-Eigenschaft sicher, dass auch der Wrapper keine festgelegte Implementierung hat, sodass keine Inkonsistenzen im schreibgeschützten Status für den öffentlichen Wrapper entstehen, den Sie verfügbar machen.  
  
-   Das durch die Registrierung nur-Lese zurückgegebene Objekt stellt <xref:System.Windows.DependencyPropertyKey> statt <xref:System.Windows.DependencyProperty>. Speichern Sie dieses Feld weiterhin als Member, aber normalerweise sollten Sie es nicht zu einem öffentlichen Member des Typs machen.  
  
 Alle privaten Felder oder Werte, die Ihre schreibgeschützte Abhängigkeitseigenschaft unterstützen, können natürlich vollständig von Ihrer gewünschten Logik beschreibbar sein. Die einfachste Möglichkeit zum Festlegen der Eigenschaft, ob am Anfang oder als Teil der Laufzeitlogik, ist jedoch das Verwenden des Eigenschaftensystems [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], anstatt das Eigenschaftensystem zu umgehen und das private Unterstützungsfeld direkt festzulegen. Es ist insbesondere in eine Signatur der <xref:System.Windows.DependencyObject.SetValue%2A> , akzeptiert einen Parameter vom Typ <xref:System.Windows.DependencyPropertyKey>. Wie und wo Sie diesen Wert programmgesteuert innerhalb Ihrer Anwendungslogik festlegen wirkt sich wie Sie möchten möglicherweise legen Sie den Zugriff auf die <xref:System.Windows.DependencyPropertyKey> erstellt, wenn Sie zuerst die Abhängigkeitseigenschaft registriert. Wenn Sie diese Logik innerhalb der Klasse bearbeiten, können Sie diese als privat einstellen, oder wenn Sie möchten, dass diese von anderen Teilen des Assembly festgelegt wird, müssen Sie dies intern festlegen. Ein Ansatz besteht im Aufrufen <xref:System.Windows.DependencyObject.SetValue%2A> innerhalb einer Klasse-Ereignishandler eines entsprechenden Ereignisses, die eine Instanz der Klasse zu informieren, die der gespeicherte Eigenschaftswert geändert werden muss. Ein anderer Ansatz ist zum Verknüpfen von Abhängigkeitseigenschaften gekoppelt mit <xref:System.Windows.PropertyChangedCallback> und <xref:System.Windows.CoerceValueCallback> Rückrufen als Teil dieser Eigenschaften Metadaten während der Registrierung.  
  
 Da die <xref:System.Windows.DependencyPropertyKey> ist privat und nicht weitergegeben wird vom Eigenschaftensystem außerhalb der Code eine schreibgeschützte Abhängigkeitseigenschaft besitzt eine bessere Leistung als eine Abhängigkeitseigenschaft mit Lese-/ Schreibzugriff Festlegen der Sicherheit. Für eine Abhängigkeitseigenschaft, die gelesen und bearbeitet werden kann, ist das identifizierende Feld explizit oder implizit öffentlich und daher kann die Eigenschaft umfassend festgelegt werden. Ausführlichere Informationen dazu finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
