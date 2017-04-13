---
title: "x:Type Markup Extension | Microsoft Docs"
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
  - "x:TypeExtension"
  - "Type"
  - "x:Type"
  - "xType"
  - "TypeExtension"
helpviewer_keywords: 
  - "x:Type markup extension [XAML Services]"
  - "XAML [XAML Services], x:Type markup extension"
  - "XAML [XAML Services], TargetType attribute"
  - "TargetType attribute [XAML Services]"
  - "Type markup extension in XAML [XAML Services]"
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 27
---
# x:Type Markup Extension
Gibt das <xref:System.Type>\-Objekt in CLR an, das der zugrunde liegende Typ für einen angegebenen XAML\-Typ ist.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## Verwendung von XAML\-Objektelementen  
  
```  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`prefix`|Optional.  Ein Präfix, das einen nicht standardmäßigen XAML\-Namespace zuordnet.  Die Angabe eines Präfix ist häufig nicht notwendig.  Siehe Hinweise.|  
|`typeNameValue`|Erforderlich.  Ein Typname, der in den aktuellen standardmäßigen XAML\-Namespace aufgelöst werden kann, oder das angegebene zugeordnete Präfix, wenn `prefix` angegeben ist.|  
  
## Hinweise  
 Die `x:Type`\-Markuperweiterung verfügt über eine ähnliche Funktion wie der `typeof()`\-Operator in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] oder der `GetType`\-Operator in [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)].  
  
 Die `x:Type`\-Markuperweiterung gibt das Konvertierungsverhalten aus Zeichenfolgen für Eigenschaften an, die den Typ <xref:System.Type> verwenden.  Die Eingabe ist ein XAML\-Typ.  Die Beziehung zwischen dem Eingabe\-XAML\-Typ und der Ausgabe CLR <xref:System.Type> ist, dass die Ausgabe <xref:System.Type> der <xref:System.Xaml.XamlType.UnderlyingType%2A> der Eingabe <xref:System.Xaml.XamlType>, nach dem Nachschlagen des notwendigen <xref:System.Xaml.XamlType> auf der Grundlage des XAML\-Schemakontexts, ist und der <xref:System.Windows.Markup.IXamlTypeResolver>\-Dienst den Kontext liefert.  
  
 In .NET Framework XAML Services wird die Handhabung dieser Markuperweiterung durch die <xref:System.Windows.Markup.TypeExtension>\-Klasse definiert.  
  
 Bei bestimmten Frameworkimplementierungen sind einige Eigenschaften, die <xref:System.Type> als Wert annehmen, in der Lage, den Namen des Typs direkt \(den Zeichenfolgenwert des `Name` des Typs\) zu akzeptieren.  Solches Verhalten zu implementieren ist jedoch ein komplexes Szenario.  Beispiele finden Sie im folgenden Abschnitt "Hinweise zur WPF\-Verwendung".  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.  Das Zeichenfolgentoken, das auf die `x:Type`\-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.TypeExtension.TypeName%2A>\-Wert der zugrunde liegenden <xref:System.Windows.Markup.TypeExtension>\-Erweiterungsklasse zugeordnet.  Unter dem Standard\-XAML\-Schemakontext für .NET Framework\-XAML\-Dienste, die auf CLR\-Typen basieren, ist der Wert dieses Attributs entweder der <xref:System.Reflection.MemberInfo.Name%2A> des gewünschten Typs oder enthält diesen <xref:System.Reflection.MemberInfo.Name%2A>, dem ein Präfix für eine nicht standardmäßige XAML\-Namensbereichszuordnung vorangestellt ist.  
  
 Die `x:Type`\-Markuperweiterung kann in der Objektelementsyntax verwendet werden.  In diesem Fall muss der Wert der <xref:System.Windows.Markup.TypeExtension.TypeName%2A>\-Eigenschaft angegeben werden, damit die Erweiterung ordnungsgemäß initialisiert wird.  
  
 Die `x:Type`\-Markuperweiterung kann auch als ausführliches Attribut verwendet werden. Allerdings ist diese Verwendung unüblich: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`  
  
