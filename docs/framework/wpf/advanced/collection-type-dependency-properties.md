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
ms.openlocfilehash: dd268c0c132f4ecefe7b2336432442d9569ca38f
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401556"
---
# <a name="collection-type-dependency-properties"></a>Abhängigkeitseigenschaften vom Auflistungstyp
Dieses Thema enthält einen Leitfaden und empfohlene Muster zur Implementierung einer Abhängigkeitseigenschaft für Eigenschaften vom Auflistungstyp.  

<a name="implementing"></a>   
## <a name="implementing-a-collection-type-dependency-property"></a>Implementieren einer Abhängigkeitseigenschaft vom Auflistungstyp  
 Für eine Abhängigkeits Eigenschaft im Allgemeinen ist das folgende Implementierungs Muster, dass Sie einen CLR-Eigenschafts Wrapper definieren, bei dem diese Eigenschaft durch einen <xref:System.Windows.DependencyProperty> Bezeichner und nicht durch ein Feld oder ein anderes Konstrukt gestützt wird. Folgen Sie diesem Muster auch bei der Implementierung einer Eigenschaft vom Auflistungstyp. Eine Auflistungstyp Eigenschaft führt jedoch zu einer gewissen Komplexität des Musters, wenn der in der Auflistung enthaltene Typ selbst eine oder <xref:System.Windows.DependencyObject> <xref:System.Windows.Freezable> eine abgeleitete Klasse ist.  
  
<a name="initializing"></a>   
## <a name="initializing-the-collection-beyond-the-default-value"></a>Initialisieren der Auflistung für einen anderen Wert als den Standardwert  
 Beim Erstellen einer Abhängigkeitseigenschaft geben Sie nicht den Standardwert der Eigenschaft als Anfangsfeldwert an. Geben Sie den Standardwert stattdessen über die Metadaten für Abhängigkeitseigenschaften an. Handelt es sich bei der Eigenschaft um einen Verweistyp, ist der in den Metadaten für Abhängigkeitseigenschaften angegebene Standardwert kein Standardwert pro Instanz. Er stellt vielmehr einen Standardwert dar, der für alle Instanzen des Typs gilt. Achten Sie also darauf, dass Sie nicht die durch die Metadaten für Auflistungseigenschaften definierte, einzelne statische Auflistung als funktionierenden Standardwert für neu erstellte Instanzen des Typs verwenden. Vergewissern Sie sich stattdessen, dass Sie den Auflistungswert bewusst als eine eindeutige (Instanz-)Auflistung als Teil Ihrer Klassenkonstruktorlogik festlegen. Andernfalls erstellen Sie unbeabsichtigterweise eine Singleton-Klasse.  
  
 Betrachten Sie das folgende Beispiel. Der nachfolgende Abschnitt des Beispiels veranschaulicht die Definition einer `Aquarium`-Klasse. Die-Klasse definiert die Auflistungstyp-Abhängigkeits Eigenschaft `AquariumObjects`, die den <xref:System.Windows.FrameworkElement> generischen <xref:System.Collections.Generic.List%601> Typ mit einer Typeinschränkung verwendet. Im-Befehl für die-Abhängigkeits Eigenschaft wird der Standardwert von den Metadaten als neuer generischer <xref:System.Collections.Generic.List%601>Wert festgelegt. <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29>  
  
 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 Wenn Sie den Code unverändert lassen, wird dieser einzelne Listenstandardwert für alle Instanzen von `Aquarium` freigegeben. Beim Ausführen des folgenden Testcodes, der zeigen soll, wie zwei getrennte `Aquarium`-Instanzen instanziiert und jeder ein einzelner unterschiedlicher `Fish` hinzugefügt würde, käme es zu einem überraschenden Ergebnis:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 Anstatt eines Eintrags besitzt jede Auflistung nun zwei! Das liegt daran, dass jedes `Aquarium` seinen `Fish` der Standardwertauflistung hinzugefügt hat, die das Ergebnis eines einzelnen Konstruktoraufrufs in den Metadaten ist und daher für alle Instanzen freigegeben ist. Diese Situation ist so gut wie nie erwünscht.  
  
 Zur Behebung des Problems müssen Sie den Abhängigkeitseigenschaftswert der Auflistung auf eine eindeutige Instanz als Teil des Klassenkonstruktoraufrufs zurücksetzen. Da die-Eigenschaft eine schreibgeschützte Abhängigkeits Eigenschaft ist, verwenden <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> Sie die-Methode, um Sie <xref:System.Windows.DependencyPropertyKey> mithilfe von festzulegen, auf die nur innerhalb der-Klasse zugegriffen werden kann.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 Bei einer erneuten Ausführung des Testcodes wären die Ergebnisse nun eher wie erwartet, da jedes `Aquarium` seine eigene eindeutige Auflistung unterstützen würde.  
  
 Dieses Muster wäre geringfügig abgewandelt, wenn Sie die Auflistungseigenschaft mit Lese-/Schreibzugriff wählen würden. In diesem Fall könnten Sie den Public-Set-Accessor vom Konstruktor aufrufen, um die Initialisierung durchzuführen, die nach wie vor die nicht Schlüssel Signatur <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> von innerhalb des Set-Wrappers mit <xref:System.Windows.DependencyProperty> einem öffentlichen Bezeichner aufruft.  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a>Melden von Bindungswertänderungen durch Auflistungseigenschaften  
 Eine Auflistungseigenschaft, die selbst eine Abhängigkeitseigenschaft ist, meldet nicht automatisch Änderungen an die ihr untergeordneten Eigenschaften. Wenn Sie in einer Auflistung Bindungen erstellen, kann möglicherweise das Melden von Änderungen durch die Bindung verhindert werden, wodurch einige Datenbindungsszenarios ungültig gemacht werden können. Wenn Sie jedoch den Sammlungstyp <xref:System.Windows.FreezableCollection%601> als Auflistungstyp verwenden, werden Änderungen der untergeordneten Eigenschaft an enthaltene Elemente in der Auflistung ordnungsgemäß gemeldet, und die Bindung funktioniert wie erwartet.  
  
 Um die Bindung von untergeordneten Eigenschaften in einer Auflistung von Abhängigkeits Objekten zu aktivieren, <xref:System.Windows.FreezableCollection%601>erstellen Sie die Auflistungs Eigenschaft als Typ mit <xref:System.Windows.DependencyObject> einer Typeinschränkung für diese Auflistung in eine beliebige abgeleitete Klasse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FreezableCollection%601>
- [XAML- und benutzerdefinierte Klassen für WPF](xaml-and-custom-classes-for-wpf.md)
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
