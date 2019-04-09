---
title: Schreibgeschützte Abhängigkeitseigenschaften
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: 45385e3e3eb8e756008a0d9ef560e061f9a31964
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162422"
---
# <a name="read-only-dependency-properties"></a>Schreibgeschützte Abhängigkeitseigenschaften
Dieses Thema beschreibt die schreibgeschützten Abhängigkeitseigenschaften, einschließlich vorhandener schreibgeschützter Abhängigkeitseigenschaften und die Szenarien und Verfahren zum Erstellen einer benutzerdefinierten, schreibgeschützten Abhängigkeitseigenschaft.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Bei diesem Thema wird davon ausgegangen, dass Sie die grundlegenden Szenarien zum Implementieren einer Abhängigkeitseigenschaft verstehen, und Metadaten für eine benutzerdefinierte Abhängigkeitseigenschaft anwenden. Mehr dazu finden Sie unter [benutzerdefinierten Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
<a name="existing"></a>   
## <a name="existing-read-only-dependency-properties"></a>Bestehende schreibgeschützte Abhängigkeitseigenschaften  
 Einige der Abhängigkeitseigenschaften, die im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Framework festgelegt sind, sind schreibgeschützt. Der Hauptgrund zum Festlegen einer schreibgeschützten Abhängigkeitseigenschaft ist, dass dies Eigenschaften sind, die zur Statusbestimmung verwendet werden sollen, allerdings wird dieser Status durch eine Vielzahl von Faktoren beeinflusst, wobei das einfache Festlegen der Eigenschaft in diesem Status aus der Perspektive des Benutzeroberflächendesigns nicht in Frage kommt. Beispiel: die Eigenschaft <xref:System.Windows.UIElement.IsMouseOver%2A> ist nur ein Oberflächenstatus, die durch die Mauseingabe festgelegt. dann wäre jeder Versuch, diesen Wert programmgesteuert - durch die Umgehung der echten Mauseingabe - festzulegen, unvorhersehbar und würde zu einer Inkonsistenz führen.  
  
 Schreibgeschützte Abhängigkeitseigenschaften sind nicht für zahlreiche Szenarien geeignet, für die Abhängigkeitseigenschaften normalerweise eine Lösung bieten, da sie nicht eingestellt werden können (genauer gesagt: Datenbindung, direkt auf einen Wert formatierbar, Überprüfung, Animation, Vererbung). Obwohl Sie nicht eingestellt werden können, verfügen schreibgeschützte Abhängigkeitseigenschaft immer noch über einige weitere Funktionen, die von Abhängigkeitseigenschaften im Eigenschaftssystem unterstützt werden. Die wichtigste verbleibende Funktion ist, dass die schreibgeschützte Abhängigkeitseigenschaft weiterhin als Eigenschaftstrigger in einem Stil verwendet werden kann. Sie können Auslöser nicht mit einer normalen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Eigenschaft aktivieren. Dies muss mit einer Abhängigkeitseigenschaft geschehen. Die oben genannte <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft ist ein perfektes Beispiel für ein Szenario, in denen es möglicherweise sehr hilfreich sein, definieren Sie einen Stil für ein Steuerelement, einige, sichtbare Eigenschaften wie Hintergrund, Vordergrund oder ähnliche Eigenschaften zusammengesetzter Elemente innerhalb der Steuerelement ändert, wenn der Benutzer den Mauszeiger über einen definierten Bereich des Steuerelements führt. Änderungen in einer schreibgeschützten Abhängigkeitseigenschaft können auch ermittelt und durch den inhärenten Ungültigkeitsprozess des Eigenschaftssystems gemeldet werden, und dies unterstützt in der Tat intern die Eigenschaftsauslöserfunktionalität.  
  
<a name="new"></a>   
## <a name="creating-custom-read-only-dependency-properties"></a>Erstellen benutzerdefinierter, schreibgeschützter Abhängigkeitseigenschaften  
 Lesen Sie auf jeden Fall den Abschnitt oben zum Thema: Warum schreibgeschützte Abhängigkeitseigenschaften für viele normale Abhängigkeitseigenschaftsszenarien nicht funktioniert. Wenn Sie ein entsprechendes Szenario haben, können Sie jedoch eine eigene schreibgeschützte Abhängigkeitseigenschaft erstellen.  
  
 Einiges des Prozesses zum Erstellen einer schreibgeschützten Abhängigkeitseigenschaft entspricht weitgehend den in [benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Implementieren einer Abhängigkeitseigenschaft](how-to-implement-a-dependency-property.md) beschriebenen Themen. Es gibt drei wichtige Unterschiede:  
  
-   Wenn die Eigenschaft registrieren, rufen Sie die <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> Methode anstelle der normalen <xref:System.Windows.DependencyProperty.Register%2A> -Methode für die Registrierung.  
  
-   Stellen Sie bei der Implementierung der [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-„Wrapper“-Eigenschaft sicher, dass auch der Wrapper keine festgelegte Implementierung hat, sodass keine Inkonsistenzen im schreibgeschützten Status für den öffentlichen Wrapper entstehen, den Sie verfügbar machen.  
  
-   Die von der schreibgeschützten Registrierung zurückgegebene Objekt ist <xref:System.Windows.DependencyPropertyKey> statt <xref:System.Windows.DependencyProperty>. Speichern Sie dieses Feld weiterhin als Member, aber normalerweise sollten Sie es nicht zu einem öffentlichen Member des Typs machen.  
  
 Alle privaten Felder oder Werte, die Ihre schreibgeschützte Abhängigkeitseigenschaft unterstützen, können natürlich vollständig von Ihrer gewünschten Logik beschreibbar sein. Die einfachste Möglichkeit zum Festlegen der Eigenschaft, ob am Anfang oder als Teil der Laufzeitlogik, ist jedoch das Verwenden des Eigenschaftensystems [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], anstatt das Eigenschaftensystem zu umgehen und das private Unterstützungsfeld direkt festzulegen. Es ist eine Signatur der <xref:System.Windows.DependencyObject.SetValue%2A> nimmt einen Parameter vom Typ <xref:System.Windows.DependencyPropertyKey>. Wie und wo Sie diesen Wert programmgesteuert in der Anwendungslogik festlegen wirkt sich wie Sie möchten möglicherweise legen Sie den Zugriff auf die <xref:System.Windows.DependencyPropertyKey> erstellt, wenn Sie die Abhängigkeitseigenschaft zuerst registriert. Wenn Sie diese Logik innerhalb der Klasse bearbeiten, können Sie diese als privat einstellen, oder wenn Sie möchten, dass diese von anderen Teilen des Assembly festgelegt wird, müssen Sie dies intern festlegen. Ein Ansatz besteht darin, rufen Sie <xref:System.Windows.DependencyObject.SetValue%2A> innerhalb eines klassenereignishandlers eines relevanten Ereignisses, das eine Klasseninstanz darüber informiert, die der gespeicherte Eigenschaftswert geändert werden muss. Ein anderer Ansatz ist, um Abhängigkeitseigenschaften zu verbinden, mit der gekoppelt <xref:System.Windows.PropertyChangedCallback> und <xref:System.Windows.CoerceValueCallback> Rückrufen als Teil der Metadaten dieser Eigenschaften während der Registrierung.  
  
 Da die <xref:System.Windows.DependencyPropertyKey> privat ist und nicht weitergegeben wird vom Eigenschaftensystem außerhalb des Codes, eine schreibgeschützte Abhängigkeitseigenschaft besitzt eine bessere einstellungssicherheit, als eine Abhängigkeitseigenschaft mit Lese-/ Schreibzugriff. Für eine Abhängigkeitseigenschaft, die gelesen und bearbeitet werden kann, ist das identifizierende Feld explizit oder implizit öffentlich und daher kann die Eigenschaft umfassend festgelegt werden. Ausführlichere Informationen dazu finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
