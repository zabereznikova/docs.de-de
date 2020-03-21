---
title: Abhängigkeitseigenschaften vom Auflistungstyp
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], dependency
- properties [WPF], collection-type
- dependency properties [WPF]
- collection-type properties [WPF]
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
ms.openlocfilehash: e783ce4b95b52b86671181dfe4b316d4b91d8fc6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141536"
---
# <a name="collection-type-dependency-properties"></a>Abhängigkeitseigenschaften vom Auflistungstyp
Dieses Thema enthält einen Leitfaden und empfohlene Muster zur Implementierung einer Abhängigkeitseigenschaft für Eigenschaften vom Auflistungstyp.  

<a name="implementing"></a>
## <a name="implementing-a-collection-type-dependency-property"></a>Implementieren einer Abhängigkeitseigenschaft vom Auflistungstyp  
 Bei einer Abhängigkeitseigenschaft im Allgemeinen folgen Sie dem Implementierungsmuster, dem Sie folgen, dass <xref:System.Windows.DependencyProperty> Sie einen CLR-Eigenschaftswrapper definieren, wobei diese Eigenschaft durch einen Bezeichner und nicht durch ein Feld oder ein anderes Konstrukt unterstützt wird. Folgen Sie diesem Muster auch bei der Implementierung einer Eigenschaft vom Auflistungstyp. Eine Auflistungseigenschaft führt jedoch zu einer gewissen Komplexität des Musters, wenn <xref:System.Windows.DependencyObject> <xref:System.Windows.Freezable> der in der Auflistung enthaltene Typ selbst eine oder abgeleitete Klasse ist.  
  
<a name="initializing"></a>
## <a name="initializing-the-collection-beyond-the-default-value"></a>Initialisieren der Auflistung für einen anderen Wert als den Standardwert  
 Beim Erstellen einer Abhängigkeitseigenschaft geben Sie nicht den Standardwert der Eigenschaft als Anfangsfeldwert an. Geben Sie den Standardwert stattdessen über die Metadaten für Abhängigkeitseigenschaften an. Handelt es sich bei der Eigenschaft um einen Verweistyp, ist der in den Metadaten für Abhängigkeitseigenschaften angegebene Standardwert kein Standardwert pro Instanz. Er stellt vielmehr einen Standardwert dar, der für alle Instanzen des Typs gilt. Achten Sie also darauf, dass Sie nicht die durch die Metadaten für Auflistungseigenschaften definierte, einzelne statische Auflistung als funktionierenden Standardwert für neu erstellte Instanzen des Typs verwenden. Vergewissern Sie sich stattdessen, dass Sie den Auflistungswert bewusst als eine eindeutige (Instanz-)Auflistung als Teil Ihrer Klassenkonstruktorlogik festlegen. Andernfalls erstellen Sie unbeabsichtigterweise eine Singleton-Klasse.  
  
 Betrachten Sie das folgende Beispiel. Der folgende Abschnitt des Beispiels zeigt `Aquarium`die Definition für eine Klasse , die einen Fehler mit dem Standardwert enthält. Die Klasse definiert die `AquariumObjects`Auflistungstypabhängigkeitseigenschaft <xref:System.Collections.Generic.List%601> , <xref:System.Windows.FrameworkElement> die den generischen Typ mit einer Typeinschränkung verwendet. In <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> der Aufrufen für die Abhängigkeitseigenschaft legen die Metadaten <xref:System.Collections.Generic.List%601>den Standardwert als neues generisches fest.

> [!WARNING]
> Der folgende Code verhält sich nicht korrekt.

 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 Wenn Sie den Code unverändert lassen, wird dieser einzelne Listenstandardwert für alle Instanzen von `Aquarium` freigegeben. Beim Ausführen des folgenden Testcodes, der zeigen soll, wie zwei getrennte `Aquarium`-Instanzen instanziiert und jeder ein einzelner unterschiedlicher `Fish` hinzugefügt würde, käme es zu einem überraschenden Ergebnis:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 Anstatt eines Eintrags besitzt jede Auflistung nun zwei! Das liegt daran, dass jedes `Aquarium` seinen `Fish` der Standardwertauflistung hinzugefügt hat, die das Ergebnis eines einzelnen Konstruktoraufrufs in den Metadaten ist und daher für alle Instanzen freigegeben ist. Diese Situation ist so gut wie nie erwünscht.  
  
 Zur Behebung des Problems müssen Sie den Abhängigkeitseigenschaftswert der Auflistung auf eine eindeutige Instanz als Teil des Klassenkonstruktoraufrufs zurücksetzen. Da es sich bei der Eigenschaft um <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> eine schreibgeschützte Abhängigkeitseigenschaft handelt, verwenden Sie die Methode zum Festlegen der Eigenschaft, auf die <xref:System.Windows.DependencyPropertyKey> nur innerhalb der Klasse zugegriffen werden kann.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 Bei einer erneuten Ausführung des Testcodes wären die Ergebnisse nun eher wie erwartet, da jedes `Aquarium` seine eigene eindeutige Auflistung unterstützen würde.  
  
 Dieses Muster wäre geringfügig abgewandelt, wenn Sie die Auflistungseigenschaft mit Lese-/Schreibzugriff wählen würden. In diesem Fall können Sie den öffentlichen Set-Accessor vom Konstruktor aufrufen, um die Initialisierung zu tun, die immer noch die Nicht-Schlüsselsignatur von <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> in Ihrem festgelegten Wrapper unter Verwendung eines öffentlichen <xref:System.Windows.DependencyProperty> Bezeichners aufruft.  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a>Melden von Bindungswertänderungen durch Auflistungseigenschaften  
 Eine Auflistungseigenschaft, die selbst eine Abhängigkeitseigenschaft ist, meldet nicht automatisch Änderungen an die ihr untergeordneten Eigenschaften. Wenn Sie in einer Auflistung Bindungen erstellen, kann möglicherweise das Melden von Änderungen durch die Bindung verhindert werden, wodurch einige Datenbindungsszenarios ungültig gemacht werden können. Wenn Sie jedoch den <xref:System.Windows.FreezableCollection%601> Auflistungstyp als Auflistungstyp verwenden, werden Untereigenschaftenänderungen an enthaltenen Elementen in der Auflistung ordnungsgemäß gemeldet, und die Bindung funktioniert wie erwartet.  
  
 Um die Subpropertybindung in einer Abhängigkeitsobjektauflistung <xref:System.Windows.FreezableCollection%601>zu aktivieren, erstellen Sie die <xref:System.Windows.DependencyObject> Auflistungseigenschaft als Typ mit einer Typeinschränkung für diese Auflistung für jede abgeleitete Klasse.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.FreezableCollection%601>
- [XAML- und benutzerdefinierte Klassen für WPF](xaml-and-custom-classes-for-wpf.md)
- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