## Hinweise zur WPF\-Verwendung  
  
### Standardmäßige XAML\-Namespaces und Namespacezuordnung  
 Der Standard\-XAML\-Namespace für WPF\-Programmierung enthält die meisten der XAML\-Typen, die Sie für typische XAML\-Szenarien benötigen, daher können Sie beim Verweisen auf XAML\-Typwerte oft Präfixe vermeiden.  Sie müssen möglicherweise ein Präfix zuordnen, wenn Sie auf einen Typ einer benutzerdefinierten Assembly verweisen, oder bei Typen, die in einer WPF\-Assembly vorliegen, aber aus einem CLR\-Namespace stammen, der nicht dem XAML\-Standardnamespace zugeordnet war.  Weitere Informationen über Präfixe, XAML\-Namespaces und das Zuordnen von CLR\-Namespaces finden Sie unter [XAML\-Namespaces und Namespacezuordnung für WPF\-XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### Geben Sie Eigenschaften an, die Typnamen\-Als\-Zeichenfolge unterstützen  
 WPF unterstützt Techniken, die das Angeben des Werts einiger Eigenschaften des Typs <xref:System.Type>, ohne die Verwendung einer `x:Type`\-Markuperweiterung zu erfordern.  Stattdessen können Sie den Wert als Zeichenfolge angeben, die den Typ benennt.  Beispiele dafür sind <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=fullName> und <xref:System.Windows.Style.TargetType%2A?displayProperty=fullName>.  Unterstützung für dieses Verhalten wird nicht durch Typkonverter oder Markuperweiterungen bereitgestellt.  Stattdessen ist dies ein durch <xref:System.Windows.FrameworkElementFactory> implementiertes Aufschiebungsverhalten.  
  
 Silverlight unterstützt eine ähnliche Konvention.  Tatsächlich unterstützt Silverlight derzeit `{x:Type}` nicht in der XAML\-Sprachunterstützung und akzeptiert keine `{x:Type}`\- Verwendungen außerhalb bestimmter Umstände, die WPF\-Silverlight XAML\-Migration unterstützen sollen.  Daher ist das Verhalten "Typname\-Als\-Zeichenfolge" in alle systemeigenen Eigenschaftenauswertung von Silverlight integriert, in denen <xref:System.Type> der Wert ist.  
  
## XAML 2009  
 XAML 2009 bietet zusätzliche Unterstützung für generische Typen und ändert das Funktionsverhalten von `x:TypeArguments` und `x:Type`, um diese Unterstützung zu bieten.  
  
-   `x:TypeArguments` und das zugeordnete Objektelement für eine generische Objektinstanziierung können sich in anderen Elementen als den Stammelementen befinden.  Weitere Informationen finden Sie im Abschnitt "XAML 2009" von [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 unterstützt eine Syntax zum Angeben einer Einschränkung für den generischen Typ in Markup.  Dies kann von `x:TypeArguments`, von `x:Type` oder von den zwei Funktionen zusammen verwendet werden.  
  
-   Die WPF\-XAML\-Implementierung fügt beim Verarbeiten von XAML 2009 für Ladevorgänge diese Funktion auch dem impliziten Typkonvertierungsverhalten für bestimmte Frameworkeigenschaften hinzu, die den Typ <xref:System.Type> verwenden.  
  
 In WPF können Sie XAML 2009\-Funktionen verwenden, jedoch nur für Loose XAML, und nicht für markupkompiliertes XAML.  Markupkompilierte XAML für WPF und die BAML\-Form von XAML unterstützen die XAML 2009\-Schlüsselwörter und \-Funktionen derzeit nicht.  
  
## Siehe auch  
 <xref:System.Windows.Style>   
 [Erstellen von Formaten und Vorlagen](../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Übersicht über XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)