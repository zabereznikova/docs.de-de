---
title: Bindung als Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: c6a424e085c7499db08d0a7e6b652f45fb2cdd70
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644084"
---
# <a name="binding-markup-extension"></a>Bindung als Markuperweiterung
Verschiebt einen Eigenschaftswert als datengebundenen Wert, erstellt ein Zwischenausdruckobjekt und interpretiert den Datenkontext, der auf das Element und seine Bindung zur Laufzeit angewendet wird.  
  
## <a name="binding-expression-usage"></a>Bindungsexpressionverwendung  
  
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
  
## <a name="syntax-notes"></a>Syntaxhinweise  
 In diesen Syntaxen `[]` `*` sind die und sind keine Literale. Sie sind Teil einer Notation, um anzugeben, dass null oder `,` mehr *bindProp-Wertpaare*`=`*value* verwendet werden können, mit einem Trennzeichen zwischen ihnen und vorangehenden *bindProp-Wertpaaren.*`=`*value*  
  
 Alle Eigenschaften, die im Abschnitt "Binding Properties That Can Be Set with the Binding <xref:System.Windows.Data.Binding> Extension" aufgeführt sind, können stattdessen mithilfe von Attributen eines Objektelements festgelegt werden. Dies ist jedoch nicht wirklich die <xref:System.Windows.Data.Binding>Verwendung von Markuperweiterungen von , es ist nur <xref:System.Windows.Data.Binding> die allgemeine XAML-Verarbeitung von Attributen, die Eigenschaften der CLR-Klasse festlegen. Mit anderen `<Binding` Worten, *bindProp1*`="`*value1* `"[` *bindPropN*`="`*valueN* `"]*/>` ist <xref:System.Windows.Data.Binding> eine äquivalente `Binding` Syntax für Attribute der Objektelementverwendung anstelle einer Ausdrucksverwendung. Weitere Informationen zur Verwendung bestimmter Eigenschaften <xref:System.Windows.Data.Binding>von XAML-Attributen finden Sie im Abschnitt <xref:System.Windows.Data.Binding> "XAML-Attributverwendung" der entsprechenden Eigenschaft in der .NET Framework-Klassenbibliothek.  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Der Name <xref:System.Windows.Data.Binding> der <xref:System.Windows.Data.BindingBase> oder-Eigenschaft, die festgelegt werden soll. Nicht <xref:System.Windows.Data.Binding> alle Eigenschaften können `Binding` mit der Erweiterung festgelegt werden, `Binding` und einige Eigenschaften können nur mithilfe weiterer verschachtelter Markuperweiterungen innerhalb eines Ausdrucks festgelegt werden. Siehe Abschnitt "Binding Properties That Can Be Set with the Binding Extension".|  
