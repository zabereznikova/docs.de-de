---
title: Bindung als Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: 8fc860f52f8fde2aed3cae224c05bbcf08b864d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541884"
---
# <a name="binding-markup-extension"></a>Bindung als Markuperweiterung
Orientiert sich einen Eigenschaftswert, um einem datengebundenen Wert und einen intermediate Expression-Objekt erstellen und zum Interpretieren der Datenkontext, der auf das Element und seine Bindung zur Laufzeit angewendet wird.  
  
## <a name="binding-expression-usage"></a>Bindung Ausdruck Nutzung  
  
```  
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
 In der folgenden Syntax die `[]` und `*` sind keine Literale. Sie sind Bestandteil der eine Notation, um anzugeben, dass NULL oder mehr *BindProp*`=`*Wert* Paare verwendet werden können, mit einer `,` als Trennzeichen zwischen Ihnen und vorherigen *BindProp*  `=` *Wert* Paare.  
  
 Die Eigenschaften im Abschnitt "Binden, können werden legen Sie mit der Bindung Erweiterungseigenschaften" aufgeführten konnte stattdessen festgelegt werden mithilfe von Attributen von einem <xref:System.Windows.Data.Binding> Object-Element. Das ist allerdings nicht tatsächlich die Markuperweiterungsverwendung von <xref:System.Windows.Data.Binding>, es ist nur die allgemeine XAML-Verarbeitung von Attributen, die Eigenschaften der CLR festlegen <xref:System.Windows.Data.Binding> Klasse. Das heißt, `<Binding` *bindProp1*`="`*value1* `"[` *BindPropN*`="`*Wertn* `"]*/>` ist eine entsprechende Syntax für Attribute von <xref:System.Windows.Data.Binding> -Objekt Elementverwendung anstelle von einer `Binding` Ausdruck Verwendung. Informationen zu den XAML-Attributen von bestimmten Eigenschaften von <xref:System.Windows.Data.Binding>, finden Sie im Abschnitt "XAML-Attributen" der entsprechenden Eigenschaft des <xref:System.Windows.Data.Binding> in der .NET Framework-Klassenbibliothek.  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Der Name des der <xref:System.Windows.Data.Binding> oder <xref:System.Windows.Data.BindingBase> festzulegende Eigenschaft. Nicht alle <xref:System.Windows.Data.Binding> Eigenschaften können festgelegt werden, mit der `Binding` -Erweiterung, und einige Eigenschaften können festgelegt werden, innerhalb einer `Binding` Ausdruck nur mithilfe von weiteren geschachtelten Markuperweiterungen. Finden Sie unter "Binden von Eigenschaften, dass können werden festlegen mit der Bindung Abschnitt" Erweiterung"".|  
|`value1, valueN`|Der Wert auf die Eigenschaft festgelegt werden soll. Die Behandlung des Attributwerts ist letztlich spezifisch für den Typ und die Logik der spezifischen <xref:System.Windows.Data.Binding> -Eigenschaft festgelegt wird.|  
|`path`|Die Pfadzeichenfolge, der die implizite festlegt <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> Eigenschaft. Siehe auch ["PropertyPath" XAML-Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Nicht qualifizierte {Binding}  
 Die `{Binding}` Anwendungsbeispiel in "Binden Ausdruck Verwendung" erstellt eine <xref:System.Windows.Data.Binding> -Objekt mit Standardwerten, inklusive der anfängliche <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> von `null`. Dies ist immer noch in vielen Szenarien nützlich, da das erstellte <xref:System.Windows.Data.Binding> kann z. B. auf die Schlüsseldaten Bindungseigenschaften zurückzugreifen werden <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> und <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> im Datenkontext zur Laufzeit festgelegt wird. Weitere Informationen über das Konzept der Datenkontext, finden Sie unter [Datenbindung](../../../../docs/framework/wpf/data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Implizite Pfad  
 Die `Binding` Markuperweiterung verwendet <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> als konzeptionelle "Standardeigenschaft", wobei `Path=` muss sich nicht im Ausdruck angezeigt werden. Bei Angabe einer `Binding` Ausdruck mit einem impliziten Pfad, der implizite Pfad muss zuerst in dem Ausdruck vor alle anderen angezeigt `bindProp` = `value` -Paare, wobei die <xref:System.Windows.Data.Binding> Eigenschaft nach Name angegeben ist. Zum Beispiel: `{Binding PathString}`, wobei `PathString` ist eine Zeichenfolge, die ausgewertet wird, um den Wert der <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> in der <xref:System.Windows.Data.Binding> erstellt, indem die Markuperweiterungsverwendung. Sie können einen impliziten Pfad mit anderen benannten Eigenschaften z. B. nach dem Komma als Trennzeichen Anfügen `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Binden von Eigenschaften, die mit der Bindungserweiterung festgelegt werden können  
 Die in diesem Thema gezeigten Syntax verwendet der generische `bindProp` = `value` Näherung, kommen viele Lese-/Schreibeigenschaften der <xref:System.Windows.Data.BindingBase> oder <xref:System.Windows.Data.Binding> , die festgelegt werden können, über die `Binding` Markuperweiterung / Syntax für Ausdrücke. Sie können in beliebiger Reihenfolge, mit Ausnahme von einer impliziten festgelegt werden <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (Sie haben die Möglichkeit, explizit angeben `Path=`, wobei es in einer beliebigen Reihenfolge festgelegt werden kann). Im Grunde einstellbaren 0 (null) oder mehrere der Eigenschaften in der folgenden Liste mit `bindProp` = `value` Paare durch Trennzeichen getrennt.  
  
 Einige der Werte dieser Eigenschaften erfordern Objekttypen, die keine systemeigenen typkonvertierung aus einer Textsyntax in XAML zu unterstützen, und daher Markuperweiterungen erfordern, um als Attributwert festgelegt werden. Überprüfen Sie im Abschnitt "XAML-Attributen" in der .NET Framework-Klassenbibliothek für jede Eigenschaft Informationen; die Zeichenfolge verwenden für die Verwendung von XAML-Attributsyntax mit oder ohne weiteren Markuperweiterung Nutzung ist im Grunde identisch mit den Wert, die Sie, in angeben einem `Binding` Ausdruck mit der Ausnahme, dass Sie nicht jedes Anführungszeichen setzen `bindProp` = `value` in die `Binding` Ausdruck.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: eine Zeichenfolge, die eine Bindungsgruppe möglicher bezeichnet. Dies ist ein relativ komplexes Bindungskonzept. finden Sie auf der Referenzseite für <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolean, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>: kann festlegen, wie eine `bindProp` = `value` Zeichenfolge im Ausdruck, aber dies erfordert einen Objektverweis für den Wert, z. B. eine [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md). Der Wert ist in diesem Fall eine Instanz einer benutzerdefinierten Konverter-Klasse.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: festlegbare in den Ausdruck als eine standardbasierte Windows-Bezeichner. finden Sie im Referenzthema für <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>: kann festlegen, wie eine `bindProp` = `value` Zeichenfolge in den Ausdruck, aber dies ist abhängig vom Typ des übergebenen Parameters. Wenn ein Verweistyp als Wert übergeben wird, erfordert diese Verwendung einen Objektverweis, z. B. eine geschachtelte [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: gegenseitig <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.Source%2A>; jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethodik dar. Finden Sie unter [-Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: kann festlegen, wie eine `bindProp` = `value` Zeichenfolge in den Ausdruck, aber dies ist abhängig vom Typ des Werts übergeben werden. Wenn die Übergabe eines Verweistyps erfordert einen Objektverweis, z. B. eine geschachtelte [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolean, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *Wert* ist ein konstanter Name aus der <xref:System.Windows.Data.BindingMode> Enumeration. Beispielsweise `{Binding Mode=OneWay}`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolean, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolean, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolean, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: eine Zeichenfolge, die einen Pfad in einem Datenobjekt oder ein allgemeines Objektmodell beschreibt. Das Format stellt mehrere unterschiedliche Konventionen für das Traversieren ein Objektmodell, das angemessen in diesem Thema beschrieben werden kann. Finden Sie unter ["PropertyPath" XAML-Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: gegenseitig mit <xref:System.Windows.Data.Binding.ElementName%2A> und <xref:System.Windows.Data.Binding.Source%2A>; jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethodik dar. Finden Sie unter [-Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md). Erfordert eine geschachtelte [RelativeSource MarkupExtension](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) Syntax zum Angeben des Werts.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: gegenseitig <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.ElementName%2A>; jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethodik dar. Finden Sie unter [-Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md). Erfordert eine geschachtelte Erweiterungsverwendung in der Regel eine [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) , eine Objektdatenquelle in einem Ressourcenwörterbuch bezeichnet.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: eine Zeichenfolge, die eine Zeichenfolge Formatkonvention für die gebundenen Daten beschreibt. Dies ist ein relativ komplexes Bindungskonzept. finden Sie auf der Referenzseite für <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: kann festlegen, wie eine `bindProp` = `value` Zeichenfolge in den Ausdruck, aber dies ist abhängig vom Typ des übergebenen Parameters. Wenn die Übergabe eines Verweistyps für den Wert erfordert einen Objektverweis, z. B. eine geschachtelte [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *Wert* ist ein konstanter Name aus der <xref:System.Windows.Data.UpdateSourceTrigger> Enumeration. Beispielsweise `{Binding UpdateSourceTrigger=LostFocus}`. Bestimmte Steuerelemente haben möglicherweise unterschiedliche Standardwerte für diese Bindungseigenschaft. Siehe <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolean, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`. Siehe Hinweise.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolean, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`. Siehe Hinweise.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: eine Zeichenfolge, die einen Pfad in das XML-DOM einer XML-Datenquelle beschreibt. Finden Sie unter [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Im folgenden sind die Eigenschaften des <xref:System.Windows.Data.Binding> , kann nicht mithilfe von festgelegt werden die `Binding` Markuperweiterung /`{Binding}` Ausdruck-Form.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: Diese Eigenschaft erwartet einen Verweis auf einen rückrufimplementierung. Rückrufe/Methoden als Ereignishandler kann nicht in XAML-Syntax verwiesen werden.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: die Eigenschaft nimmt eine generische Auflistung von <xref:System.Windows.Controls.ValidationRule> Objekte. Dies als ein Eigenschaftenelement in ausgedrückt werden könnte eine <xref:System.Windows.Data.Binding> Objekt-Element, aber hat Sie keine unmittelbar zur Verfügung Attribut Analyse Verfahren für die Verwendung in einem `Binding` Ausdruck. Finden Sie unter dem Referenzthema für <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Im Hinblick auf Vorrangs einer Abhängigkeitseigenschaft eine `Binding` Ausdruck ist gleichbedeutend mit einem lokal festgelegten Wert. Wenn Sie einen lokalen Wert für eine Eigenschaft festlegen, die zuvor bereits profitierten eine `Binding` Ausdruck, der `Binding` wird vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Beschreibt die Datenbindung auf einer grundlegenden Ebene wird in diesem Thema nicht behandelt. Finden Sie unter [-Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding> unterstützen keine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Erweiterungssyntax. Sie würden stattdessen Eigenschaftenelemente verwenden. Finden Sie unter Referenzthemen für <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding>.  
  
 Boolesche Werte, die für Markuperweiterungen für XAML werden Groß-/Kleinschreibung. Sie können z. B. angeben entweder `{Binding NotifyOnValidationError=true}` oder `{Binding NotifyOnValidationError=True}`.  
  
 Bindungen, die datenvalidierung umfassen werden in der Regel angegeben, indem eine explizite `Binding` Element statt als ein `{Binding ...}` Ausdruck und Einstellung <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> oder <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> ist ungewöhnlich, dass in einem Ausdruck. Grund hierfür ist die Begleiteigenschaft <xref:System.Windows.Data.Binding.ValidationRules%2A> kann nicht ohne weiteres in der Form Ausdruck festgelegt werden. Weitere Informationen finden Sie unter [implementieren Binding Validation](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md).  
  
 `Binding` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn erfüllt werden als Escapesequenz für Attributwerte, um die nicht als literale Werte oder Namen sein, und diese Anforderung eher global und nicht den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften attributiert. Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax normalerweise wird mit dem ein XAML-Prozessor erkennt, dass eine Markuperweiterung den Zeichenfolgeninhalt verarbeiten muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 `Binding` ist eine untypische Markuperweiterung, die die <xref:System.Windows.Data.Binding> Klasse, die die Funktionalität der Erweiterung für WPF XAML-Implementierung implementiert implementiert auch einige andere Methoden und Eigenschaften, die nicht in XAML beziehen. Die anderen Member dienen zur stellen <xref:System.Windows.Data.Binding> einer vielseitiger und eigenständige Klasse, die viele Datenbindungsszenarien neben fungiert als eine XAML-Markuperweiterung behandeln können.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Data.Binding>  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
