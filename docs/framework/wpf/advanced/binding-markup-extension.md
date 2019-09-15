---
title: Bindung als Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: 6776c89db474668b3aed0e38a3e18359bf93399d
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991483"
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
 In diesen Syntaxen `[]` sind und `*` keine Literale. Sie sind Teil einer Notation, um anzugeben, dass NULL oder mehr *BindProp*`=`-*Wertpaare* verwendet werden können, `,` wobei ein Trennzeichen zwischen Ihnen und vorangehenden *BindProp*`=`-*Wertpaaren* verwendet werden kann.  
  
 Alle Eigenschaften, die im Abschnitt "Bindungseigenschaften, die mit der Bindungs Erweiterung festgelegt werden können" aufgelistet sind, können stattdessen mithilfe der Attribute <xref:System.Windows.Data.Binding> eines-Objekt Elements festgelegt werden. Dies ist jedoch nicht wirklich die Verwendung der Markup Erweiterung von <xref:System.Windows.Data.Binding>, sondern lediglich die allgemeine XAML-Verarbeitung von Attributen, die Eigenschaften der CLR <xref:System.Windows.Data.Binding> -Klasse festlegen. Anders ausgedrückt: `<Binding` *bindProp1*`="`*value1* *bindpropn* *valueN ist eine* äquivalente Syntax für Attribute der <xref:System.Windows.Data.Binding> Verwendung von Objekt Elementen.`"]*/>` `="``"[` anstelle einer `Binding` Ausdrucks Verwendung. Weitere Informationen zur Verwendung von XAML-Attributen für bestimmte Eigenschaften <xref:System.Windows.Data.Binding>von finden Sie im Abschnitt "XAML-Attribut Verwendung" der entsprechenden Eigenschaft <xref:System.Windows.Data.Binding> von in der .NET Framework-Klassenbibliothek.  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Der Name <xref:System.Windows.Data.Binding> der festzulegenden-Eigenschaft oder <xref:System.Windows.Data.BindingBase> der-Eigenschaft. Nicht alle <xref:System.Windows.Data.Binding> Eigenschaften können mit der `Binding` Erweiterung festgelegt werden, und einige Eigenschaften können nur in einem `Binding` Ausdruck mithilfe weiterer geschachtelter Markup Erweiterungen festgelegt werden. Weitere Informationen finden Sie im Abschnitt "Bindungseigenschaften, die mit der Bindungs Erweiterung festgelegt werden können".|  
