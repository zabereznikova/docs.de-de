---
title: Bindung als Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: 3455c7ccdedb432fc05c7dc9e80f0f7509f4fa0c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170312"
---
# <a name="binding-markup-extension"></a>Bindung als Markuperweiterung
Verzögert einen Eigenschaftenwert, um einen datengebundenen Wert, Erstellen eines intermediären Ausdrucks-Objekts und interpretieren den Datenkontext, der für das Element und seine Bindung zur Laufzeit gilt.  
  
## <a name="binding-expression-usage"></a>Von Bindungsausdrücken  
  
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
  
## <a name="syntax-notes"></a>Die Anmerkungen zu dieser Syntax  
 In der folgenden Syntax die `[]` und `*` sind keine Literale. Sie sind Teil einer Notation, um anzugeben, dass NULL oder mehr *BindProp*`=`*Wert* Paare verwendet werden können, mit einem `,` als Trennzeichen zwischen Ihnen und vorherigen *BindProp*  `=` *Wert* Paare.  
  
 Die Eigenschaften im Abschnitt "Binden, können werden legen Sie mit der Bindung Erweiterungseigenschaften" aufgeführten konnte stattdessen festgelegt werden mithilfe von Attributen von einem <xref:System.Windows.Data.Binding> Object-Element. Dies ist jedoch nicht wirklich die Markuperweiterungsverwendung von <xref:System.Windows.Data.Binding>, es ist nur die allgemeine XAML-Verarbeitung von Attributen, die Eigenschaften der CLR <xref:System.Windows.Data.Binding> Klasse. Das heißt, `<Binding` *bindProp1*`="`*value1* `"[` *BindPropN*`="`*Wertn* `"]*/>` ist eine alternative Syntax für die Attribute des <xref:System.Windows.Data.Binding> Objekt Objektelementverwendung anstelle einer `Binding` Ausdruck Nutzung. Informationen zu den XAML-Attributverwendung von bestimmten Eigenschaften von <xref:System.Windows.Data.Binding>, finden Sie im Abschnitt "XAML-Attributverwendung" der relevanten Eigenschaft von <xref:System.Windows.Data.Binding> in der .NET Framework-Klassenbibliothek.  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Der Name des der <xref:System.Windows.Data.Binding> oder <xref:System.Windows.Data.BindingBase> festzulegende Eigenschaft. Nicht alle <xref:System.Windows.Data.Binding> Eigenschaften können festgelegt werden, mit der `Binding` -Erweiterung und einige Eigenschaften können festgelegt werden, in eine `Binding` Ausdruck nur mithilfe von weiteren geschachtelte Markuperweiterungen. Finden Sie unter "Binden von Eigenschaften, dass können werden festgelegt mit der Bindung Abschnitt" Erweiterung"".|  
