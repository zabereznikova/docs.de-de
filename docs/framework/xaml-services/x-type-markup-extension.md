---
title: x:Type-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: e4d56c5b5deda0bd1df8827020e0b76cc6276c1c
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353774"
---
# <a name="xtype-markup-extension"></a>x:Type-Markuperweiterung
Stellt die CLR <xref:System.Type> -Objekt, das die zugrunde liegende Typ für einen angegebenen XAML-Typ ist.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`prefix`|Dies ist optional. Ein Präfix, das einen nicht standardmäßigen XAML-Namespace zugeordnet. Angeben eines Präfix ist häufig nicht erforderlich. Siehe Hinweise.|  
|`typeNameValue`|Erforderlich. Ein Typname, die auf den aktuellen Standard-XAML-Namespace aufgelöst werden kann; oder das angegebene Präfix Wenn `prefix` angegeben wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `x:Type` Markuperweiterung hat eine ähnliche Funktion für die `typeof()` -Operator in c# oder der `GetType` Operator in Microsoft Visual Basic.  
  
 Die `x:Type` Markuperweiterung gibt das Konvertierungsverhalten für Eigenschaften, die den Typ aus Zeichenfolgen <xref:System.Type>. Die Eingabe ist ein XAML-Typ. Die Beziehung zwischen der Eingabe-XAML-Typ und die Ausgabe CLR <xref:System.Type> ist, die die Ausgabe <xref:System.Type> ist die <xref:System.Xaml.XamlType.UnderlyingType%2A> der Eingabe <xref:System.Xaml.XamlType>, nach der Suche der erforderlichen <xref:System.Xaml.XamlType> basierend auf XAML-Schemakontext und der <xref:System.Windows.Markup.IXamlTypeResolver>Dienst, der den Kontext bereitstellt.  
  
 In .NET Framework-XAML-Dienste, wird die Handhabung dieser Markuperweiterung durch definiert die <xref:System.Windows.Markup.TypeExtension> Klasse.  
  
 In bestimmten frameworkimplementierungen, einige Eigenschaften, die nutzen <xref:System.Type> als Wert den Namen des Typs direkt angenommen werden kann (der Zeichenfolgenwert des Typs `Name`). Implementieren dieses Verhalten ist jedoch ein kompliziertes Szenario. Beispiele finden Sie im folgenden Abschnitt "Hinweise zur WPF-Verwendung".  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `x:Type`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.Markup.TypeExtension.TypeName%2A>-Wert der zugrunde liegenden <xref:System.Windows.Markup.TypeExtension>-Erweiterungsklasse zugeordnet. Unter der standardmäßigen XAML-Schemakontext für .NET Framework XAML-Dienste, die auf CLR-Typen basieren, ist der Wert dieses Attributs die <xref:System.Reflection.MemberInfo.Name%2A> des gewünschten Typs, oder enthält, die <xref:System.Reflection.MemberInfo.Name%2A> vorangestellt wird ein Präfix für einen nicht standardmäßigen XAML-Namespace die Zuordnung.  
  
 Die `x:Type` Markuperweiterung in Objektelementsyntax verwendet werden kann. In diesem Fall geben Sie den Wert der <xref:System.Windows.Markup.TypeExtension.TypeName%2A> Eigenschaft ist erforderlich, um die Erweiterung ordnungsgemäß initialisiert.  
  
 Die `x:Type` Markuperweiterung kann auch als ausführliche Attribut verwendet werden; diese Verwendung ist jedoch nicht typisch: `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a>Hinweise zur WPF-Verwendung  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Standard-XAML-Namespace und Typzuordnung  
 Der XAML-Standardnamespace für WPF-Programmierung enthält die XAML-Typen für die typische XAML-Szenarien benötigen Sie die meisten; aus diesem Grund können Sie häufig Präfixe vermeiden, wenn Sie Werte für XAML-Typen zu verweisen. Sie müssen möglicherweise ein Präfix zugeordnet wird, wenn Sie einen Typ verweist, aus einer benutzerdefinierten Assembly oder für Typen, die in einer WPF-Assembly vorhanden sein, aber aus einem CLR-Namespace, der nicht dem XAML-Standardnamespace zugeordnet werden. Weitere Informationen zum Zuordnen von CLR-Namespaces, XAML-Namespaces und Präfixe finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Geben Sie die Eigenschaften dieser Unterstützung Typename-als-Zeichenfolge  
 WPF unterstützt Techniken, mit denen der Wert für einige Eigenschaften des Typs <xref:System.Type> ohne eine `x:Type` Markuperweiterungsverwendung. Stattdessen können Sie den Wert als Zeichenfolge angeben, die den Typ bezeichnet. Beispiele dafür sind <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> und <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Für dieses Verhalten wird nicht über Markuperweiterungen oder Typkonverter unterstützt. Stattdessen ist dies eine Verzögerung Verhalten über implementiert <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight-Unterstützung eine ähnliche Konvention. In der Tat Silverlight unterstützt derzeit keine `{x:Type}` in der XAML-sprachunterstützung und akzeptiert keine `{x:Type}` Verwendung außerhalb von wenigen Situationen, die WPF-Silverlight-XAML-Migration unterstützt werden sollen. Aus diesem Grund ist das Verhalten der Typename-als-Zeichenfolge in alle Silverlight-Eigenschaft "native"-Evaluierung integriert, in denen eine <xref:System.Type> ist der Wert.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 bietet zusätzliche Unterstützung für generische Typen und das Funktionsverhalten der ändert `x:TypeArguments` und `x:Type` zur Bereitstellung dieser Unterstützung.  
  
-   `x:TypeArguments` und das zugeordnete Objekt-Element für eine generische Objektinstanziierung kann auf andere Elemente als Stamm. Weitere Informationen finden Sie im Abschnitt "XAML 2009" [X: TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 unterstützt eine Syntax zum Angeben eines generischen Typs Einschränkung im Markup. Dies kann verwendet werden, indem `x:TypeArguments`, `x:Type`, oder indem die beiden Funktionen sollten in Kombination.  
  
-   WPF XAML-Implementierung, bei der Verarbeitung von XAML 2009 für Load auch diese Funktion die implizite Typkonvertierungsverhalten für bestimmte Frameworkeigenschaften hinzufügt, mit dem Typ <xref:System.Type>.  
  
 In WPF können Sie XAML 2009-Funktionen verwenden, jedoch nur für loose XAML (XAML, das nicht markupkompiliert ist). Markupkompilierte XAML für WPF und die BAML-Form von XAML unterstützen die XAML 2009-Schlüsselwörter und -Funktionen derzeit nicht.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Style>  
 [Erstellen von Formaten und Vorlagen](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Übersicht über XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
