---
title: Rückrufe und Validierung von Abhängigkeitseigenschaften
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], validation
- coerce value callbacks [WPF]
- callbacks [WPF], validation
- dependency properties [WPF], callbacks
- validation of dependency properties [WPF]
ms.assetid: 48db5fb2-da7f-49a6-8e81-3540e7b25825
ms.openlocfilehash: c5f7439753037aeb5c2ff558da63e063ad65a5e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186435"
---
# <a name="dependency-property-callbacks-and-validation"></a>Rückrufe und Validierung von Abhängigkeitseigenschaften
Dieses Thema beschreibt die Erstellung von Abhängigkeitseigenschaften mithilfe alternativer benutzerdefinierter Implementierungen für eigenschaftenbezogene Funktionen wie die Überprüfungsbestimmung, Rückrufe, die immer dann aufgerufen werden, wenn der effektive Wert der Eigenschaft geändert wird, und das Überschreiben möglicher externer Einflüsse auf die Wertbestimmung. Dieses Thema enthält auch Szenarios, in denen das Erweitern des Standardverhaltens des Eigenschaftensystems mithilfe dieser Techniken geeignet ist.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Voraussetzungen  
 Bei diesem Thema wird davon ausgegangen, dass Sie die grundlegenden Szenarien zum Implementieren einer Abhängigkeitseigenschaft verstehen, und Metadaten für eine benutzerdefinierte Abhängigkeitseigenschaft anwenden. Weitere Informationen finden Sie unter [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md) und [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md).  
  