|`value1, valueN`|Der Wert, der die Eigenschaft auf festgelegt. Die Behandlung von den Wert des Attributs ist letztendlich für den Typ und die Logik der spezifischen <xref:System.Windows.Data.Binding> -Eigenschaft festgelegt wird.|  
|`path`|Die Pfadzeichenfolge, die den impliziten festlegt <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> Eigenschaft. Siehe auch ["PropertyPath"-XAML-Syntax](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Nicht qualifizierte {Binding}  
 Die `{Binding}` Gebrauch in "Bindungsausdrücken" erstellt eine <xref:System.Windows.Data.Binding> Objekt mit den Standardwerten, wozu ein ursprüngliches <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> von `null`. Dies ist in vielen Fällen nach wie vor nützlich da das erstellte <xref:System.Windows.Data.Binding> möglicherweise werden der vertrauenden Seite für die Bindungseigenschaften für die wichtigen Daten wie z. B. <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> und <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> im Datenkontext zur Laufzeit festgelegt wird. Weitere Informationen über das Konzept der Datenkontext, finden Sie unter [Datenbindung](../data/data-binding-wpf.md).  
  
## <a name="implicit-path"></a>Implizite Pfad  
 Die `Binding` Markuperweiterung verwendet <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> als konzeptionelle "default-Eigenschaft", wobei `Path=` muss sich nicht im Ausdruck angezeigt werden. Bei Angabe einer `Binding` Ausdruck mit einem impliziten Pfad, der implizite Pfad muss zuerst in den Ausdruck ein, bevor alle anderen Vorkommen `bindProp` = `value` Paare, wobei die <xref:System.Windows.Data.Binding> Eigenschaft wird anhand des Namens. Zum Beispiel: `{Binding PathString}`, wobei `PathString` ist eine Zeichenfolge, die ausgewertet wird, um den Wert der <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> in die <xref:System.Windows.Data.Binding> durch die Verwendung der Markuperweiterung erstellt. Sie können einen impliziten Pfad mit anderen benannten Eigenschaften z. B. nach dem Komma als Trennzeichen, Anfügen `{Binding LastName, Mode=TwoWay}`.  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Binden der Eigenschaften, die mit der Bindungserweiterung festgelegt werden können  
 Die in diesem Thema gezeigten Syntax verwendet den generischen `bindProp` = `value` Schätzung, weil es viele Lese-/Schreibeigenschaften der gibt <xref:System.Windows.Data.BindingBase> oder <xref:System.Windows.Data.Binding> , die festgelegt werden können, über die `Binding` Markuperweiterung / Die Ausdruckssyntax. Sie können festgelegt werden, in beliebiger Reihenfolge, mit Ausnahme von einer impliziten <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (Sie haben die Möglichkeit, explizit angeben `Path=`, wobei sie in beliebiger Reihenfolge festgelegt werden kann). Im Wesentlichen lassen sich 0 (null) oder mehrere Eigenschaften in der folgenden Liste mit `bindProp` = `value` durch Kommas getrennt.  
  
 Einige der Werte dieser Eigenschaften erfordern Objekttypen, die nicht unterstützen eine systemeigene typkonvertierung aus einer Textsyntax in XAML, und daher Markuperweiterungen erfordern, um als Attributwert festgelegt werden. Überprüfen Sie den XAML-Attributverwendung-Abschnitt in der .NET Framework-Klassenbibliothek für jede Eigenschaft Informationen; die Zeichenfolge, die Sie für die XAML-Attributsyntax mit verwenden oder ohne weitere Markuperweiterung Nutzung ist im Grunde identisch mit dem Wert, der Sie, in angeben einem `Binding` Ausdruck mit der Ausnahme, dass Sie keine Anführungszeichen um die einzelnen setzen `bindProp` = `value` in die `Binding` Ausdruck.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: eine Zeichenfolge, die eine mögliche Bindungsgruppe identifiziert. Dies ist ein relativ komplexes Bindungskonzept. finden Sie auf der Referenzseite für <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolesch, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>: kann festgelegt werden, als eine `bindProp` = `value` Zeichenfolge im Ausdruck, jedoch dazu erfordert einen Objektverweis für den Wert, z. B. eine [StaticResource-Markuperweiterung](staticresource-markup-extension.md). Der Wert ist in diesem Fall eine Instanz einer benutzerdefinierten Konverter-Klasse.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: als ein Bezeichner standardbasierte im Ausdruck festgelegt werden. finden Sie im Referenzthema für <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>: kann festgelegt werden, als eine `bindProp` = `value` Zeichenfolge in den Ausdruck, aber dies ist abhängig von dem Typ des übergebenen Parameters. Wenn ein Verweistyp für den Wert zu übergeben, wird diese Verwendung erfordert einen Objektverweis wie z. B. eine geschachtelte [StaticResource-Markuperweiterung](staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: im Vergleich zu sich gegenseitig ausschließende <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.Source%2A>; jede dieser Binden der Eigenschaften eine bestimmten Bindungsmethodik darstellt. Finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: kann festgelegt werden, als eine `bindProp` = `value` Zeichenfolge in den Ausdruck, aber dies ist abhängig von dem Typ des Werts übergeben werden. Wenn die Übergabe eines Verweistyps erfordert einen Objektverweis wie z. B. eine geschachtelte [StaticResource-Markuperweiterung](staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolesch, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *Wert* ein Konstantennamen aus wird die <xref:System.Windows.Data.BindingMode> Enumeration. Beispielsweise `{Binding Mode=OneWay}`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolesch, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolesch, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolesch, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: eine Zeichenfolge, die einen Pfad für ein Objekt oder eine allgemeine Objektmodell beschreibt. Das Format bietet mehrere unterschiedliche Konventionen für das Durchlaufen eines Objektmodells, das angemessen in diesem Thema beschrieben werden kann. Finden Sie unter ["PropertyPath"-XAML-Syntax](propertypath-xaml-syntax.md).  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: mit gegenseitig im Vergleich zu <xref:System.Windows.Data.Binding.ElementName%2A> und <xref:System.Windows.Data.Binding.Source%2A>; jedes dieser Binden der Eigenschaften eine bestimmten Bindungsmethodik darstellt. Finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md). Erfordert eine geschachtelte [RelativeSource MarkupExtension](relativesource-markupextension.md) Nutzung zum Angeben des Werts.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: im Vergleich zu sich gegenseitig ausschließende <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.ElementName%2A>; jede dieser Binden der Eigenschaften eine bestimmten Bindungsmethodik darstellt. Finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md). Erfordert die Verwendung einer geschachtelten Erweiterung, in der Regel eine [StaticResource-Markuperweiterung](staticresource-markup-extension.md) , die auf einer Objektdatenquelle aus einem Schlüssel versehene Ressource-Wörterbuch.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: eine Zeichenfolge, die eine Zeichenfolge Formatkonvention für die gebundenen Daten beschreibt. Dies ist ein relativ komplexes Bindungskonzept. finden Sie auf der Referenzseite für <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: kann festgelegt werden, als eine `bindProp` = `value` Zeichenfolge in den Ausdruck, aber dies ist abhängig von dem Typ des übergebenen Parameters. Wenn die Übergabe eines Verweistyps für den Wert von erfordert einen Objektverweis wie z. B. eine geschachtelte [StaticResource-Markuperweiterung](staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *Wert* ein Konstantennamen aus wird die <xref:System.Windows.Data.UpdateSourceTrigger> Enumeration. Beispielsweise `{Binding UpdateSourceTrigger=LostFocus}`. Bestimmte Steuerelemente verfügen über möglicherweise unterschiedliche Standardwerte für diese Bindungseigenschaft. Siehe <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolesch, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`. Siehe Hinweise.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolesch, kann es sich um `true` oder `false`. Die Standardeinstellung ist `false`. Siehe Hinweise.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: eine Zeichenfolge, die einen Pfad für das XML-DOM des XML-Datenquelle beschreibt. Finden Sie unter [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Im folgenden sind die Eigenschaften des <xref:System.Windows.Data.Binding> , kann nicht mithilfe von festgelegt werden die `Binding` Markuperweiterung /`{Binding}` Ausdruck-Form.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: Diese Eigenschaft erwartet, dass einen Verweis auf eine rückrufimplementierung. Rückrufe/Methoden als Ereignishandler kann nicht in der XAML-Syntax verwiesen werden.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: die Eigenschaft akzeptiert eine generische Auflistung von <xref:System.Windows.Controls.ValidationRule> Objekte. Dies als ein Eigenschaftenelement in ausgedrückt werden könnte eine <xref:System.Windows.Data.Binding> Objekt-Element, aber verfügt über keine verfügbar Attribut-Analyse-Technik für die Verwendung in einer `Binding` Ausdruck. Finden Sie unter Referenzthema für <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Im Hinblick auf haben Abhängigkeitseigenschaften eine `Binding` Ausdruck ist gleichbedeutend mit einem lokal festgelegten Wert. Wenn Sie einen lokalen Wert einer Eigenschaft festlegen, die bisher ein `Binding` Ausdruck, der `Binding` vollständig entfernt. Weitere Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](dependency-property-value-precedence.md).  
  
 Der Datenbindung auf einer grundlegenden Ebene wird in diesem Thema nicht behandelt. Finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding> bieten keine Unterstützung für eine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Erweiterungssyntax. Verwenden Sie stattdessen Eigenschaftenelemente. Finden Sie unter Referenzthemen für <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding>.  
  
 Boolesche Werte für die XAML werden die Groß-/Kleinschreibung. Sie können z. B. angeben entweder `{Binding NotifyOnValidationError=true}` oder `{Binding NotifyOnValidationError=True}`.  
  
 Bindungen, bei denen die datenvalidierung werden in der Regel durch eine explizite angegeben `Binding` Element statt als ein `{Binding ...}` Ausdruck und Einstellung <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> oder <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> ist ungewöhnlich, dass in einem Ausdruck. Grund hierfür ist die zugehörige Eigenschaft <xref:System.Windows.Data.Binding.ValidationRules%2A> kann nicht ohne weiteres in der Form Ausdruck festgelegt werden. Weitere Informationen finden Sie unter [implementieren Binding Validation](../data/how-to-implement-binding-validation.md).  
  
 `Binding` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn eine Anforderung, um die Attributwerte, um als literale Werte oder Namen werden mit Escapezeichen versehen, und die Anforderung eher global und nicht für bestimmte Typen oder Eigenschaften der attributierten Typkonverter ist. Alle Markuperweiterungen in XAML verwenden die `{` und `}` Zeichen in der Attributsyntax, dies ist die Konvention mit dem ein XAML-Prozessor erkennt, dass der Inhalt der Zeichenfolge von eine Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
 `Binding` ist eine ungewöhnliche Markuperweiterung in, das die <xref:System.Windows.Data.Binding> Klasse, die die Funktionalität von Erweiterungen für WPF XAML-Implementierung implementiert implementiert auch einige andere Methoden und Eigenschaften, die nicht mit XAML verknüpft sind. Die anderen Mitglieder machen sollen <xref:System.Windows.Data.Binding> eine vielseitigere und eigenständige-Klasse, die zusätzlich zu Ihrer Funktion als eine XAML-Markuperweiterung viele Datenbindungsszenarien behandeln kann.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding>
- [Übersicht über die Datenbindung](../data/data-binding-overview.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
