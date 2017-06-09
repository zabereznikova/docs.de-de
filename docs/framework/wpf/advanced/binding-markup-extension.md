---
title: "Bindung als Markuperweiterung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Binding"
helpviewer_keywords: 
  - "Bindungsmarkuperweiterungen"
  - "XAML, Bindung als Markuperweiterung"
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Bindung als Markuperweiterung
Überträgt einen Eigenschaftswert in einen datengebundenen Wert, indem ein Objekt für den Zwischenausdruck erstellt und der Datenkontext interpretiert wird, der auf das Element und seine Bindung zur Laufzeit angewendet wird.  
  
## Verwenden von Bindungsausdrücken  
  
```  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## Hinweise zur Syntax  
 In der folgenden Syntax sind `[]` und `*` keine Literale.  Es handelt sich um einen Teil einer Notation, mit der angegeben wird, dass 0 \(null\) oder mehr *bindProp*`=`*Wert*\-Paare verwendet werden können, die durch ein `,`\-Trennzeichen getrennt sind und denen *bindProp*`=`*Wert*\-Paare vorangestellt sind.  
  
 Jede der im Abschnitt "Bindungseigenschaften, die mit der Bindungserweiterung festgelegt werden können" aufgeführten Eigenschaften können stattdessen mit Attributen eines <xref:System.Windows.Data.Binding>\-Objektelements festgelegt werden.  Dies ist jedoch nicht die wirkliche Markuperweiterungsverwendung von <xref:System.Windows.Data.Binding>, dies ist nur die allgemeine XAML\-Verarbeitung von Attributen, die Eigenschaften der <xref:System.Windows.Data.Binding>\-CRL\-Klasse festlegen.  Anders ausgedrückt ist `<Binding` *bindProp1*`="`*Wert1*`"[` *bindPropN*`="`*WertN*`"]*/>` eine gleichwertige Syntax für Attribute der <xref:System.Windows.Data.Binding>\-Objektelementverwendung anstelle einer `Binding`\-Ausdrucksverwendung.  Informationen zur XAML\-Attributverwendung von bestimmten Eigenschaften von <xref:System.Windows.Data.Binding> finden Sie im Abschnitt "Verwendung von XAML\-Attributen" der entsprechenden Eigenschaft von <xref:System.Windows.Data.Binding> in der .NET Framework\-Klassenbibliothek.  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Der Name der festzulegenden <xref:System.Windows.Data.Binding>\-Eigenschaft oder <xref:System.Windows.Data.BindingBase>\-Eigenschaft.  Nicht alle <xref:System.Windows.Data.Binding>\-Eigenschaften können mit der `Binding`\-Erweiterung festgelegt werden, und manche Eigenschaften können nur mit einem `Binding`\-Ausdruck festgelegt werden, indem weitere verschachtelte Markuperweiterungen verwendet werden.  Weitere Informationen finden Sie im Abschnitt "Bindungseigenschaften, die mit der Bindungserweiterung festgelegt werden können".|  
|`value1, valueN`|Der Wert, der für die Eigenschaft festgelegt wird.  Die Behandlung des Attributwerts hängt letztendlich vom spezifischen Typ und von der Logik der spezifischen <xref:System.Windows.Data.Binding>\-Eigenschaft ab, die festgelegt wird.|  
|`path`|Die Pfadzeichenfolge, die die implizite <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>\-Eigenschaft festlegt.  Siehe auch [XAML\-Syntax von PropertyPath](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## Nicht qualifiziertes {Binding}  
 Mit der in "Verwenden von Bindungsausdrücken" dargestellten `{Binding}`\-Verwendung wird ein <xref:System.Windows.Data.Binding>\-Objekt mit Standardwerten erstellt, das einen anfänglichen <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> von `null` enthält.  Dies ist in vielen Szenarios weiterhin nützlich, da die erstellte <xref:System.Windows.Data.Binding> möglicherweise wichtige Datenbindungseigenschaften wie <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> und <xref:System.Windows.Data.Binding.Source%2A?displayProperty=fullName> benötigt, die im Laufzeitdatenkontext festgelegt werden.  Weitere Informationen zum Konzept des Datenkontexts finden Sie unter [Datenbindung](../../../../docs/framework/wpf/data/data-binding-wpf.md).  
  
## Impliziter Pfad  
 Die `Binding`\-Markuperweiterung verwendet <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> als konzeptionelle "Standardeigenschaft", wobei `Path=` nicht im Ausdruck angezeigt werden muss.  Wenn Sie einen `Binding`\-Ausdruck mit einem impliziten Pfad angeben, muss der implizite Pfad im Ausdruck an erster Stelle angegeben werden, vor anderen `bindProp`\=`value`\-Paaren, wobei die <xref:System.Windows.Data.Binding>\-Eigenschaft durch den Namen angegeben wird.  Beispiel: `{Binding PathString}`, wobei `PathString` eine Zeichenfolge ist, die als Wert von <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName> in der durch die Markuperweiterungsverwendung erstellten <xref:System.Windows.Data.Binding> ausgewertet wird.  Sie können nach dem Komma als Trennzeichen einen impliziten Pfad mit anderen benannten Eigenschaften anfügen, z. B. `{Binding LastName, Mode=TwoWay}`.  
  
## Bindungseigenschaften, die mit der Bindungserweiterung festgelegt werden können  
 Die in diesem Thema veranschaulichte Syntax verwendet die generische Näherung `bindProp`\=`value`, da es viele Eigenschaften von <xref:System.Windows.Data.BindingBase> oder <xref:System.Windows.Data.Binding> mit Lese\-\/Schreibzugriff gibt, die anhand der `Binding`\-Markuperweiterungs\-\/Ausdruckssyntax festgelegt werden können.  Sie können in jeder Reihenfolge festgelegt werden, mit Ausnahme eines impliziten <xref:System.Windows.Data.Binding.Path%2A?displayProperty=fullName>.  \(Sie haben die Möglichkeit, `Path=` explizit anzugeben. In diesem Fall kann dies in jeder Reihenfolge festgelegt werden.\)  Grundsätzlich können Sie keine oder mehrere der in der folgenden Liste aufgeführten Eigenschaften festlegen, indem Sie `bindProp`\=`value`\-Paare verwenden und durch Kommas voneinander trennen.  
  
 Einige dieser Eigenschaftswerte erfordern Objekttypen, die keine systemeigene Typkonvertierung aus einer Textsyntax in XAML unterstützen. Für diese müssen daher Markuperweiterungen als Attributwert festgelegt werden.  Im Abschnitt zur Verwendung von XAML\-Attributen in der .NET Framework\-Klassenbibliothek für die einzelnen Eigenschaften finden Sie weitere Informationen. Die Zeichenfolge, die Sie für die XAML\-Attributsyntax mit oder ohne Verwendung weiterer Markuperweiterungen verwenden, entspricht im Grund dem Wert, den Sie in einem `Binding`\-Ausdruck angeben, mit dem Unterschied, dass Sie um `bindProp` \=`value` im `Binding`\-Ausdruck keine Anführungszeichen einfügen.  
  
-   <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: Eine Zeichenfolge, die eine mögliche Bindungsgruppe identifiziert.  Dies ist ein relativ komplexes Bindungskonzept, siehe Referenzseite für <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
-   <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolean, kann `true` oder `false` lauten.  Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.Converter%2A>: Kann als `bindProp`\=`value`\-Zeichenfolge im Ausdruck festgelegt werden, hierzu ist jedoch ein Objektverweis für den Wert erforderlich, z. B. eine [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  Der Wert in diesem Fall ist eine Instanz einer benutzerdefinierten Konverterklasse.  
  
-   <xref:System.Windows.Data.Binding.ConverterCulture%2A>: Als standardbasierter Bezeichner im Ausdruck festlegbar. Weitere Informationen finden Sie im Referenzthema zu <xref:System.Windows.Data.Binding.ConverterCulture%2A>.  
  
-   <xref:System.Windows.Data.Binding.ConverterParameter%2A>: Kann als `bindProp`\=`value`\-Zeichenfolge im Ausdruck festgelegt werden, dies ist jedoch vom Typ des übergebenen Parameters abhängig.  Wenn der Typ durch einen Verweis übergeben wird, erfordert diese Verwendung einen Objektverweis, z. B. eine geschachtelte [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.ElementName%2A>: Schließt sich mit <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.Source%2A> gegenseitig aus, jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethodik dar.  Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: Kann als `bindProp`\=`value`\-Zeichenfolge im Ausdruck festgelegt werden, dies ist jedoch vom Typ des übergebenen Werts abhängig.  Beim Übergeben eines Verweistyps ist ein Objektverweis erforderlich, z. B. eine geschachtelte [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolean, kann `true` oder `false` lauten.  Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.Mode%2A>: *Wert* ist ein konstanter Name aus der <xref:System.Windows.Data.BindingMode>\-Enumeration.  Beispielsweise `{Binding Mode=OneWay}`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolean, kann `true` oder `false` lauten.  Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolean, kann `true` oder `false` lauten.  Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolean, kann `true` oder `false` lauten.  Die Standardeinstellung ist `false`.  
  
-   <xref:System.Windows.Data.Binding.Path%2A>: Eine Zeichenfolge, die den Pfad für ein Datenobjekt oder ein allgemeines Objektmodell beschreibt.  Das Format stellt mehrere unterschiedliche Konventionen zum Durchlaufen eines Objektmodells bereit, die in diesem Thema nicht ausführlich beschrieben werden können.  Weitere Informationen finden Sie unter [XAML\-Syntax von PropertyPath](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
-   <xref:System.Windows.Data.Binding.RelativeSource%2A>: Schließt sich mit <xref:System.Windows.Data.Binding.ElementName%2A> und <xref:System.Windows.Data.Binding.Source%2A> gegenseitig aus. Jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethodik dar.  Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  Erfordert eine geschachtelte [RelativeSource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)\-Verwendung, um den Wert anzugeben.  
  
-   <xref:System.Windows.Data.Binding.Source%2A>: Schließt sich mit <xref:System.Windows.Data.Binding.RelativeSource%2A> und <xref:System.Windows.Data.Binding.ElementName%2A> gegenseitig aus, jede dieser Bindungseigenschaften stellt eine bestimmte Bindungsmethodik dar.  Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  Erfordert eine geschachtelte Erweiterungsverwendung, in der Regel eine [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md), die aus einem Ressourcenwörterbuch mit Schlüssel auf eine Objektdatenquelle verweist.  
  
-   <xref:System.Windows.Data.BindingBase.StringFormat%2A>: Eine Zeichenfolge, die eine Zeichenfolgenformatkonvention für die gebundenen Daten beschreibt.  Dies ist ein relativ komplexes Bindungskonzept, siehe Referenzseite für <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
-   <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: Kann als `bindProp`\=`value`\-Zeichenfolge im Ausdruck festgelegt werden, dies ist jedoch vom Typ des übergebenen Parameters abhängig.  Wenn ein Verweis für den Typ übergeben wird, ist ein Objektverweis erforderlich, z. B. eine geschachtelte [StaticResource\-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *Wert* ist ein konstanter Name aus der <xref:System.Windows.Data.UpdateSourceTrigger>\-Enumeration.  Beispielsweise `{Binding UpdateSourceTrigger=LostFocus}`.  Bestimmte Steuerelemente verfügen potenziell über andere Standardwerte für diese Bindungseigenschaft.  Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolean, kann `true` oder `false` lauten.  Die Standardeinstellung ist `false`.  Siehe Hinweise.  
  
-   <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolean, kann `true` oder `false` lauten.  Die Standardeinstellung ist `false`.  Siehe Hinweise.  
  
-   <xref:System.Windows.Data.Binding.XPath%2A>: Eine Zeichenfolge, die den Pfad für das XML\-DOM einer XML\-Datenquelle beschreibt.  Weitere Informationen finden Sie unter [Binden an XML\-Daten mithilfe von XMLDataProvider und XPath\-Abfragen](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Folgende <xref:System.Windows.Data.Binding>\-Eigenschaften können nicht mithilfe der `Binding`\-Markuperweiterung\/`{Binding}`\-Ausdrucksform festgelegt werden.  
  
-   <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: Diese Eigenschaft erwartet einen Verweis auf eine Rückrufimplementierung.  Auf Rückrufe\/Methoden, die keine Ereignishandler sind, kann nicht in XAML\-Syntax verwiesen werden.  
  
-   <xref:System.Windows.Data.Binding.ValidationRules%2A>: Die Eigenschaft nimmt eine generische Auflistung von <xref:System.Windows.Controls.ValidationRule>\-Objekten an.  Dies kann als Eigenschaftenelement in einem <xref:System.Windows.Data.Binding>\-Objektelement ausgedrückt werden, es ist jedoch kein problemlos verfügbares Attributanalyseverfahren für die Verwendung in einem `Binding`\-Ausdruck vorhanden.  Siehe das Referenzthema zu <xref:System.Windows.Data.Binding.ValidationRules%2A>.  
  
-   <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## Hinweise  
  
> [!IMPORTANT]
>  Hinsichtlich des Vorrangs einer Abhängigkeitseigenschaft entspricht ein `Binding`\-Ausdruck einem lokal festgelegten Wert.  Wenn Sie einen lokalen Wert für eine Eigenschaft festlegen, die zuvor über einen `Binding`\-Ausdruck verfügte, wird die `Binding` vollständig entfernt.  Ausführliche Informationen finden Sie unter [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Die Datenbindung auf einer grundlegenden Ebene wird in diesem Thema nicht behandelt.  Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding> unterstützen keine [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Erweiterungssyntax. Sie müssen stattdessen Eigenschaftenelemente verwenden.  Siehe die Referenzthemen zu <xref:System.Windows.Data.MultiBinding> und <xref:System.Windows.Data.PriorityBinding>.  
  
 Bei booleschen Werten für XAML wird die Groß\-\/Kleinschreibung nicht beachtet.  Sie könnten z. B. `{Binding NotifyOnValidationError=true}` oder `{Binding NotifyOnValidationError=True}` angeben.  
  
 Bindungen mit Datenvalidierung werden in der Regel von einem expliziten `Binding`\-Element angegeben und das Festlegen von `{Binding ...}`<xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> oder <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> in einem Ausdruck ist nicht üblich.  Der Grund ist, dass die Begleiteigenschaft <xref:System.Windows.Data.Binding.ValidationRules%2A> nicht unmittelbar im Ausdrucksformular festgelegt werden kann.  Weitere Informationen finden Sie unter [Implementieren der Bindungsvalidierung](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md).  
  
 `Binding` ist eine Markuperweiterung.  Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung stärker global als Typkonverter sind, die bestimmten Typen oder Eigenschaften zugeordnet sind.  Alle Markuperweiterungen in XAML verwenden die Zeichen `{` und `}` in der Attributsyntax. Dies ist die Konvention, durch die ein XAML\-Prozessor erkennt, dass der Zeichenfolgeninhalt von einer Markuperweiterung verarbeitet werden muss.  Weitere Informationen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 `Binding` ist insofern eine untypische Markuperweiterung, als dass die <xref:System.Windows.Data.Binding>\-Klasse, die die Erweiterungsfunktion für die WPF\-XAML\-Implementierung implementiert, auch einige andere Methoden und Eigenschaften implementiert, die keinen Bezug zu XAML besitzen.  Die anderen Member werden dazu verwendet, aus der <xref:System.Windows.Data.Binding>\-Klasse eine vielseitigere und in sich geschlossene Klasse zu machen, die zusätzlich zu ihrer Funktion als XAML\-Markuperweiterung viele Datenbindungsszenarien adressiert.  
  
## Siehe auch  
 <xref:System.Windows.Data.Binding>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)