<a name="Validation_Callbacks"></a>
## <a name="validation-callbacks"></a>Überprüfungsrückrufe  
 Überprüfungsrückrufe können beim ersten Registrieren einer Abhängigkeitseigenschaft zugewiesen werden. Der Validierungsrückruf ist nicht Teil von Eigenschaftenmetadaten. es ist eine direkte <xref:System.Windows.DependencyProperty.Register%2A> Eingabe der Methode. Sobald ein Validierungsrückruf für eine Abhängigkeitseigenschaft erstellt wurde, kann er daher nicht durch eine neue Implementierung überschrieben werden.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 Die Rückrufe werden so implementiert, dass ihnen ein Objektwert bereitgestellt wird. Sie geben `true` zurück, wenn der bereitgestellte Wert für die Eigenschaft gültig ist. Andernfalls geben sie `false` zurück. Es wird davon ausgegangen, dass die Eigenschaft entsprechend dem im Eigenschaftensystem registrierten Typ zum richtigen Typ gehört. Typüberprüfungen werden daher innerhalb von Rückrufen in der Regel nicht ausgeführt. Die Rückrufe werden vom Eigenschaftensystem bei einer Vielzahl verschiedener Vorgänge verwendet. Dazu gehören die anfängliche Typinitialisierung nach Standardwert, <xref:System.Windows.DependencyObject.SetValue%2A>programmgesteuerte Änderungen durch Aufrufen oder Versuche, Metadaten mit einem neuen Standardwert zu überschreiben. Wenn der Validierungsrückruf von einem dieser Vorgänge aufgerufen wird und `false` zurückgibt, wird eine Ausnahme ausgelöst. Anwendungsentwickler müssen diese Ausnahmen behandeln können. Rückrufen werden üblicherweise zur Validierung von Enumerationswerten oder der Einschränkung von Werten aus ganzen Zahlen oder Double-Datentypen verwendet, wenn die Eigenschaft Messungen festlegt, die 0 (null) oder höher entsprechen müssen.  
  
 Überprüfungsrückrufe sollen Klassen-Validierungssteuerelemente, keine Instanz-Validierungssteuerelemente sein. Die Parameter des Rückrufs kommunizieren <xref:System.Windows.DependencyObject> keine bestimmte, für die die zu überprüfenden Eigenschaften festgelegt sind. Daher sind die Validierungsrückrufe nicht nützlich für das Erzwingen der möglichen „Abhängigkeiten“, die einen Eigenschaftswert beeinflussen können, bei dem der instanzspezifische Wert einer Eigenschaft von Faktoren wie instanzspezifischen Werten anderer Eigenschaften oder dem Laufzeitzustand anhängen.  
  
 Im Folgenden finden Sie Beispielcode für ein sehr einfaches Validierungsrückrufszenario: Überprüfen, ob eine Eigenschaft, die <xref:System.Double> als Primitiv eingegeben wird, nicht <xref:System.Double.PositiveInfinity> oder <xref:System.Double.NegativeInfinity>ist.  
  
 [!code-csharp[DPCallbackOverride#ValidateValueCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#validatevaluecallback)]
 [!code-vb[DPCallbackOverride#ValidateValueCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#validatevaluecallback)]  
  
<a name="Coerce_Value_Callbacks_and_Property_Changed_Events"></a>
## <a name="coerce-value-callbacks-and-property-changed-events"></a>Coerce-Wert-Rückrufe und Eigenschaftenänderungsereignisse  
 Coerce-Wertrückrufe übergeben die <xref:System.Windows.DependencyObject> spezifische Instanz für <xref:System.Windows.PropertyChangedCallback> Eigenschaften, ebenso wie Implementierungen, die vom Eigenschaftensystem aufgerufen werden, wenn sich der Wert einer Abhängigkeitseigenschaft ändert. Mithilfe dieser zwei Rückrufe können Sie eine Reihe von Eigenschaften für Elemente erstellen, wobei Änderungen an einer Eigenschaft eine Umwandlung oder eine erneute Auswertung von einer anderen Eigenschaft erzwingt.  
  
 In einem typischen Szenario für die Verwendung einer Bindung von Abhängigkeitseigenschaften gibt es eine von einer Benutzerschnittstelle gesteuerte Eigenschaft, in der das Element jeweils eine Eigenschaft für den minimalen und maximalen Wert enthält, und eine dritte Eigenschaft für den tatsächlichen oder den aktuellen Wert. Wenn das Maximum in diesem Szenario so angepasst würde, dass der aktuelle Wert den neuen Maximalwert übersteigt, sollten Sie es erzwingen, dass der aktuellen Wert nicht größer sein darf als der neue Maximalwert, und eine ähnliche Beziehung für den Minimalwert und den aktuellen Wert festlegen.  
  
 Im Folgenden finden Sie einen sehr kurzen Beispielcode für nur eine der drei Abhängigkeitseigenschaften, die diese Beziehung veranschaulichen. Im Beispiel wird gezeigt, wie die `CurrentReading`-Eigenschaft eines Satzes aus Minimalwert/Maximalwert/aktuellem Wert von verknüpften *Reading-Eigenschaften registriert wird. Die Überprüfung wird hier wie im vorherigen Abschnitt verwendet.  
  
 [!code-csharp[DPCallbackOverride#CurrentDefinitionWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#currentdefinitionwithwrapper)]
 [!code-vb[DPCallbackOverride#CurrentDefinitionWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#currentdefinitionwithwrapper)]  
  
 Das Eigenschaftenänderungsrückrufen für „Current“ wird verwendet, um die Änderung an andere abhängige Eigenschaften weiterzuleiten, indem explizit die Coerce-Wert-Rückrufe aufgerufen werden, die für diese anderen Eigenschaften registriert sind:  
  
 [!code-csharp[DPCallbackOverride#OnPCCurrent](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#onpccurrent)]
 [!code-vb[DPCallbackOverride#OnPCCurrent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#onpccurrent)]  
  
 Der Coerce-Wert-Rückruf überprüft die Werte von Eigenschaften, von denen die aktuelle Eigenschaft potenziell abhängt, und erzwingt bei Bedarf den aktuellen Wert:  
  
 [!code-csharp[DPCallbackOverride#CoerceCurrent](~/samples/snippets/csharp/VS_Snippets_Wpf/DPCallbackOverride/CSharp/SDKSampleLibrary/class1.cs#coercecurrent)]
 [!code-vb[DPCallbackOverride#CoerceCurrent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DPCallbackOverride/visualbasic/sdksamplelibrary/class1.vb#coercecurrent)]  
  
> [!NOTE]
> Standardwerte von Eigenschaften werden nicht erzwungen. Ein Eigenschaftswert, der dem Standardwert entspricht, kann auftreten, wenn ein <xref:System.Windows.DependencyObject.ClearValue%2A>Eigenschaftswert noch seinen ursprünglichen Standardwert hat, oder durch Löschen anderer Werte mit .  
  
 Der Coerce-Wert und die Eigenschaftenänderungsrückrufen sind Teil der Eigenschaftenmetadaten. Da die Rückrufe für eine bestimmte Abhängigkeitseigenschaft auf einem Typ vorhanden sind, die von dem Typ abgeleitet ist, der die Abhängigkeitseigenschaft besitzt, können sie von Ihnen geändert werden, indem die Metadaten für diese Eigenschaft auf Ihrem Typ überschrieben werden.  
  
<a name="Advanced"></a>
## <a name="advanced-coercion-and-callback-scenarios"></a>Erweiterte Umwandlung und Rückrufszenarios  
  
### <a name="constraints-and-desired-values"></a>Einschränkungen und gewünschte Werte  
 Die <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> Rückrufe werden vom Eigenschaftensystem verwendet, um einen Wert gemäß der von Ihnen deklarierten Logik zu erzwangen, aber ein coerced-Wert einer lokal festgelegten Eigenschaft behält intern weiterhin einen "gewünschten Wert". Wenn die Einschränkungen auf anderen Eigenschaftswerten basieren, kann sich dies während der Lebensdauer der Anwendung dynamisch ändern. Die Umwandlungseinschränkungen werden auch dynamisch geändert, und die eingeschränkte Eigenschaft kann ihren Wert ändern, um sich unter den gegebenen neuen Einschränkungen so stark wie möglich dem gewünschten Wert anzunähern. Der Wert entspricht dem gewünschten Wert, wenn alle Einschränkungen aufgehoben werden. Sie können möglicherweise einige recht komplizierte Abhängigkeitsszenarios einführen, wenn Sie über mehrere Eigenschaften verfügen, die zirkulär voneinander abhängig sind. Beispielsweise könnten der Minimal- und Maximalwert im Szenario zum Minimalwert/Maximalwert/aktuellen Wert vom Benutzer einstellbar sein. Wenn dies der Fall ist, müssen Sie erzwingen, dass der Maximalwert immer größer als Minimalwert ist und umgekehrt. Wenn diese Umwandlung aber aktiv ist und der Maximalwert in den Minimalwert umgewandelt wird, bleibt „Current“ in einem nicht festlegbaren Zustand, da es von beiden abhängt und auf den Bereich zwischen den Werten, der 0 (null) entspricht, eingeschränkt ist. Wenn der Maximal- oder Minimalwert dann angepasst wurde, scheint „Current“ einem dieser Werte zu „folgen“, da der gewünschte Wert von „Current“ noch immer gespeichert ist und versucht, den gewünschten Wert zu erreichen, während die Einschränkungen gelockert werden.  
  
 Technisch gesehen gibt es keine Kritik an komplexen Abhängigkeiten. Allerdings können sie leichte Leistungseinbußen mit sich bringen, wenn sie eine große Anzahl von erneuten Auswertung erfordern, und Benutzer verwirren, wenn sie die Benutzeroberfläche direkt beeinflussen. Seien Sie vorsichtig bei Eigenschaftenänderungs- und Coerce-Wert-Rückrufen, und stellen Sie sicher, dass die versuchte Umwandlung so eindeutig wie möglich behandelt werden kann und nicht übermäßig einschränkt.  
  
### <a name="using-coercevalue-to-cancel-value-changes"></a>Abbrechen von Wertänderungen mit CoerceValue  
 Das Eigenschaftensystem behandelt <xref:System.Windows.CoerceValueCallback> alle, <xref:System.Windows.DependencyProperty.UnsetValue> die den Wert zurückgibt, als Sonderfall. Dieser Sonderfall bedeutet, dass die <xref:System.Windows.CoerceValueCallback> Eigenschaftsänderung, die zum Aufruf des Aufrufs geführt hat, vom Eigenschaftensystem abgelehnt werden sollte und dass das Eigenschaftensystem stattdessen den vorherigen Wert der Eigenschaft melden sollte. Dieser Mechanismus kann bei der Überprüfung hilfreich sein, dass asynchron initiierte Änderungen an einer Eigenschaft für den aktuellen Objektzustand noch gültig sind, sowie bei der Unterdrückung dieser Änderungen, sofern sie nicht gültig sind. Ein anderes mögliches Szenario ist die selektive Unterdrückung eines Werts, je nachdem welche der Komponenten der Eigenschaftswertermittlung für den gemeldeten Wert verantwortlich ist. Dazu können Sie den <xref:System.Windows.DependencyProperty> übergebenen Rückruf und den Eigenschaftsbezeichner als Eingabe für <xref:System.Windows.DependencyPropertyHelper.GetValueSource%2A>verwenden und dann die <xref:System.Windows.ValueSource>verarbeiten.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [Metadaten für Abhängigkeitseigenschaften](dependency-property-metadata.md)
- [Benutzerdefinierte Abhängigkeitseigenschaften](custom-dependency-properties.md)
