---
title: Bindung als Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: d0a437e756da16db978d8074c4355fd83d211b67
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453609"
---
# <a name="binding-markup-extension"></a>Bindung als Markuperweiterung
Gibt an, dass ein Eigenschafts Wert ein Daten gebundener Wert ist, indem ein zwischen Ausdrucks Objekt erstellt und der Datenkontext interpretiert wird, der für das Element und seine Bindung zur Laufzeit gilt.  
  
## <a name="binding-expression-usage"></a>Verwendung des Bindungs Ausdrucks  
  
```xaml  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## <a name="syntax-notes"></a>Syntax Hinweise  
 In diesen Syntaxen sind die `[]` und `*` keine Literale. Sie sind Teil einer Notation, um anzugeben, dass NULL oder mehr *BindProp* -`=`*Wertpaare* verwendet werden können, wobei ein `,` Trennzeichen zwischen Ihnen und vorangehenden *BindProp* -`=`*Wert* -Paaren verwendet werden kann.  
  
 Alle Eigenschaften, die im Abschnitt "Bindungseigenschaften, die mit der Bindungs Erweiterung festgelegt werden können" aufgelistet sind, können stattdessen mithilfe von Attributen eines <xref:System.Windows.Data.Binding> Object-Elements festgelegt werden. Dies ist jedoch nicht wirklich die Markup Erweiterungs Verwendung von <xref:System.Windows.Data.Binding>, sondern nur die allgemeine XAML-Verarbeitung von Attributen, die Eigenschaften der CLR-<xref:System.Windows.Data.Binding> Klasse festlegen. Anders ausgedrückt: `<Binding` *bindProp1*`="`*value1*`"[` *bindpropn*`="`*valueN*`"]*/>` ist eine äquivalente Syntax für Attribute der <xref:System.Windows.Data.Binding> Objekt Element Verwendung anstelle einer `Binding` Ausdrucks Verwendung. Informationen zur Verwendung des XAML-Attributs für bestimmte Eigenschaften <xref:System.Windows.Data.Binding>finden Sie im Abschnitt "XAML-Attribut Verwendung" der entsprechenden Eigenschaft <xref:System.Windows.Data.Binding> in der .NET Framework-Klassenbibliothek.  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Der Name der festzulegenden <xref:System.Windows.Data.Binding> oder <xref:System.Windows.Data.BindingBase> Eigenschaft. Nicht alle <xref:System.Windows.Data.Binding> Eigenschaften können mit der `Binding`-Erweiterung festgelegt werden, und einige Eigenschaften können nur in einem `Binding` Ausdruck festgelegt werden, indem weitere geschachtelte Markup Erweiterungen verwendet werden. Weitere Informationen finden Sie im Abschnitt "Bindungseigenschaften, die mit der Bindungs Erweiterung festgelegt werden können".|  
|`value1, valueN`|Der Wert, auf den die Eigenschaft festgelegt werden soll. Die Behandlung des Attribut Werts ist letztendlich spezifisch für den Typ und die Logik der spezifischen <xref:System.Windows.Data.Binding> Eigenschaft, die festgelegt wird.|  
|`path`|Die Pfad Zeichenfolge, die die implizite <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> Eigenschaft festlegt. Siehe auch [PropertyPath-XAML-Syntax](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Nicht qualifiziert {Binding}  
 Die in "Verwendung von Bindungs Ausdrücken" angezeigte `{Binding}` Verwendung erstellt ein <xref:System.Windows.Data.Binding>-Objekt mit Standardwerten, das eine anfängliche <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> `null`enthält. Dies ist in vielen Szenarien weiterhin nützlich, da sich die erstellten <xref:System.Windows.Data.Binding> möglicherweise auf Schlüsseldaten Bindungseigenschaften wie <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> und <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType>, die im Laufzeitdaten Kontext festgelegt werden. Weitere Informationen zum Konzept des Daten Kontexts finden Sie unter [Datenbindung](../data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Impliziter Pfad  
 Die `Binding` Markup Erweiterung verwendet <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> als konzeptionelle Standard Eigenschaft, bei der `Path=` nicht im Ausdruck angezeigt werden muss. Wenn Sie einen `Binding` Ausdruck mit einem impliziten Pfad angeben, muss der implizite Pfad vor allen anderen `bindProp`=`value` Paaren, in denen die <xref:System.Windows.Data.Binding>-Eigenschaft mit dem Namen angegeben ist, zuerst im Ausdruck angezeigt werden. Beispiel: `{Binding PathString}`, wobei `PathString` eine Zeichenfolge ist, die als Wert von <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> in der von der Markup Erweiterungs Verwendung erstellten <xref:System.Windows.Data.Binding> ausgewertet wird. Sie können einen impliziten Pfad mit anderen benannten Eigenschaften nach dem Komma Trennzeichen anfügen, z. b. `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Bindungseigenschaften, die mit der Bindungs Erweiterung festgelegt werden können  
 Die in diesem Thema gezeigte Syntax verwendet den generischen `bindProp`=`value` Näherungswert, da viele Lese-/Schreibeigenschaften von <xref:System.Windows.Data.BindingBase> oder <xref:System.Windows.Data.Binding> vorhanden sind, die über die Syntax der `Binding` Markup Erweiterung/Ausdruck festgelegt werden können. Sie können mit Ausnahme eines impliziten <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>in beliebiger Reihenfolge festgelegt werden. (Sie haben die Möglichkeit, `Path=`explizit anzugeben. in diesem Fall kann Sie in beliebiger Reihenfolge festgelegt werden.) Im Grunde können Sie in der folgenden Liste NULL oder mehr Eigenschaften festlegen, indem Sie `bindProp`=`value` durch Kommas getrennte Paare verwenden.  
  
 Einige dieser Eigenschaftswerte erfordern Objekttypen, die keine systemeigene Typkonvertierung aus einer Text Syntax in XAML unterstützen. Daher benötigen Sie Markup Erweiterungen, damit Sie als Attribut Wert festgelegt werden können. Weitere Informationen finden Sie im Abschnitt "XAML-Attribut Verwendung" in der .NET Framework-Klassenbibliothek für jede Eigenschaft. die Zeichenfolge, die Sie für die XAML-Attribut Syntax mit oder ohne weitere Markup Erweiterungs Verwendung verwenden, ist im Grunde identisch mit dem Wert, den Sie in einem `Binding` Ausdruck angeben, mit der Ausnahme, dass Sie die einzelnen `bindProp`=`value` nicht in Anführungszeichen setzen. der `Binding` Ausdruck.  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: eine Zeichenfolge, die eine mögliche Bindungs Gruppe identifiziert. Dies ist ein relativ erweitertes Bindungs Konzept. <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>finden Sie unter Referenzseite.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: kann als `bindProp`=`value` Zeichenfolge im Ausdruck festgelegt werden. hierfür ist jedoch ein Objekt Verweis für den Wert erforderlich, z. b. eine [statikresource-Markup Erweiterung](staticresource-markup-extension.md). Der Wert in diesem Fall ist eine Instanz einer benutzerdefinierten Konverterklasse.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: kann im Ausdruck als Standard basierter Bezeichner festgelegt werden. Weitere Informationen zu <xref:System.Windows.Data.Binding.ConverterCulture%2A>finden Sie im Referenz Thema.  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: kann als `bindProp`=`value` Zeichenfolge im Ausdruck festgelegt werden. Dies ist jedoch abhängig vom Typ des übergebenen Parameters. Wenn Sie einen Verweistyp für den Wert übergeben, erfordert diese Verwendung einen Objekt Verweis, z. b. eine eingefügte [statikresource-Markup Erweiterung](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: gegenseitig ausschließende und <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.Source%2A>; Jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethode dar. Siehe [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: kann als `bindProp`=`value` Zeichenfolge im Ausdruck festgelegt werden. Dies ist jedoch abhängig vom Typ des Werts, der weitergegeben wird. Wenn ein Verweistyp übergeben wird, ist ein Objekt Verweis erforderlich, wie z. b. eine [eingefügte statikresource-Markup Erweiterung](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: der *Wert* ist ein konstanter Name aus der <xref:System.Windows.Data.BindingMode> Enumeration. Beispielsweise `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: eine Zeichenfolge, die einen Pfad zu einem Datenobjekt oder einem allgemeinen Objektmodell beschreibt. Das-Format bietet verschiedene Konventionen für das Durchlaufen eines Objektmodells, das in diesem Thema nicht ausreichend beschrieben werden kann. Siehe [PropertyPath-XAML-Syntax](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: gegenseitig ausschließende und mit <xref:System.Windows.Data.Binding.ElementName%2A> und <xref:System.Windows.Data.Binding.Source%2A>; Jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethode dar. Siehe [Übersicht über die Datenbindung](../data/data-binding-overview.md). Erfordert die Verwendung der Verwendung von " [RelativeSource MarkupExtension](relativesource-markupextension.md) ", um den Wert anzugeben.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: gegenseitig ausschließende und <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.ElementName%2A>; Jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethode dar. Siehe [Übersicht über die Datenbindung](../data/data-binding-overview.md). Erfordert eine geschmestete Erweiterungs Verwendung, in der Regel eine [statikresource-Markup Erweiterung](staticresource-markup-extension.md) , die auf eine Objektdaten Quelle aus einem Schlüsselwörter-Schlüssel Wörterbuch verweist.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: eine Zeichenfolge, die eine Zeichen folgen-Format Konvention für die gebundenen Daten beschreibt. Dies ist ein relativ erweitertes Bindungs Konzept. <xref:System.Windows.Data.BindingBase.StringFormat%2A>finden Sie unter Referenzseite.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: kann als `bindProp`=`value` Zeichenfolge im Ausdruck festgelegt werden. Dies ist jedoch abhängig vom Typ des übergebenen Parameters. Wenn Sie einen Verweistyp für den Wert übergeben, ist ein Objekt Verweis erforderlich, wie z. b. eine [eingefügte statikresource-Markup Erweiterung](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: der *Wert* ist ein konstanter Name aus der <xref:System.Windows.Data.UpdateSourceTrigger> Enumeration. Beispielsweise `{Binding UpdateSourceTrigger=LostFocus}`. Bestimmte Steuerelemente haben möglicherweise unterschiedliche Standardwerte für diese Bindungs Eigenschaft. Siehe <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Der Standardwert ist `false`. Siehe Hinweise.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Der Standardwert ist `false`. Siehe Hinweise.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: eine Zeichenfolge, die einen Pfad zum XMLDOM einer XML-Datenquelle beschreibt. Weitere Informationen finden [Sie unterbinden an XML-Daten mithilfe von XmlDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Die folgenden Eigenschaften von <xref:System.Windows.Data.Binding>, die nicht mit dem Formular `Binding` Markup Erweiterung/`{Binding}` Ausdruck festgelegt werden können.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: Diese Eigenschaft erwartet einen Verweis auf eine Rückruf Implementierung. Auf Rückrufe bzw. andere Methoden als Ereignishandler kann nicht in der XAML-Syntax verwiesen werden.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: die Eigenschaft nimmt eine generische Auflistung von <xref:System.Windows.Controls.ValidationRule> Objekten an. Dies könnte als Eigenschafts Element in einem <xref:System.Windows.Data.Binding> Object-Element ausgedrückt werden, verfügt jedoch nicht über eine nicht sofort verfügbare Attribut-zu-Methode für die Verwendung in einem `Binding` Ausdruck. <xref:System.Windows.Data.Binding.ValidationRules%2A>finden Sie im Referenz Thema.  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
> Im Hinblick auf die Rangfolge der Abhängigkeits Eigenschaften entspricht ein `Binding` Ausdruck einem lokal festgelegten Wert. Wenn Sie einen lokalen Wert für eine Eigenschaft festgelegt haben, die zuvor einen `Binding` Ausdruck enthielt, wird die `Binding` vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).  
  
 Das Beschreiben der Datenbindung auf der Basisebene wird in diesem Thema nicht behandelt. Siehe [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
> [!NOTE]
> eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Erweiterungs Syntax wird von <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding> nicht unterstützt. Stattdessen verwenden Sie Eigenschafts Elemente. Informationen zu <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding>finden Sie in den Referenz Themen.  
  
 Bei booleschen Werten für XAML wird Groß-/Kleinschreibung nicht beachtet. Beispielsweise können Sie entweder `{Binding NotifyOnValidationError=true}` oder `{Binding NotifyOnValidationError=True}`angeben.  
  
 Bindungen, die die Datenvalidierung einbeziehen, werden in der Regel durch ein explizites `Binding` Element anstelle von `{Binding ...}` Ausdruck angegeben, und das Festlegen von <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> oder <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> in einem Ausdruck ist nicht üblich. Dies liegt daran, dass die <xref:System.Windows.Data.Binding.ValidationRules%2A> der Begleit Eigenschaft im Ausdrucks Formular nicht leicht festgelegt werden kann. Weitere Informationen finden Sie unter [Implementieren der Bindungs Validierung](../data/how-to-implement-binding-validation.md).  
  
 `Binding` ist eine Markuperweiterung. Markup Erweiterungen werden in der Regel implementiert, wenn es erforderlich ist, Attributwerte als literale Werte oder Handlernamen zu versehen, und die Anforderung ist globaler als Typkonverter, die auf bestimmte Typen oder Eigenschaften zurückzuführen sind. Alle Markup Erweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attribut Syntax. Dies ist die Konvention, mit der ein XAML-Prozessor erkennt, dass eine Markup Erweiterung den Zeichen folgen Inhalt verarbeiten muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
 `Binding` ist eine atypische Markup Erweiterung darin, dass die <xref:System.Windows.Data.Binding> Klasse, die die Erweiterungsfunktionen für die XAML-Implementierung von WPF implementiert, auch mehrere andere Methoden und Eigenschaften implementiert, die nicht mit XAML verknüpft sind. Die anderen Member sind dazu gedacht, <xref:System.Windows.Data.Binding> eine viel vielseitigere und eigenständige Klasse zu machen, die viele Daten Bindungs Szenarien adressieren kann, zusätzlich zur Funktion als XAML-Markup Erweiterung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding>
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