|`value1, valueN`|Der Wert, auf den die Eigenschaft festgelegt werden soll. Die Behandlung des Attribut Werts ist letztendlich spezifisch für den Typ und die Logik der <xref:System.Windows.Data.Binding> festzulegenden Eigenschaft.|  
|`path`|Die Pfad Zeichenfolge, die <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> die implizite Eigenschaft festlegt. Siehe auch [PropertyPath-XAML-Syntax](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Nicht qualifiziert {Binding}  
 Die `{Binding}` in "Verwendung von Bindungs Ausdrücken" gezeigte Verwendung erstellt <xref:System.Windows.Data.Binding> ein-Objekt mit Standardwerten, das eine <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> anfängliche `null`von enthält. Dies ist in vielen Szenarios immer noch nützlich, da <xref:System.Windows.Data.Binding> der erstellte möglicherweise auf Schlüsseldaten Bindungseigenschaften, <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> wie <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> z. b., und festgelegt wird, die im Laufzeitdaten Kontext festgelegt werden. Weitere Informationen zum Konzept des Daten Kontexts finden Sie unter [Datenbindung](../data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Impliziter Pfad  
 Die `Binding` Markup Erweiterung verwendet <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> als konzeptionelle "Standard Eigenschaft", wobei `Path=` nicht im Ausdruck angezeigt werden muss. Wenn Sie `Binding` einen Ausdruck mit einem impliziten Pfad angeben, muss der implizite Pfad vor allen anderen = `bindProp` `value` Paaren, in denen die Eigenschaft anhand des <xref:System.Windows.Data.Binding> namens angegeben wird, zuerst im Ausdruck angezeigt werden. Beispiel: `{Binding PathString}`, wobei `PathString` eine Zeichenfolge ist, die als Wert von <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> <xref:System.Windows.Data.Binding> ausgewertet wird, der von der Markup Erweiterungs Verwendung erstellt wurde. Sie können nach dem Komma Trennzeichen einen impliziten Pfad mit anderen benannten Eigenschaften anfügen, z `{Binding LastName, Mode=TwoWay}`. b.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Bindungseigenschaften, die mit der Bindungs Erweiterung festgelegt werden können  
 Die in diesem Thema gezeigte Syntax verwendet die generische `bindProp` <xref:System.Windows.Data.Binding> = `value` Näherung, da viele Lese-/Schreibeigenschaften von <xref:System.Windows.Data.BindingBase> oder vorhanden sind, die `Binding` durch die Markup Erweiterung festgelegt werden können. Ausdruckssyntax. Sie können in beliebiger Reihenfolge festgelegt werden, mit Ausnahme eines <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>impliziten. (Sie haben die Möglichkeit, explizit anzugeben `Path=`. in diesem Fall kann Sie in beliebiger Reihenfolge festgelegt werden.) Im Grunde können Sie in der folgenden Liste NULL oder mehr Eigenschaften festlegen, indem Sie durch `bindProp` Kommas getrennte Paare verwenden = `value` .  
  
 Einige dieser Eigenschaftswerte erfordern Objekttypen, die keine systemeigene Typkonvertierung aus einer Text Syntax in XAML unterstützen. Daher benötigen Sie Markup Erweiterungen, damit Sie als Attribut Wert festgelegt werden können. Weitere Informationen finden Sie im Abschnitt "XAML-Attribut Verwendung" in der .NET Framework-Klassenbibliothek für jede Eigenschaft. die Zeichenfolge, die Sie für die XAML-Attribut Syntax mit oder ohne weitere Markup Erweiterungs Verwendung verwenden, ist im Grunde identisch mit `Binding` dem Wert, den Sie in einem Ausdruck angeben, mit der Ausnahme, `bindProp` dass Sie keine Anführungszeichen herum =platzieren.imAusdruck. `value` `Binding`  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: eine Zeichenfolge, die eine mögliche Bindungs Gruppe identifiziert. Dies ist ein relativ erweitertes Bindungs Konzept. Siehe Referenzseite für <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Die Standardeinstellung ist `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: kann im `bindProp` Ausdruck als = `value` Zeichenfolge festgelegt werden, aber hierfür ist ein Objekt Verweis für den Wert erforderlich, z. b. eine [statikresource-Markup Erweiterung](staticresource-markup-extension.md). Der Wert in diesem Fall ist eine Instanz einer benutzerdefinierten Konverterklasse.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: kann im Ausdruck als Standard basierter Bezeichner festgelegt werden. Weitere Informationen finden Sie im <xref:System.Windows.Data.Binding.ConverterCulture%2A>Referenz Thema für.  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: kann im Ausdruck als `bindProp` = `value` Zeichenfolge festgelegt werden. Dies ist jedoch abhängig vom Typ des übergebenen Parameters. Wenn Sie einen Verweistyp für den Wert übergeben, erfordert diese Verwendung einen Objekt Verweis, z. b. eine eingefügte [statikresource-Markup Erweiterung](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: Schließen Sie gegen <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.Source%2A>gegenseitig aus. jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethode dar. Siehe [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: kann im Ausdruck als `bindProp` = `value` Zeichenfolge festgelegt werden. Dies ist jedoch abhängig vom Typ des Werts, der weitergegeben wird. Wenn ein Verweistyp übergeben wird, ist ein Objekt Verweis erforderlich, wie z. b. eine [eingefügte statikresource-Markup Erweiterung](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Die Standardeinstellung ist `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *value* ist ein konstanter Name aus der <xref:System.Windows.Data.BindingMode> -Enumeration. Beispielsweise `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Die Standardeinstellung ist `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Die Standardeinstellung ist `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Die Standardeinstellung ist `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: eine Zeichenfolge, die einen Pfad zu einem Datenobjekt oder einem allgemeinen Objektmodell beschreibt. Das-Format bietet verschiedene Konventionen für das Durchlaufen eines Objektmodells, das in diesem Thema nicht ausreichend beschrieben werden kann. Siehe [PropertyPath-XAML-Syntax](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: gegenseitig ausschließende <xref:System.Windows.Data.Binding.ElementName%2A> und <xref:System.Windows.Data.Binding.Source%2A>mit und. jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethode dar. Siehe [Übersicht über die Datenbindung](../data/data-binding-overview.md). Erfordert die Verwendung der Verwendung von " [RelativeSource MarkupExtension](relativesource-markupextension.md) ", um den Wert anzugeben.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: Schließen Sie gegen <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.ElementName%2A>gegenseitig aus. jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethode dar. Siehe [Übersicht über die Datenbindung](../data/data-binding-overview.md). Erfordert eine geschmestete Erweiterungs Verwendung, in der Regel eine [statikresource-Markup Erweiterung](staticresource-markup-extension.md) , die auf eine Objektdaten Quelle aus einem Schlüsselwörter-Schlüssel Wörterbuch verweist.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: eine Zeichenfolge, die eine Zeichen folgen-Format Konvention für die gebundenen Daten beschreibt. Dies ist ein relativ erweitertes Bindungs Konzept. Siehe Referenzseite für <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: kann im Ausdruck als `bindProp` = `value` Zeichenfolge festgelegt werden. Dies ist jedoch abhängig vom Typ des übergebenen Parameters. Wenn Sie einen Verweistyp für den Wert übergeben, ist ein Objekt Verweis erforderlich, wie z. b. eine [eingefügte statikresource-Markup Erweiterung](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *value* ist ein konstanter Name aus der <xref:System.Windows.Data.UpdateSourceTrigger> -Enumeration. Beispielsweise `{Binding UpdateSourceTrigger=LostFocus}`. Bestimmte Steuerelemente haben möglicherweise unterschiedliche Standardwerte für diese Bindungs Eigenschaft. Siehe <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Die Standardeinstellung ist `false`. Siehe Hinweise.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolescher Wert kann entweder `true` oder `false`sein. Die Standardeinstellung ist `false`. Siehe Hinweise.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: eine Zeichenfolge, die einen Pfad zum XMLDOM einer XML-Datenquelle beschreibt. Weitere Informationen finden [Sie unterbinden an XML-Daten mithilfe von XmlDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Die folgenden Eigenschaften von <xref:System.Windows.Data.Binding> können nicht über das `Binding` Formular für Markup Erweiterung/`{Binding}` Ausdruck festgelegt werden.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: Diese Eigenschaft erwartet einen Verweis auf eine Rückruf Implementierung. Auf Rückrufe bzw. andere Methoden als Ereignishandler kann nicht in der XAML-Syntax verwiesen werden.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: die-Eigenschaft nimmt eine generische Auflistung <xref:System.Windows.Controls.ValidationRule> von-Objekten an. Dies könnte als Eigenschafts Element in einem <xref:System.Windows.Data.Binding> -Objekt Element ausgedrückt werden, verfügt jedoch nicht über eine nicht sofort verfügbare Attribut-zu-Methode für die Verwendung in einem `Binding` -Ausdruck. Informationen hierzu finden Sie <xref:System.Windows.Data.Binding.ValidationRules%2A>im Referenz Thema.  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
> Im Hinblick auf die Rangfolge der Abhängigkeits Eigenschaften entspricht ein `Binding` -Ausdruck einem lokal festgelegten Wert. Wenn Sie einen lokalen Wert für eine Eigenschaft festlegen, die zuvor einen `Binding` -Ausdruck enthielt `Binding` , wird der vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).  
  
 Das Beschreiben der Datenbindung auf der Basisebene wird in diesem Thema nicht behandelt. Siehe [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding><xref:System.Windows.Data.PriorityBinding> und[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] unterstützen keine Erweiterungs Syntax. Stattdessen verwenden Sie Eigenschafts Elemente. Weitere Informationen finden Sie <xref:System.Windows.Data.MultiBinding> unter <xref:System.Windows.Data.PriorityBinding>Referenz Themen für und.  
  
 Bei booleschen Werten für XAML wird Groß-/Kleinschreibung nicht beachtet. Beispielsweise können Sie entweder `{Binding NotifyOnValidationError=true}` oder `{Binding NotifyOnValidationError=True}`angeben.  
  
 Bindungen, die Daten validieren, werden in der Regel `Binding` durch ein explizites `{Binding ...}` -Element anstelle eines <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> - <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> Ausdrucks angegeben, und das Festlegen von oder in einem Ausdruck ist nicht üblich. Dies liegt daran, dass die <xref:System.Windows.Data.Binding.ValidationRules%2A> Begleit Eigenschaft nicht im Ausdrucks Formular problemlos festgelegt werden kann. Weitere Informationen finden Sie unter [Implementieren der Bindungs Validierung](../data/how-to-implement-binding-validation.md).  
  
 `Binding` ist eine Markuperweiterung. Markup Erweiterungen werden in der Regel implementiert, wenn es erforderlich ist, Attributwerte als literale Werte oder Handlernamen zu versehen, und die Anforderung ist globaler als Typkonverter, die auf bestimmte Typen oder Eigenschaften zurückzuführen sind. Alle Markup Erweiterungen in XAML verwenden die `{` Zeichen `}` und in der Attribut Syntax. Dies ist die Konvention, mit der ein XAML-Prozessor erkennt, dass eine Markup Erweiterung den Zeichen folgen Inhalt verarbeiten muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
 `Binding`ist eine atypische Markup Erweiterung darin, <xref:System.Windows.Data.Binding> dass die Klasse, die die Erweiterungsfunktionen für die XAML-Implementierung von WPF implementiert, auch mehrere andere Methoden und Eigenschaften implementiert, die nicht mit XAML verknüpft sind. Die anderen Member sind dazu gedacht, <xref:System.Windows.Data.Binding> eine vielseitige und eigenständige Klasse zu erstellen, die viele Daten Bindungs Szenarien adressieren kann, zusätzlich zur Funktion als XAML-Markup Erweiterung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding>
- [Übersicht zur Datenbindung](../data/data-binding-overview.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
