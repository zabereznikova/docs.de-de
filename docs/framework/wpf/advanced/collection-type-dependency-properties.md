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
ms.openlocfilehash: 9ce0b70bfdd70b47857167ff14e62ed2bbda569d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010695"
---
# <a name="collection-type-dependency-properties"></a>Abhängigkeitseigenschaften vom Auflistungstyp
Dieses Thema enthält einen Leitfaden und empfohlene Muster zur Implementierung einer Abhängigkeitseigenschaft für Eigenschaften vom Auflistungstyp.  

<a name="implementing"></a>   
## <a name="implementing-a-collection-type-dependency-property"></a>Implementieren einer Abhängigkeitseigenschaft vom Auflistungstyp  
 Für eine Abhängigkeitseigenschaft im Allgemeinen Implementierung, die Sie ausführen, wird Sie definieren eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Eigenschaftenwrapper, in dem diese Eigenschaft basiert auf einer <xref:System.Windows.DependencyProperty> -Bezeichner statt ein Feld oder anderes Konstrukt. Folgen Sie diesem Muster auch bei der Implementierung einer Eigenschaft vom Auflistungstyp. Eine Eigenschaft vom Auflistungstyp führt jedoch komplexer, das Muster, wenn der Typ, der in der Auflistung enthalten ist, die selbst ist ein <xref:System.Windows.DependencyObject> oder <xref:System.Windows.Freezable> abgeleitete Klasse.  
  
<a name="initializing"></a>   
## <a name="initializing-the-collection-beyond-the-default-value"></a>Initialisieren der Auflistung für einen anderen Wert als den Standardwert  
 Beim Erstellen einer Abhängigkeitseigenschaft geben Sie nicht den Standardwert der Eigenschaft als Anfangsfeldwert an. Geben Sie den Standardwert stattdessen über die Metadaten für Abhängigkeitseigenschaften an. Handelt es sich bei der Eigenschaft um einen Verweistyp, ist der in den Metadaten für Abhängigkeitseigenschaften angegebene Standardwert kein Standardwert pro Instanz. Er stellt vielmehr einen Standardwert dar, der für alle Instanzen des Typs gilt. Achten Sie also darauf, dass Sie nicht die durch die Metadaten für Auflistungseigenschaften definierte, einzelne statische Auflistung als funktionierenden Standardwert für neu erstellte Instanzen des Typs verwenden. Vergewissern Sie sich stattdessen, dass Sie den Auflistungswert bewusst als eine eindeutige (Instanz-)Auflistung als Teil Ihrer Klassenkonstruktorlogik festlegen. Andernfalls erstellen Sie unbeabsichtigterweise eine Singleton-Klasse.  
  
 Betrachten Sie das folgende Beispiel. Der nachfolgende Abschnitt des Beispiels veranschaulicht die Definition einer `Aquarium`-Klasse. Die Klasse definiert die Auflistung Typ Abhängigkeitseigenschaft `AquariumObjects`, verwendet die generische <xref:System.Collections.Generic.List%601> Typ mit einem <xref:System.Windows.FrameworkElement> typeinschränkung. In der <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29> -Aufruf für die Abhängigkeitseigenschaft, die Metadaten legt den Standardwert als neue generische <xref:System.Collections.Generic.List%601>.  
  
 [!code-csharp[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport2/CSharp/page.xaml.cs#collectionproblemdefinition)]
 [!code-vb[PropertiesOvwSupport2#CollectionProblemDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport2/visualbasic/page.xaml.vb#collectionproblemdefinition)]  
  
 Wenn Sie den Code unverändert lassen, wird dieser einzelne Listenstandardwert für alle Instanzen von `Aquarium` freigegeben. Beim Ausführen des folgenden Testcodes, der zeigen soll, wie zwei getrennte `Aquarium`-Instanzen instanziiert und jeder ein einzelner unterschiedlicher `Fish` hinzugefügt würde, käme es zu einem überraschenden Ergebnis:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 Anstatt eines Eintrags besitzt jede Auflistung nun zwei! Das liegt daran, dass jedes `Aquarium` seinen `Fish` der Standardwertauflistung hinzugefügt hat, die das Ergebnis eines einzelnen Konstruktoraufrufs in den Metadaten ist und daher für alle Instanzen freigegeben ist. Diese Situation ist so gut wie nie erwünscht.  
  
 Zur Behebung des Problems müssen Sie den Abhängigkeitseigenschaftswert der Auflistung auf eine eindeutige Instanz als Teil des Klassenkonstruktoraufrufs zurücksetzen. Da die Eigenschaft eine schreibgeschützte Abhängigkeitseigenschaft ist, verwenden Sie die <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29> Methode, mit der <xref:System.Windows.DependencyPropertyKey> , die nur innerhalb der Klasse zugänglich ist.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 Bei einer erneuten Ausführung des Testcodes wären die Ergebnisse nun eher wie erwartet, da jedes `Aquarium` seine eigene eindeutige Auflistung unterstützen würde.  
  
 Dieses Muster wäre geringfügig abgewandelt, wenn Sie die Auflistungseigenschaft mit Lese-/Schreibzugriff wählen würden. In diesem Fall könnten Sie den öffentlichen Set-Accessor aufrufen, aus dem Konstruktor, um die Initialisierung auszuführen, die weiterhin die nichtschlüsselsignatur von Aufrufen <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> innerhalb Ihres Set-Wrappers mithilfe einer öffentlichen <xref:System.Windows.DependencyProperty> Bezeichner.  
  
## <a name="reporting-binding-value-changes-from-collection-properties"></a>Melden von Bindungswertänderungen durch Auflistungseigenschaften  
 Eine Auflistungseigenschaft, die selbst eine Abhängigkeitseigenschaft ist, meldet nicht automatisch Änderungen an die ihr untergeordneten Eigenschaften. Wenn Sie in einer Auflistung Bindungen erstellen, kann möglicherweise das Melden von Änderungen durch die Bindung verhindert werden, wodurch einige Datenbindungsszenarios ungültig gemacht werden können. Allerdings bei der Verwendung des Auflistungstyps <xref:System.Windows.FreezableCollection%601> als Ihren Auflistungstyp dann Untereigenschaften-Änderungen an den darin enthaltenen Elemente in der Auflistung ordnungsgemäß gemeldet, und Bindung funktioniert wie erwartet.  
  
 Um die Bindung von untergeordneten Eigenschaften in einer Auflistung zu ermöglichen, erstellen Sie die Auflistungseigenschaft als Typ <xref:System.Windows.FreezableCollection%601>, mit einer typeinschränkung für diese Sammlung in einen <xref:System.Windows.DependencyObject> abgeleitete Klasse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FreezableCollection%601>
- [XAML- und benutzerdefinierte Klassen für WPF](xaml-and-custom-classes-for-wpf.md)
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
