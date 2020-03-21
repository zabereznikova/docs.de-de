---
title: Schreibgeschützte Abhängigkeitseigenschaften
ms.date: 03/30/2017
helpviewer_keywords:
- dependency properties [WPF], read-only
- read-only dependency properties [WPF]
ms.assetid: f23d6ec9-3780-4c09-a2ff-b2f0a2deddf1
ms.openlocfilehash: 8adc90182f0f42f52e6ace4e13c68acb3539516b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187179"
---
# <a name="read-only-dependency-properties"></a>Schreibgeschützte Abhängigkeitseigenschaften
Dieses Thema beschreibt die schreibgeschützten Abhängigkeitseigenschaften, einschließlich vorhandener schreibgeschützter Abhängigkeitseigenschaften und die Szenarien und Verfahren zum Erstellen einer benutzerdefinierten, schreibgeschützten Abhängigkeitseigenschaft.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Bei diesem Thema wird davon ausgegangen, dass Sie die grundlegenden Szenarien zum Implementieren einer Abhängigkeitseigenschaft verstehen, und Metadaten für eine benutzerdefinierte Abhängigkeitseigenschaft anwenden. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
<a name="existing"></a>
## <a name="existing-read-only-dependency-properties"></a>Bestehende schreibgeschützte Abhängigkeitseigenschaften  
 Einige der Abhängigkeitseigenschaften, die im [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Framework festgelegt sind, sind schreibgeschützt. Der Hauptgrund zum Festlegen einer schreibgeschützten Abhängigkeitseigenschaft ist, dass dies Eigenschaften sind, die zur Statusbestimmung verwendet werden sollen, allerdings wird dieser Status durch eine Vielzahl von Faktoren beeinflusst, wobei das einfache Festlegen der Eigenschaft in diesem Status aus der Perspektive des Benutzeroberflächendesigns nicht in Frage kommt. Beispielsweise ist die <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft wirklich nur Oberflächenzustand, wie von der Mauseingabe bestimmt. dann wäre jeder Versuch, diesen Wert programmgesteuert - durch die Umgehung der echten Mauseingabe - festzulegen, unvorhersehbar und würde zu einer Inkonsistenz führen.  
  
 Schreibgeschützte Abhängigkeitseigenschaften sind nicht für zahlreiche Szenarien geeignet, für die Abhängigkeitseigenschaften normalerweise eine Lösung bieten, da sie nicht eingestellt werden können (genauer gesagt: Datenbindung, direkt auf einen Wert formatierbar, Überprüfung, Animation, Vererbung). Obwohl Sie nicht eingestellt werden können, verfügen schreibgeschützte Abhängigkeitseigenschaft immer noch über einige weitere Funktionen, die von Abhängigkeitseigenschaften im Eigenschaftssystem unterstützt werden. Die wichtigste verbleibende Funktion ist, dass die schreibgeschützte Abhängigkeitseigenschaft weiterhin als Eigenschaftstrigger in einem Stil verwendet werden kann. Sie können Trigger nicht mit einer normalen CLR-Eigenschaft (Common Language Runtime) aktivieren. Es muss eine Abhängigkeitseigenschaft sein. Die <xref:System.Windows.UIElement.IsMouseOver%2A> oben genannte Eigenschaft ist ein perfektes Beispiel für ein Szenario, in dem es sehr nützlich sein könnte, einen Stil für ein Steuerelement zu definieren, in dem einige sichtbare Eigenschaften wie Hintergrund, Vordergrund oder ähnliche Eigenschaften zusammengesetzter Elemente innerhalb des Steuerelements sich ändern, wenn der Benutzer eine Maus über einen definierten Bereich des Steuerelements platziert. Änderungen in einer schreibgeschützten Abhängigkeitseigenschaft können auch ermittelt und durch den inhärenten Ungültigkeitsprozess des Eigenschaftssystems gemeldet werden, und dies unterstützt in der Tat intern die Eigenschaftsauslöserfunktionalität.  
  
<a name="new"></a>
## <a name="creating-custom-read-only-dependency-properties"></a>Erstellen benutzerdefinierter, schreibgeschützter Abhängigkeitseigenschaften  
 Lesen Sie auf jeden Fall den Abschnitt oben zum Thema: Warum schreibgeschützte Abhängigkeitseigenschaften für viele normale Abhängigkeitseigenschaftsszenarien nicht funktioniert. Wenn Sie ein entsprechendes Szenario haben, können Sie jedoch eine eigene schreibgeschützte Abhängigkeitseigenschaft erstellen.  
  
 Einiges des Prozesses zum Erstellen einer schreibgeschützten Abhängigkeitseigenschaft entspricht weitgehend den in [benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Implementieren einer Abhängigkeitseigenschaft](how-to-implement-a-dependency-property.md) beschriebenen Themen. Es gibt drei wichtige Unterschiede:  
  
- Rufen Sie beim Registrieren <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A> Ihrer Eigenschaft die <xref:System.Windows.DependencyProperty.Register%2A> Methode anstelle der normalen Methode für die Eigenschaftsregistrierung auf.  
  
- Stellen Sie beim Implementieren der CLR-Eigenschaft "wrapper" sicher, dass auch der Wrapper keine festgelegte Implementierung hat, damit für den öffentlichen Wrapper, den Sie verfügbar machen, keine Inkonsistenz im schreibgeschützten Zustand vorhanden ist.  
  
- Das Objekt, das von der <xref:System.Windows.DependencyPropertyKey> schreibgeschützten Registrierung zurückgegeben wird, ist nicht <xref:System.Windows.DependencyProperty>. Speichern Sie dieses Feld weiterhin als Member, aber normalerweise sollten Sie es nicht zu einem öffentlichen Member des Typs machen.  
  
 Alle privaten Felder oder Werte, die Ihre schreibgeschützte Abhängigkeitseigenschaft unterstützen, können natürlich vollständig von Ihrer gewünschten Logik beschreibbar sein. Die einfachste Möglichkeit, die Eigenschaft entweder entweder anfänglich oder als Teil der Laufzeitlogik festzulegen, besteht jedoch darin, die APIs des Eigenschaftensystems zu verwenden, anstatt das Eigenschaftensystem zu umgehen und das Feld für die private Sicherung direkt festzulegen. Insbesondere gibt es eine <xref:System.Windows.DependencyObject.SetValue%2A> Signatur, die einen <xref:System.Windows.DependencyPropertyKey>Parameter vom Typ akzeptiert. Wie und wo Sie diesen Wert programmgesteuert in ihrer Anwendungslogik festlegen, <xref:System.Windows.DependencyPropertyKey> wirkt sich darauf aus, wie Sie den Zugriff auf die erstellte Einstellung festlegen möchten, als Sie die Abhängigkeitseigenschaft zum ersten Mal registriert haben. Wenn Sie diese Logik innerhalb der Klasse bearbeiten, können Sie diese als privat einstellen, oder wenn Sie möchten, dass diese von anderen Teilen des Assembly festgelegt wird, müssen Sie dies intern festlegen. Ein Ansatz besteht <xref:System.Windows.DependencyObject.SetValue%2A> darin, innerhalb eines Klassenereignishandlers eines relevanten Ereignisses aufzurufen, das eine Klasseninstanz darüber informiert, dass der gespeicherte Eigenschaftswert geändert werden muss. Ein weiterer Ansatz besteht darin, <xref:System.Windows.PropertyChangedCallback> Abhängigkeitseigenschaften mithilfe von gekoppelten und <xref:System.Windows.CoerceValueCallback> Rückrufen als Teil der Metadaten dieser Eigenschaften während der Registrierung zu verbinden.  
  
 Da <xref:System.Windows.DependencyPropertyKey> der privat ist und nicht vom Eigenschaftensystem außerhalb des Codes weitergegeben wird, verfügt eine schreibgeschützte Abhängigkeitseigenschaft über eine bessere Einstellungssicherheit als eine Lese-/Schreibabhängigkeitseigenschaft. Für eine Abhängigkeitseigenschaft, die gelesen und bearbeitet werden kann, ist das identifizierende Feld explizit oder implizit öffentlich und daher kann die Eigenschaft umfassend festgelegt werden. Ausführlichere Informationen dazu finden Sie unter [Sicherheit von Abhängigkeitseigenschaften](dependency-property-security.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
