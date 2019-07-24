---
title: Schreibgeschützte Abhängigkeitseigenschaften
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: aa6893b100311ead74f610dd20f327d130dff74a
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401651"
---
# <a name="read-only-dependency-properties"></a>Schreibgeschützte Abhängigkeitseigenschaften
Dieses Thema beschreibt die schreibgeschützten Abhängigkeitseigenschaften, einschließlich vorhandener schreibgeschützter Abhängigkeitseigenschaften und die Szenarien und Verfahren zum Erstellen einer benutzerdefinierten, schreibgeschützten Abhängigkeitseigenschaft.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Bei diesem Thema wird davon ausgegangen, dass Sie die grundlegenden Szenarien zum Implementieren einer Abhängigkeitseigenschaft verstehen, und Metadaten für eine benutzerdefinierte Abhängigkeitseigenschaft anwenden. Mehr dazu finden Sie unter [benutzerdefinierten Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
<a name="existing"></a>   
## <a name="existing-read-only-dependency-properties"></a>Bestehende schreibgeschützte Abhängigkeitseigenschaften  
 Einige der Abhängigkeitseigenschaften, die im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Framework festgelegt sind, sind schreibgeschützt. Der Hauptgrund zum Festlegen einer schreibgeschützten Abhängigkeitseigenschaft ist, dass dies Eigenschaften sind, die zur Statusbestimmung verwendet werden sollen, allerdings wird dieser Status durch eine Vielzahl von Faktoren beeinflusst, wobei das einfache Festlegen der Eigenschaft in diesem Status aus der Perspektive des Benutzeroberflächendesigns nicht in Frage kommt. Beispielsweise ist die- <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft tatsächlich einfach nur mit dem Status "verfügbar", wie von der Mauseingabe bestimmt. dann wäre jeder Versuch, diesen Wert programmgesteuert - durch die Umgehung der echten Mauseingabe - festzulegen, unvorhersehbar und würde zu einer Inkonsistenz führen.  
  
 Schreibgeschützte Abhängigkeitseigenschaften sind nicht für zahlreiche Szenarien geeignet, für die Abhängigkeitseigenschaften normalerweise eine Lösung bieten, da sie nicht eingestellt werden können (genauer gesagt: Datenbindung, direkt auf einen Wert formatierbar, Überprüfung, Animation, Vererbung). Obwohl Sie nicht eingestellt werden können, verfügen schreibgeschützte Abhängigkeitseigenschaft immer noch über einige weitere Funktionen, die von Abhängigkeitseigenschaften im Eigenschaftssystem unterstützt werden. Die wichtigste verbleibende Funktion ist, dass die schreibgeschützte Abhängigkeitseigenschaft weiterhin als Eigenschaftstrigger in einem Stil verwendet werden kann. Trigger können nicht mit einer normalen common Language Runtime (CLR)-Eigenschaft aktiviert werden. Dabei muss es sich um eine Abhängigkeits Eigenschaft handeln. Die oben <xref:System.Windows.UIElement.IsMouseOver%2A> genannte Eigenschaft ist ein perfektes Beispiel für ein Szenario, in dem es sehr nützlich sein kann, einen Stil für ein Steuerelement zu definieren, bei dem eine sichtbare Eigenschaft, z. b. eine Hintergrund-, Vordergrund-oder ähnliche Eigenschaften von zusammengesetzten Elementen innerhalb des das Steuerelement ändert sich, wenn der Benutzer mit der Maus über einen definierten Bereich Ihres Steuer Elements bewegt wird. Änderungen in einer schreibgeschützten Abhängigkeitseigenschaft können auch ermittelt und durch den inhärenten Ungültigkeitsprozess des Eigenschaftssystems gemeldet werden, und dies unterstützt in der Tat intern die Eigenschaftsauslöserfunktionalität.  
  
<a name="new"></a>   
## <a name="creating-custom-read-only-dependency-properties"></a>Erstellen benutzerdefinierter, schreibgeschützter Abhängigkeitseigenschaften  
 Lesen Sie auf jeden Fall den Abschnitt oben zum Thema: Warum schreibgeschützte Abhängigkeitseigenschaften für viele normale Abhängigkeitseigenschaftsszenarien nicht funktioniert. Wenn Sie ein entsprechendes Szenario haben, können Sie jedoch eine eigene schreibgeschützte Abhängigkeitseigenschaft erstellen.  
  
 Einiges des Prozesses zum Erstellen einer schreibgeschützten Abhängigkeitseigenschaft entspricht weitgehend den in [benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Implementieren einer Abhängigkeitseigenschaft](how-to-implement-a-dependency-property.md) beschriebenen Themen. Es gibt drei wichtige Unterschiede:  
  
- Wenn Sie die-Eigenschaft registrieren, <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> müssen Sie die-Methode <xref:System.Windows.DependencyProperty.Register%2A> anstelle der normalen-Methode für die Eigenschaften Registrierung aufzurufen.  
  
- Wenn Sie die CLR-Wrapper Eigenschaft implementieren, stellen Sie sicher, dass der Wrapper auch nicht über eine Set-Implementierung verfügt, sodass keine Inkonsistenzen im schreibgeschützten Zustand für den von Ihnen verfügbar gemachten öffentlichen Wrapper vorhanden sind.  
  
- Das von der schreibgeschützten Registrierung zurückgegebene Objekt ist <xref:System.Windows.DependencyPropertyKey> <xref:System.Windows.DependencyProperty>nicht. Speichern Sie dieses Feld weiterhin als Member, aber normalerweise sollten Sie es nicht zu einem öffentlichen Member des Typs machen.  
  
 Alle privaten Felder oder Werte, die Ihre schreibgeschützte Abhängigkeitseigenschaft unterstützen, können natürlich vollständig von Ihrer gewünschten Logik beschreibbar sein. Die einfachste Möglichkeit, die-Eigenschaft entweder anfänglich oder als Teil der Lauf Zeit Logik festzulegen, ist jedoch die Verwendung der APIs des Eigenschaften Systems, anstatt das Eigenschaften System zu umgehen und das private Unterstützungs Feld direkt festzulegen. Insbesondere gibt es eine Signatur von <xref:System.Windows.DependencyObject.SetValue%2A> , die einen Parameter vom Typ <xref:System.Windows.DependencyPropertyKey>akzeptiert. Wie und wo Sie diesen Wert Programm gesteuert innerhalb ihrer Anwendungslogik festlegen, wirkt sich darauf aus, wie Sie den Zugriff auf <xref:System.Windows.DependencyPropertyKey> den erstellen können, wenn Sie die Abhängigkeits Eigenschaft zum ersten Mal registriert haben. Wenn Sie diese Logik innerhalb der Klasse bearbeiten, können Sie diese als privat einstellen, oder wenn Sie möchten, dass diese von anderen Teilen des Assembly festgelegt wird, müssen Sie dies intern festlegen. Ein Ansatz besteht darin, <xref:System.Windows.DependencyObject.SetValue%2A> innerhalb eines Klassen Ereignis Handlers eines relevanten Ereignisses aufzurufen, das einer Klasseninstanz mitteilt, dass der gespeicherte Eigenschafts Wert geändert werden muss. Ein anderer Ansatz besteht darin, Abhängigkeits Eigenschaften zusammenzufassen <xref:System.Windows.PropertyChangedCallback> , <xref:System.Windows.CoerceValueCallback> indem Sie bei der Registrierung als Teil der Metadaten der Eigenschaften als Teil der Metadaten der Eigenschaft gekoppelt werden.  
  
 Da die <xref:System.Windows.DependencyPropertyKey> privat ist und nicht vom-Eigenschaften System außerhalb des Codes weitergegeben wird, verfügt eine schreibgeschützte Abhängigkeits Eigenschaft über eine bessere Einstellungs Sicherheit als eine Abhängigkeits Eigenschaft mit Lese-/Schreibzugriff. Für eine Abhängigkeitseigenschaft, die gelesen und bearbeitet werden kann, ist das identifizierende Feld explizit oder implizit öffentlich und daher kann die Eigenschaft umfassend festgelegt werden. Ausführlichere Informationen dazu finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