|`value1, valueN`|Der für die Eigenschaft festzulegende Wert. Die Behandlung des Attributwerts ist letztlich spezifisch für <xref:System.Windows.Data.Binding> den Typ und die Logik der bestimmten Eigenschaft, die festgelegt wird.|  
|`path`|Die Pfadzeichenfolge, die <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> die implizite Eigenschaft festlegt. Siehe auch [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>UnqualifizierteS "Binding"  
 Die `{Binding}` in "Binding Expression Usage" <xref:System.Windows.Data.Binding> angezeigte Verwendung erstellt ein <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> `null`Objekt mit Standardwerten, das eine Initiale von enthält. Dies ist in vielen Szenarien <xref:System.Windows.Data.Binding> immer noch nützlich, da die <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> erstellten möglicherweise auf Schlüsseldatenbindungseigenschaften basieren, z. B. und <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> die im Laufzeitdatenkontext festgelegt werden. Weitere Informationen zum Konzept des Datenkontexts finden Sie unter [Datenbindung](../../../desktop-wpf/data/data-binding-overview.md).  
  
## <a name="implicit-path"></a>Impliziter Pfad  
 Die `Binding` Markuperweiterung <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> verwendet als konzeptionelle `Path=` "Standardeigenschaft", wobei im Ausdruck nicht angezeigt werden muss. Wenn Sie `Binding` einen Ausdruck mit einem impliziten Pfad angeben, muss der `bindProp` = `value` implizite <xref:System.Windows.Data.Binding> Pfad zuerst im Ausdruck angezeigt werden, vor allen anderen Paaren, bei denen die Eigenschaft durch den Namen angegeben wird. Beispiel: `{Binding PathString}`, `PathString` wobei es sich um eine Zeichenfolge <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> handelt, die als Wert der durch die Markuperweiterungsverwendung <xref:System.Windows.Data.Binding> erstellten Zeichenfolge ausgewertet wird. Sie können einen impliziten Pfad mit anderen benannten Eigenschaften nach `{Binding LastName, Mode=TwoWay}`dem Kommatrennzeichen anfügen, z. B. .  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Bindungseigenschaften, die mit der Bindungserweiterung festgelegt werden können  
 Die in diesem Thema gezeigte Syntax verwendet die generische `bindProp` = `value` Annäherung, <xref:System.Windows.Data.BindingBase> da <xref:System.Windows.Data.Binding> es viele Lese-/Schreibeigenschaften von oder die durch die `Binding` Markuperweiterung / Ausdruckssyntax festgelegt werden können. Sie können in beliebiger Reihenfolge festgelegt werden, mit Ausnahme einer impliziten <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (Sie haben die Möglichkeit, `Path=`explizit anzugeben, in welchem Fall es in beliebiger Reihenfolge festgelegt werden kann). Grundsätzlich können Sie null oder mehr der Eigenschaften in `bindProp` = `value` der Liste unten festlegen, indem Sie Durch Kommas getrennte Paare verwenden.  
  
 Mehrere dieser Eigenschaftswerte erfordern Objekttypen, die keine systemeigene Typkonvertierung aus einer Textsyntax in XAML unterstützen und daher Markuperweiterungen erfordern, um als Attributwert festgelegt zu werden. Überprüfen Sie den Abschnitt XAML-Attributverwendung in der .NET Framework-Klassenbibliothek für jede Eigenschaft auf weitere Informationen. Die Zeichenfolge, die Sie für die XAML-Attributsyntax mit oder ohne weitere Markuperweiterungsverwendung verwenden, entspricht im Wesentlichen dem Wert, den Sie in einem `Binding` Ausdruck angeben, mit der Ausnahme, dass Sie keine Anführungszeichen um `bindProp` = `value` jede im `Binding` Ausdruck platzieren.  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: eine Zeichenfolge, die eine mögliche Bindungsgruppe identifiziert. Dies ist ein relativ fortschrittliches Bindungskonzept; siehe Referenzseite <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>für .  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolean, kann `true` `false`entweder oder sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: `bindProp` = `value` kann als Zeichenfolge im Ausdruck festgelegt werden, erfordert jedoch dazu einen Objektverweis für den Wert, z. B. eine [StaticResource Markup Extension](staticresource-markup-extension.md). Der Wert in diesem Fall ist eine Instanz einer benutzerdefinierten Konverterklasse.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: Setzbar im Ausdruck als standardbasierter Bezeichner; siehe Referenzthema <xref:System.Windows.Data.Binding.ConverterCulture%2A>für .  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: kann als `bindProp` = `value` Zeichenfolge im Ausdruck festgelegt werden, dies hängt jedoch vom Typ des übergebenen Parameters ab. Wenn Sie einen Verweistyp für den Wert übergeben, erfordert diese Verwendung einen Objektverweis, z. B. eine geschachtelte [StaticResource Markup Extension](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: sich gegenseitig <xref:System.Windows.Data.Binding.RelativeSource%2A> <xref:System.Windows.Data.Binding.Source%2A>ausschließend versus ; jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethode dar. Siehe [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: kann als `bindProp` = `value` Zeichenfolge im Ausdruck festgelegt werden, dies hängt jedoch vom Typ des übergebenen Werts ab. Wenn ein Verweistyp übergeben wird, ist ein Objektverweis erforderlich, z. B. eine geschachtelte [StaticResource Markup Extension](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolean, kann `true` `false`entweder oder sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *Der Wert* ist <xref:System.Windows.Data.BindingMode> ein konstanter Name aus der Enumeration. Beispielsweise `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolean, kann `true` `false`entweder oder sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolean, kann `true` `false`entweder oder sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolean, kann `true` `false`entweder oder sein. Der Standardwert ist `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>: eine Zeichenfolge, die einen Pfad in ein Datenobjekt oder ein allgemeines Objektmodell beschreibt. Das Format bietet mehrere verschiedene Konventionen zum Durchlaufen eines Objektmodells, das in diesem Thema nicht angemessen beschrieben werden kann. Siehe [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: sich gegenseitig <xref:System.Windows.Data.Binding.ElementName%2A> ausschließen <xref:System.Windows.Data.Binding.Source%2A>d. R. mit und ; jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethode dar. Siehe [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md). Erfordert eine geschachtelte [RelativeSource MarkupExtension-Verwendung,](relativesource-markupextension.md) um den Wert anzugeben.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: sich gegenseitig <xref:System.Windows.Data.Binding.RelativeSource%2A> <xref:System.Windows.Data.Binding.ElementName%2A>ausschließend versus ; jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethode dar. Siehe [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md). Erfordert eine geschachtelte Erweiterungsverwendung, in der Regel eine [StaticResource Markup-Erweiterung,](staticresource-markup-extension.md) die auf eine Objektdatenquelle aus einem Schlüsselressourcenwörterbuch verweist.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>: eine Zeichenfolge, die eine Zeichenfolgenformatkonvention für die gebundenen Daten beschreibt. Dies ist ein relativ fortschrittliches Bindungskonzept; siehe Referenzseite <xref:System.Windows.Data.BindingBase.StringFormat%2A>für .  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: kann als `bindProp` = `value` Zeichenfolge im Ausdruck festgelegt werden, dies hängt jedoch vom Typ des übergebenen Parameters ab. Wenn sie einen Verweistyp für den Wert übergeben, ist ein Objektverweis erforderlich, z. B. eine geschachtelte [StaticResource Markup Extension](staticresource-markup-extension.md).  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *Der Wert* ist <xref:System.Windows.Data.UpdateSourceTrigger> ein konstanter Name aus der Enumeration. Beispielsweise `{Binding UpdateSourceTrigger=LostFocus}`. Bestimmte Steuerelemente haben möglicherweise unterschiedliche Standardwerte für diese Bindungseigenschaft. Siehe <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolean, kann `true` `false`entweder oder sein. Der Standardwert ist `false`. Siehe Hinweise.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolean, kann `true` `false`entweder oder sein. Der Standardwert ist `false`. Siehe Hinweise.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>: eine Zeichenfolge, die einen Pfad in das XMLDOM einer XML-Datenquelle beschreibt. Siehe [Binden an XML-Daten mithilfe eines XMLDataProvider- und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Die folgenden Eigenschaften <xref:System.Windows.Data.Binding> davon können nicht `Binding` mithilfe des`{Binding}` Markuperweiterungs-/Ausdrucksformulars festgelegt werden.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: Diese Eigenschaft erwartet einen Verweis auf eine Rückrufimplementierung. Auf Rückrufe/Methoden, die nicht auf Ereignishandler anzurechnen sind, kann in der XAML-Syntax nicht verwiesen werden.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: Die Eigenschaft nimmt <xref:System.Windows.Controls.ValidationRule> eine generische Auflistung von Objekten. Dies kann als Eigenschaftselement <xref:System.Windows.Data.Binding> in einem Objektelement ausgedrückt werden, verfügt jedoch `Binding` über keine leicht verfügbare Attributanalysetechnik für die Verwendung in einem Ausdruck. Siehe Referenzthema <xref:System.Windows.Data.Binding.ValidationRules%2A>für .  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Bemerkungen  
  
> [!IMPORTANT]
> In Bezug auf die `Binding` Priorität der Abhängigkeitseigenschaft entspricht ein Ausdruck einem lokal festgelegten Wert. Wenn Sie einen lokalen Wert für eine `Binding` Eigenschaft `Binding` festlegen, die zuvor über einen Ausdruck verfügte, wird der vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).  
  
 Das Beschreiben der Datenbindung auf einer grundlegenden Ebene wird in diesem Thema nicht behandelt. Siehe [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding>und <xref:System.Windows.Data.PriorityBinding> unterstützen keine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Erweiterungssyntax. Stattdessen würden Sie Eigenschaftselemente verwenden. Siehe Referenzthemen <xref:System.Windows.Data.MultiBinding> <xref:System.Windows.Data.PriorityBinding>für und .  
  
 Boolesche Werte für XAML werden von der Groß-/Kleinschreibung nicht berücksichtigt. Sie können z. `{Binding NotifyOnValidationError=true}` `{Binding NotifyOnValidationError=True}`B. entweder oder angeben.  
  
 Bindungen, die eine Datenüberprüfung beinhalten, `Binding` werden in `{Binding ...}` der Regel <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> durch <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> ein explizites Element und nicht als Ausdruck angegeben, und das Festlegen oder in einem Ausdruck ist ungewöhnlich. Dies liegt daran, dass die companion-Eigenschaft <xref:System.Windows.Data.Binding.ValidationRules%2A> nicht ohne weiteres im Ausdrucksformular festgelegt werden kann. Weitere Informationen finden Sie unter Implementieren der [Bindungsvalidierung](../data/how-to-implement-binding-validation.md).  
  
 `Binding` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte nicht literale Werte oder Handlernamen entfernt werden müssen, und die Anforderung globaler ist als Typkonverter, die bestimmten Typen oder Eigenschaften zugeordnet sind. Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in ihrer Attributsyntax, d. h. die Konvention, nach der ein XAML-Prozessor erkennt, dass eine Markuperweiterung den Zeichenfolgeninhalt verarbeiten muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
 `Binding`ist eine atypische Markuperweiterung, da die <xref:System.Windows.Data.Binding> Klasse, die die Erweiterungsfunktionalität für die XAML-Implementierung von WPF implementiert, auch mehrere andere Methoden und Eigenschaften implementiert, die nicht mit XAML verknüpft sind. Die anderen Member sollen <xref:System.Windows.Data.Binding> eine vielseitigere und eigenständigere Klasse erstellen, die viele Datenbindungsszenarien zusätzlich zur Funktion als XAML-Markuperweiterung adressieren kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding>
- [Datenbindung sübersicht](../../../desktop-wpf/data/data-binding-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
